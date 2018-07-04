+++
title = "Avenza Georeferenced Maps in QGIS"
description = "How to create an Avenza georeferenced 'PDF' that will work as a referenced map in the Avenza app"
weight = 20
draft = false
date = 2018-07-04T16:05:45-06:00
tags = ["QGIS", "Avenza", "Field Work"]
categories = ["Environment", "Geomatics"]
+++

I have tried using Avenza PDF in the past on my phone but was never able to get an easily exportable map to work with it from QGIS. That was until I actually tried to google around a bit and figure out how to make it work. I am using QGIS 3.2 so was unable to use some of the plugins that I had found as they were for earlier versions of QGIS and haven't been updated at this time.

So, to start I created a basic map using the print composer and attempted to load it into Avenza, which then quickly told me the map was not georeferenced. That's no good, but wasn't a surprise. That would be too easy! Though the real solution wasn't too far off. All you need to do is export your map as a .TIFF and ensure that you select 'Save World File' under the layout export settings menu. If you are doing an atlas of pages, you can set the output to be .tiff there as well for each page of the atlas. With this .TIFF I was able to import the file directly into Avenza without issue and it worked great.
