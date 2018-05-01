+++
title = "GeoServer Fun"
description = "My attempts at setting up a proper GeoServer so that my team can access large datasets locally"
weight = 20
draft = false
date = 2018-05-01T13:42:23-06:00
tags = ["GeoServer", "GIS","Large Data", "Open Source"]
categories = ["Environment", "Geomatics"]
+++

I got this big idea in my head that I wanted to make it easier for co-workers to access the treasure trove of GIS data I have been collecting. Mostly just standard public datasets, but it's nice to be able to pull them into your GIS Environment and view them along with the other layers your looking at. Originally I had setup a bunch of geopackages on dropbox to organize and share the datasets, however this required each user to download a local copy of the data and wasn't terribly efficient. This got me thinking about tiling and a proper server scenario.

I had fooled around a bit with basic XYZ tiling for some large raster files, and it worked relatively well but each one would require the work to go into tiling it and hosting a simple server to handle serving up the files. This seemed tedious and an inevitable nightmare to deal with as more layers inevitably get added and the system grows. So I started looking into my options... which led me to [GeoServer](http://geoserver.org/). This seemed pretty promising and so far it has been. At this point I'm still just implementing it slowly and adding layers. For the most part it has been simple to add geopackages as stores and then publish each individual layer. It is a rather elegant server solution and seemingly just works. Though it does some poking around to figure out how to get things rolling.

The next big step is to work on adding some of the really large raster datasets I have and get them delivered and tiled while being cached locally. It seems like this shouldn't be too hard, but I am still syncing up the machine I am using as a server and it says it will take another 24hrs to complete the data transfer.... I guess i'll discuss the tiling functionality of geoserver later.
