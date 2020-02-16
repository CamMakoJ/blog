+++
title = "Blender Topography Maps of Alberta - 1"
description = "I have seen a few of these before and thought it would be need to try out for myself"
weight = 20
draft = false
date = 2020-02-16T11:15:08-06:00
tags = ["DEM", "Contours", "Blender", "QGIS"]
categories = ["Environment", "Geomatics"]
+++

### Acquiring Our Data
I have seen some really cool applications of DEM models in blender. I have done a bit of messing around in blender previously, however it's been awhile and I never really got very good at it. So we shall see how this goes, but i'm taking a crack at importing the province of Alberta's 25m DEM from Altalis. It is a public dataset so if you want to snag it head here [Altalis](https://www.altalis.com/).

### What next?
Well given blender doesn't natively support GIS data to make things easy, I am using the [BlenderGIS](https://github.com/domlysz/BlenderGIS) addon. It works great though can take some effort to setup as you really need to install gdal and numpy in python as well. I won't go into that as I really just followed the instructions on the BlenderGIS page.

As well to make my life easier, I warped all the data into the same projection (in this case UTM12N). This should make things easier in blender as they should at least all align properly.

I tried a few different methods for importing my DEM but it wasn't quite as straightforward as I had hoped as blender didn't like my .tif for some reason (After some research I now realize that its because I didn't export it with a .tfw worldfile). Now that I have the worldfile I am good to go. I also used BlenderGIS to import google satellite imagery to overlay the mesh though I couldn't find a great way to overlay that properly.

This is a work in progress for sure. Check back in the future to see how it goes.
