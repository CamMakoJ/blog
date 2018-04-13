+++
title = "Creating a DEM from Contours"
description = "I somehow always forget how to do this and have to rebuild the wheel, now I wont forget... or can at least find the wheel"
weight = 20
draft = false
date = 2018-04-13T15:02:33-06:00
tags = ["QGIS", "GrassGIS", "Contours", "DEM"]
categories = ["Geomatics"]
+++

### Contours
Contours are a great way to visualize topography on a flat map without covering background imagery. It is often great for figures where you want a visible basemap.

### Digital Elevation Model
That being said it is nice to have a digital elevation model (DEM) for easier interpretation of what the ground is looking like. I find this easier to see where there are steep slopes and depressions that may be wetlands.

### DEM --> Contours
Generally this is a fairly simple task and most GIS suites can handle it quite simply with a dedicated contour extraction tool. From an elevation raster to vector lines. This is usually simpler as you are decreasing the resolution of the data in a sense and removing all the "in-between" and are just left with the contour break lines.

### Contours --> DEM
This is often where I get hung up in processing as its much less intuitive. It makes sense that it would be trickier as you are trying to re-interpret the original data and fill in all the gaps, where you are starting with break lines.
