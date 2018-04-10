+++
title = "Environmental Map"
description = "This is an environmental map that I plan on working "
date = "2018-04-04T09:34:47-06:00"
weight = 20
draft = false
bref = "A map filled with all the environmental data I can find"
toc = false
tags = ["Geomatics", "LeafletJS", "WMS"]
+++

{{< load-leaflet >}}
{{< load-betterwms >}}

<div id="map" style="width:100%;height:600px;">
<script>

// Overlay layers
var amwiLayer = L.tileLayer.betterWms('https://maps.alberta.ca/genesis/services/Alberta_Merged_Wetland_Inventory/Latest/MapServer/WMSServer?', {
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

*Many layers will only work at certain zoom levels.*

#### Layer List and Sources
| Layer | Source |
| --- |---|
| Alberta Merged Wetland Inventory | https://maps.alberta.ca/genesis/services/Alberta_Merged_Wetland_Inventory/Latest/MapServer/WMSServer |
