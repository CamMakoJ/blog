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
Leaflet JS is a javascript library for the creation of web maps.

<div id="map" style="width:100%;height:500px;">
<script>

//simple map
var map = L.map('map', {
  center: [51.08,-114.09],
  zoom: 12,
  preferCanvas: true
  });

var controlLayers = {
  amwiLayer: L.tileLayer.wms('https://maps.alberta.ca/genesis/services/Alberta_Merged_Wetland_Inventory/Latest/MapServer/WMSServer?',{
    layers: '12'
    })
}
      L.control.layers(controlLayers)
      controlLayers.amwiLayer.addTo(map)

    // Load Esri Leaflet from CDN
  // L.esri.basemapLayer("Imagery").addTo(map);
</script>
</div>
