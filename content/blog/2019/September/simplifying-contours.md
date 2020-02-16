+++
title = "Using a DEM and getting Simplified Contours"
description = "Using a digital elevation model to get simplified contours"
weight = 20
draft = false
date = 2019-09-28T11:15:08-06:00
tags = ["DEM", "Contours", "Simplified"]
categories = ["Environment", "Geomatics"]
+++

When creating contours from high resolution DEM data you can often have a lot of distracting artifacts for small areas with slight deviations in topography. Depending on the final resolution of your end product and the intent of the maps you are creating it may be beneficial to reduce the resolution of the DEM so that your contours are simplified. This is a lossy process and the contours will lose detail but the cost is offset by readability, which can often be worth it.

### Resampling the DEM
This processing tool essentially adjusts the resolution of the DEM based on the parameters input. It is a SAGA tool where you select your grid, your upscale and downscale method (I like to just use nearest neighbor) and a cell size. Generally I leave extent blank as I want the extent to match the input data. The cell-size is what is usually of most importance, as it will be the new resolution of the data (For eg. if I have a 0.5 m cell size DEM if I adjust the cell size here to 10 m it will re-sample those grids to meet the new cell size). Often I find myself adjusting the cell size a few times based on the of the contours that I get in the end.

### Creating the Contours
This is a built-in QGIS raster tool under the extraction menu. You should select the re-sampled DEM layer from earlier and it should recognize the band number (DEM generally just have one) and assuming the DEM is using ELEV as the attribute then you should be fine using default settings. The interval between contour lines depends on the output your looking for. In this case I wanted 1 m intervals (one of the reasons you end up with so many small and distracting lines). The offset is optional, generally I leave that at default.
At this point if there is still an unnecessary level of detail for your product it might be worth to resample the DEM again at a larger cell size. Continue to do this until your happy with the results, keeping in mind that the larger the cell size the more information is lost so always keep the end product and its intent in mind.
