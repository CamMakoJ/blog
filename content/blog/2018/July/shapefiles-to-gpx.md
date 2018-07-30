+++
title = "Turning Shapefiles into a GPX"
description = "This seemingly simple task has often given me grief in the past, I will try and explain my process"
weight = 20
draft = false
date = 2018-07-30T15:53:44-06:00
tags = ["QGIS", "GPS", "Shapefiles", "GPX"]
categories = ["Geomatics"]
+++

Quite often for environmental field work I need to convert shapefiles or other GIS formats into GPX files. Now this would seem like it should be a simple task for the mighty QGIS. However in many cases its not as simple as hitting export and choosing the gpx file type. What I have found is super helpful is considering what I typically see in GPX files. Routes, Tracks, and Waypoints. This is a little different then the points, lines, and polygons of the shapefile world. Typically then I like to convert all of my polygons to lines prior to saving as a GPX. I find this is super effective at ensuring the GPX file is happily readable by your GPS. The next thing I generally do is re-project the layers into [WGS 84 (EPSG: 4326)](http://www.epsg-registry.org/export.htm?wkt=urn:ogc:def:crs:EPSG::4326)

Converting to lines and re-projecting usually completes my geometry steps. The next issue is generally the limited attributes within a GPX file. When you save the GPX file ensure you enable 'GPS_USE_EXTENSIONS' or remove all the attributes from the shapefile other then 'name'.

That process typically works for me, I am looking to automate it, and will provide an update if I get around to it.
