+++
title = "Using Expressions in a QGIS Atlas"
description = "Automating atlas style maps with overviews that change as well"
weight = 20
draft = false
date = 2018-06-05T10:44:45-06:00
tags = ["QGIS", "Expressions", "Atlas"]
categories = ["Geomatics"]
+++

It has taken me a long time to get comfortable with the print composer in QGIS. I think for me the biggest issue is once you hit that composer you need to combine all the data you have worked with and make it look appealing while conveying the message you are trying to tell with the map. It's art, it's science, it's cartography! It also can be a very fun part of telling the data's story and I love maps for that as they can show a lot in a simple way.

One way to improve the message your telling, depending on the project, is to use the Atlas feature of QGIS. In it you can create a series of maps that are based on features within a coverage layer. Say you have a layer with 10 polygons representing areas of interest but they are far apart and you want to have 1:5000 map of each. If you use this layer as your 'coverage' layer then the print composer will create 10 'maps' each focused on 1 of the polygons.

### Setting the Coverage Layer
In the print composer, select the 'Atlas' panel near the layout and item properties panels. If this isn't visible under 'View>Panels' make sure the 'Atlas' panel is checked. Once your in the panel, check the 'Generate Atlas' box and configure the coverage layer. You can also select an attribute to serve as the page name (typically I would use a unique identifier or if you have a name attribute that works great to).  As well I generally try and have an 'order' attribute included so that I can set them to export in an order I want. I find using a fid finicky, as they often aren't in the order you want them.

### Using Expressions to Update maps
One of the most powerful features of atlas making is the ability to use expressions to individualize each map of the atlas. A basic example could be pulling attributes from the current feature into a textbox. To do this, create the textbox normally. Then in the Item Properties panel, select 'insert expression'. This will open a window like this:
![QGIS Expression Window](/img/posts/qgis-atlas-expressions/expression-screen.JPG)

This is an expression to take two attributes for each feature, "NorthingA" and "EastingA" and combine them into a string separated by a comma. On the atlas page then this textbox is providing a specific location on each of the maps that I want to show. This is incredibly useful if you want each of the atlas pages to display specific information to that feature.
