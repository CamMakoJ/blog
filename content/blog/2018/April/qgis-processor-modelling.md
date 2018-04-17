+++
title = "QGIS Processor Modelling"
description = "Using the QGIS process modeller to make up for my lack of python skills"
weight = 20
draft = false
date = 2018-04-12T17:03:46-06:00
tags = ["QGIS", "Process Modelling", "Constraints Mapping"]
categories = ["Environment", "Geomatics"]
+++

### Constraints Mapping
I had a project where I needed to look at constraints mapping for a series of project areas. Essentially I needed to look at a project and see what parts and how many layers it intersected with. The first thing I wanted to look at was how to go about automating as much as I could and since my python skills are still very green I looked into using the new to me QGIS process modeler.

### Processing Modeler
The process modeler is a rad tool as you can work out a process visually and not need to worry about the 'raw' coding. It does have its limitations, but it does open up a whole world of scripting with a pretty small investment to understand it. Here is a quick example I created so I could merge and clip a variety of shapefiles at once.

![QGIS Processor Modeler](/img/posts/qgis-process-modeler/process-modeler.JPG)

You can see that I take three types of inputs (points, lines, and polygons) and then process them through a "merge" followed by a "clip" and then three outputs. This was something that I normally would have done by hand, creating a lot of temporary shapefiles in the process. This way I just end up with the outputs that I want, and while it may take longer to process, its all in one step. Hopefully I will find new ways to use this and have some cooler examples in the future.
