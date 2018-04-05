+++
title = "LeafletJS Maps"
description = "I have been wanting to learn about leaftlet maps for awhile... here goes"
weight = 20
draft = false
date = 2018-04-04T11:03:51-06:00
tags = ["LeafletJS", "Web Maps"]
categories = ["Geomatics", "Coding"]
+++

{{< load-leaflet >}}

### LeafletJS
Leaflet JS is a javascript library for the creation of web maps. I wanted to use
it to create a simple web-map for viewing the Alberta Merged Wetland Inventory (AMWI) streamed
via a web map service (WMS). Eventually I would like to be able to upload a shapefile to
zoom to an area and determine if an area does intersect any mapped wetlands. To access the
WMS for the AMWI I used the links available in Alberta's open data portal. This is an excellent
service for both accessing data as a service or downloading data for local use as well.

<div id="map" style="width:100%;height:350px;">
<script>

// Overlay layers
var amwiLayer = L.tileLayer.wms('https://maps.alberta.ca/genesis/services/Alberta_Merged_Wetland_Inventory/Latest/MapServer/WMSServer?', {
  layers: '12',
  transparent: true,
  format:  'image/png'
});
// overlay object
var overlayMaps = {
  "AMWI": amwiLayer
};

// Basemap layers
var esriImagery = L.esri.basemapLayer("Imagery");
var esriTopography = L.esri.basemapLayer("Topographic");
// Basemap object
var baseMaps = {
  "Imagery": esriImagery,
  "Topographic": esriTopography
};

//simple map
var map = L.map('map', {
  center: [51.25, -113.88],
  zoom: 15,
  layers: [esriImagery, amwiLayer]
});
//adding the layer controls
L.control.layers(baseMaps, overlayMaps).addTo(map);

</script>
</div>

<br>

### Creating the map
This was my first foray into LeafletJS so I started by adding the javascript libraries and
ensured they were loading correctly. Then I added a simple empty map based on the
template shown in the [LeafletJS Docs](http://leafletjs.com/reference-1.3.0.html#map-factory). The 'layers'
properties will be the default visible layers. But should be left out if your testing at this
point.


```javascript
var map = L.map('map', {
  center: [52.00, -115.00],
  zoom: 15,
  layers: [esriImagery, amwiLayer]
});
```
One of the first issues I ran into was that I had not first added the map div to the HTML.
I needed to create a div with the same ID as the map variable used above then the javacript
would know where to render the map. In my case that's the simple `<div id="map">`.

### Adding the WMS layer
To add the basemap and the AMWI layer using WMS services is the next component. Since we are
using one as a basemap and the other as an overlay layer they needed to be added separately.

The AMWI layer is saved as a variable and includes an object specifying the WMS options. There are
more options available then those used, but so that the basemaps are visible underneath the AMWI overlay we need to
specify that the we want `transpert: true` and `format: 'image/png'` otherwise the null data will appear opaque and
block the basemaps.
```javascript
var amwiLayer = L.tileLayer.wms('https://maps.alberta.ca/genesis/services/
Alberta_Merged_Wetland_Inventory/Latest/MapServer/WMSServer?', {
  layers: '12',
  transparent: true,
  format:  'image/png'
});
```
Once we have the layer as a variable we create an object with all of the intended overlay
layers (in this case just AMWI). This will then be added to the layer controller of the leaflet.
```javascript
var overlayMaps = {
  "AMWI": amwiLayer
};
```
Once that is complete you can do the same with the basemaps you want to use (I used ESRI).
Create an object with all of the basemaps you want available and then add them to the leaflet map.
This code will go just underneath your call to create the map itself and it adds the
option to toggle layers on/off as well as switch basemaps.

```javacript
L.control.layers(baseMaps, overlayMaps).addTo(map);
```

I am going to keep working on a more advanced version of this [Environmental Map]({{< relref "docs/environmental-map.md" >}})
