+++
title = "AER Shapefile Submissions"
description = "These can be tricky as their intake can be a little picky"
weight = 20
draft = false
date = 2018-05-29T11:49:16-06:00
tags = ["AER", "Shapefile", "Water Act", "QGIS"]
categories = ["Environment", "Geomatics"]
+++

The [AER One Stop](https://www1.aer.ca/onestop/) is a great regulator solution to some of the uncertainty in project delivery, such as to who to send what to. However it has created some confusion on its own that I have dealt with when formatting shapefiles for upload to the site. I have really only used this feature as part of Water Activities and they have since released [guidelines](https://www1.aer.ca/onestop/documents/QRG_ImportSpatialData_WaterActApplications.pdf) on how to ensure your shapefile complies with their filters.

The key really is that the shapefile needs to be in the NAD83 10TM AEP (Forest) projection. I find this easiest to find in my GIS software using the EPSG:3400 code. The shapefile itself also can only have 3 fields, not including the geometry itself (FID, ID, and Name) FID being the default numbering, ID being a unique number for each polygon being submitted, and name being a text name of the polygon in question.

### Changing Projection and Creating fields in QGIS
Generally in Alberta I find project boundaries and drawing in different projections, but typically UTM 12N or UTM 11N. So the first step to ensure that the polygon can be re-projected to the correct projection (10TM Forest). Then the second component is ensuring the fields meet the allowable values as described above.

#### Re-Projection
There are a few ways to do this. For me the simplest is generally to create a new empty shapefile in the projection that I want it to be (in this case 10TM Forest). Once I have done that then I toggle it to make it editable and copy the polygon from the original shapefile to the new layer. At this point ensure you check that your shapefiles match and are in the correct real world locations using imagery, or other reference material.

#### Creating Fields
When creating the shapefile you have the ability to add fields as shown in the image above, however if you didn't do it at that stage its ok. Now that we have our polygon in the appropriate projection and the right place spatially we can add fields to the attribute table itself. Once you have done that the FID will auto populate and you can fill in the ID as well as the name.
