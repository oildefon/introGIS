[<<< Previous](../README.md)  | [Next >>>](2setup.md)  

# Basic GIS Lexicon

There are two main types of data used in a GIS system when making a map. They are vector data and raster data. Vector data is the most common form of map data and is made up of points, lines and polygons that are drawn to represent physical features or locations. Rasters are images such as satellite imagery or aerial photography and are much less common, but can be very useful for certain types of mapping projects.

A good way to make sense of these concepts is by looking at a conventional map and analyzing the information it shows:

![Map of Current Rail Speeds in the United States](images/usamap.png)

CC BY-SA 3.0 derivative work: User:Justthisonceokey Blank_US_Map.svg: User:Theshibboleth – Blank_US_Map.svg: User:Theshibboleth Routes derived from Amtrak-Streckennetz.svg Speed limits own work. Inspired by High_Speed_Railroad_Map_of_Europe_2013.svg

This map shows the current rail speeds in the United States. In order to convey information about rail speeds the map contains railroad information (the lines) and their respective speeds (different colors, according to the legend), plus cities that have railroads (red dots) and states (gray polygons). In GIS, these points, lines and polygons are known as *features*.

## Layers

Features on a map are organized in "layers." To understand layers, imagine having several different transparency film sheets, each one with a different type of features drawn over it. For example, one transparency sheet to display US states, another one to display only railroads, and a last one to display just the red dots that represent the cities. When these transparent sheets are overlayed on top of each other, they would look like the map above. Each of these features is represented as a vector—that is, scalable points, lines or polygons that can be easily created, edited, or deleted using QGIS.

## Features and Attributes

A feature is a entity that appears in a layer on a map. For example, each feature on the above railroads layer would represent one railroad line. Each layer contains the same type of feature (points, lines or polygons).

An *attribute* is a characteristic of a feature, for example, if the line drawn on the map is a feature that represents the railroad line, then the attribute would be a variable that describes something about that line, such as the average speed of trains on that railroad line. 

Each layer will have its own attribute table, which is basically a spreadsheet showing each feature as a row, and each attribute as a column. Just like in stats software, attributes can contain data as strings (text), numerical, date, or boolean.

## Geographic Data and Coordinate Reference System

GIS files will also include geographic data that tells QGIS what vectors to create for each feature (be they points, lines or polygons), that will be represented in space according to a Coordinate Reference System (CRS), which is basically a reference for QGIS to know how to transpose aspects in a three-dimensional spherical world into two-dimensional rectangular representations. All layers in your map must be on the same CRS, otherwise data will be inaccurate or even incompatible.

Below you will find two projections of the United States. Notice in the first one that the shape of the country is different to the shape we are used to seeing on maps, because it is a different projection (Sphere Azimuthal Equidistant projection). The second example is using a projection that is intended for Tokyo. Alaska and Hawaii are visible, but the United States mainland became a sprayed line. Tokyo would look great on this projection, though. This gives you an idea of how important CRS are, and how different the same geographic shapes can look depending on the projection.

![Sphere Azimuthal Equidistant projection](images/proy1.png)  ![Tokyo Japan Plane Rectangular CS XVIII](images/proy2.png)

Bear in mind that data might not have geographic information but could still be used in QGIS. For example, if on one hand you have a spreadsheet with data about the states, and on the other hand you have a vector layer representing states but with no attributes, you can join the dataset and the vector layer so that all the data in the spreadsheet will become attributes for the vector layer. You can also map points on a map if you have coordinates or even physical addresses. The process of using geographic data to represent features on a GIS is called georeferencing. 

## File Formats in QGIS: Shapefiles

Vector layers are commonly shared in shapefile format (.SHP). Shapefiles in GIS generate many files with the same name but different formats, and they all need to be in the same location for QGIS and other GIS software to open them correctly. Remember this when saving and copying layers. To tackle this inconvenience, GIS software has evolved and allows to read compressed files (i.e. .zip, .gz) that already contain all of the related files required by the layer.

## Other Types of Layers in QGIS: Raster Layers

There are other ways to display spatial data in QGIS in addition to vector layers. The other common type of layer is the raster layer, which consist of images for reference, aesthetics or additional information. Rasters are essentially photos that have data stored in each pixel.  Since rasters can store so much data, they are best used to represent continuous data in which every point in space might be a different value, such as a layer of data that describes temperature or elevation. For example, most heatmaps are made with raster data. Sometimes rasters are simply images with no data stored in them, such as a historical map that's been scanned into a computer. In this case, the raster image could be used as a baselayer or reference point. 

Raster layers can be turned into vectors using QGIS, although for the data to be usable, thresholds and cutoffs must be used to narrow data in bins (i.e. elevation 0-10m; 10-20m; 20-30m…). Raster layers are commonly shared in .tiff format, and the images contain metadata including georeferenciation (normally, the coordinates of each corner), and the numeric values stored in bands, which were used to generate the colors in the image.

[<<< Previous](../README.md)  | [Next >>>](2setup.md)  
