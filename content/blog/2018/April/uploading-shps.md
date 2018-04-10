+++
title = "Uploading shapefiles to LeafletJS"
description = "I have been wanting to learn about leaftlet maps for awhile... here goes"
weight = 20
draft = true
date = 2018-04-05T09:45:15-06:00
tags = ["LeafletJS", "Web Maps", "shapefile"]
categories = ["Geomatics", "Coding"]
+++

{{< load-leaflet >}}

{{< shp-uploader >}}

<script src="{{ "/js/shp.js" | relURL }}" type="text/javascript">


### Building on Previous Learning
Yesterday I worked through connecting a WMS server to a [leaflet map]({{ relref "blog/2018/April/leafletmaps.md"}}). Now I want to be able to upload a shapefile to that
map.

### Uploading the file
I have worked with this before in some other small projects and so I won't get too in
depth on how this works.

### Map and Uploader

  <input type='file' id="shapefile"> <br>
  <input type='button' id='upload' value='load' onclick='loadFile();' class='button w30'>
