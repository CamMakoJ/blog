+++
title = "Using a DEM to get Slope Directions"
description = "Using a digital elevation model to get slope gradients"
weight = 20
draft = false
date = 2018-08-03T11:15:08-06:00
tags = ["DEM", "Slope", "Catchment Areas", "Wetland Assessment"]
categories = ["Environment", "Geomatics"]
+++

To properly assess wetlands it's important to understand what is happening to surface water at and near the wetland itself. If you have a digital elevation model from LIDAR or something similar then you can look at visually to determine the catchment areas and slope direction, however in some cases I find the overall surface to be too flat to effectively do this visually. I also find that using software to do the math is a lot easier... and more reproducible. So I will show you the process that I have used to create a grid of flow direction arrows in QGIS.

### Gradient Vectors From Surface
This processing tool essentially takes the value from the DEM and then calculates out, based on the 'step' area what the general slope and aspect are for each section of the grid. The Size Range min/max setup the area that will be averaged for each arrow. I find a reasonable scale here often creates better results. A setup I typically use is as follows:

![Gradient Vectors from Surface](/img/posts/slope-direction-from-dem/surface-gradient.JPG#center)


The values you use however will heavily depend on the resolution and size of your DEM as well as what your trying to visualize, such as landscape level flow or very intricate flow patterns. If you are looking for something more intricate then it is likely you would benefit from some of the other SAGA tools that do channelization prediction.
