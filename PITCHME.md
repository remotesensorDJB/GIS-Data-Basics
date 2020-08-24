@title[GIS Data Basics]
GIS Data Basics
-------------------------------
### @fa[globe fa-5x]
###### D.J. Biddle, GISP
###### Use the @fa[angle-down] and @fa[angle-right] arrows to navigate
---
@title[the plan]
#### the plan
- The way I see it...conceptual models @fa[arrow-right] data models
- Issues of representation
- The evolution of the ArcGIS platform
---
@title[Conceptual Models vs Data Models]

@snap[west span-40]
@css[fragment](First, a question...)
@snapend

@snap[east span-50]
@css[fragment](What *ARE* GIS data?)
@snapend
+++
@snap[north span-20]
@css[fragment](A layer??)
@snapend

@snap[west span-40]
@css[fragment](A shapefile?)
@snapend

@snap[east span-60]
@css[fragment](An image?)
@snapend

@snap[south span-80]
@css[fragment](A GPS file?)
@snapend
+++
While all are terms for GIS data of some type, none really gets at the essence of what GIS data really are?
+++
In the simplest terms, GIS data are representations of reality. 

![VR](https://media.giphy.com/media/26AHxbQMIf0CzRdTO/giphy.gif)
+++
GIS data are...

- **Models** for understanding the real world.
- **Structures** to facilitate knowledge
- **Links** between
    - Place/Location
	- Time (whether explicit or not)
	- Attributes/Descriptions
+++
Could these terms not be used to describe...

- Oral/written accounts?
- Paper maps? 
- Mental maps? 

What makes GIS data unique? 
+++
**Digital spatial representations**

Before we get to @fa[arrow-up], we have to answer...

- What to represent?
- How we represent it? 
    - What **conceptual model** do we adopt? 
+++
##### Conceptual models

How are geographic features distributed in the real world?

In GIS, we rely on two primary models...



@snap[south-west span-40]
@box[bg-blue text-white rounded box-padding fragment](Discrete Objects)
@snapend

@snap[south-east span-40]
@box[bg-green text-white rounded box-padding fragment](Continuous Fields)
@snapend
+++
##### Discrete Objects

Objects exist is a defined/bounded location

- Single features @fa[angle-right] points
- Connected sets of points @fa[angle-right] lines
- Lines that enclose areas @fa[angle-right] polygons
+++
@snap[north-west span-80]
![tree](images/tree.jpg) 
@css[text-black fragment](Tree: Point Feature)
@snapend

@snap[east]
@css[text-black fragment](Road: Line Feature) 
![Road](images/road.jpg)
@snapend

@snap[south-west]
![building](images/building.jpg) 
@css[text-black fragment](Building: Polygon Feature)
+++
#### But what about a mountain? 
![mountain](images/mountain.png)
+++
##### Continuous Fields

Each feature/quantity is measurable *everywhere*

- Elevation
- Population *density*
- Precipitation amount
- Percent canopy closure
+++
From Conceptual model @fa[arrow-right] Data model...

Discrete objects become...@css[fragment](*vector data*)

Continuous fields become...@css[fragment](*raster data*)
+++
@snap[west span-50]
![vector](images/vector.jpg)
@snapend

@snap[east span-50]
@box[bg-gray text-white waved box-padding](Vector Model# **Features** are stored map objects. **Feature classes** are collections of similar objects that share the geometry and attributes.)
+++
@snap[west span-50]
![attributes](images/attributes.jpg)
@snapend

@snap[east span-50]
@box[bg-gray text-white waved box-padding](Attibute Tables# Features are linked to tables containing information about the spatial objects. <br/><br/>The map object and the table data are connected by a unique integer.)
@snapend
+++
@snap[west span-50]
![raster](images/raster.jpg)
@snapend

@snap[east span-50]
@box[bg-gray text-white waved box-padding](Raster Data# The raster model breaks map areas into small squares known as cells or pixels. <br/><br/>A single numeric value is stored in each cell, such as elevation.)
@snapend
+++
##### Vector vs Raster
![Vector v Raster](images/vector-vs-raster.jpg)
---
##### Issues of representation

The real world is **infinitely complex**...

BUT, we our ability to *sample* and *store* data is **limited**. 

@css[fragment](So, what gets represented, and what gets left out?)
+++
@snap[north]
@css[text-black](Often, the **scale** of our data dictates the level of detail we can achieve)
@snapend
@snap[south]
@box[bg-gray text-white waved box-padding](Map Scale# Map scale is the ratio of distance on the map to distance on the ground. <br/><br/> It is dimensionless and can be expressed in any units: cm or inches or mm.)
+++
1 cm on map = 100,000 cm on ground

![scale](images/scale.png)
+++
**Large** scale maps have features that appear *larger* than they would in **small** scale maps.

![large v small](images/large-vs-small.jpg)
+++
##### Scale Impacts
- Generalization: Simplifying features for map display
    - Loss of detail/omission of features at **smaller** scales
    - The *Baltimore Phenomenon*

- Aggregation and MAUP
    - At what scale do features merge to become one? 
	- Where do we draw the boundaries of aggregate units?
+++
![generalize](images/generalize.jpg)
+++
![generalize 2](images/generalize2.jpg)
+++
Two representations of the same feature, at different source scales...

![scale conflict](images/scale-conflict.jpg)
+++
##### Data Quality
- No data are perfect...always a compromise
- **Quality is defined as the fitness of the data for the intended use**
    - Data that works for one problem may be unsuitable for another.
- As an GIS user, it is *your* responsibilty to determine the suitability of your data to its intended use. 
+++
##### Data Accuracy
Multiple dimensions to accuracy...

- Geometric accuracy
- Thematic accuracy
- Logical consistency
+++
##### Geometric accuracy

Is the feature where it says it is?	

- Errors from source data (GPS, image data, digitzing) can propegate during processing
- *Data validation* compares one dataset to a high accuracy reference to determine accuracy.
+++
##### Thematic accuracy

How accurate are the attributes? 

- How was it measured? 
- What was the accuracy of the measurement? 
- What sources of error were present? 
+++
##### Logical consistency

How well does the data represent the real world? 

- **Topology** @fa[arrow-right] rules that spatial data must adhere to.
- Roads must connect to ones another
- County boundaries cannot have gaps or overlaps
- City points must be contained within county polygons. 
+++
![topology](images/topology.jpg)
+++
##### Precision

**Precision** can mean one of two things in science...

@ul
- How many significant digits/decimal places in a measurement?
    - The GPS device is precise to 1-meter.
- The statistical variability of a repeated measurement.
    - 20 GPS readings of a location  have a std. dev. of 5 meters. The *precision* is ~10 meters.
@ulend
+++
##### Accuracy vs. Precision

![accuracy vs precision](images/accuracy-precision.png)
+++
##### Data Citations
**Citing data is a professional and ethical responsibility**

A good citation enables someone to find the source should they wish to obtain a copy

Formats may vary for different agencies or companies
+++
##### Citation Format

**Data set name (Year published) [source type]. Producer name, producer contact information. Resource URL: [Date accessed].**
+++
##### Citation Examples

- Black Hills RIS Vegetation Database (2008) [downloaded file]. Black Hills National Forest, Custer, SD. URL: http://www.fs.usda.gov/main/blackhills/landmanagement/gis [August, 2010].
- Esri™ Data and Maps (2012) [DVD]. Esri™, Inc., Redlands, CA.
- National Hydrography Dataset (2015) [downloaded file]. United States Geological Survey on the National Map Viewer. URL: http://viewer.nationalmap.gov/viewer/ [July 23, 2015].
- USA Topo Maps (2009) [map service]. Esri™ on ArcGIS Online. URL: http://server.arcgisonline. com/ arcgis/services/USA_Topo_Maps/MapServer [January 1, 2012].
---
### The Evolution of ArcGIS 

From ArcInfo @fa[arrow-right] ArcGIS Pro
+++
![ArcGIS History](images/arc-history.jpg)
+++
##### Software Tiers
![Tiers](images/arc-functionality.jpg)
+++
@snap[north span-80]
@css[text-black](As processing power, connection speeds, storage capacity, graphics capabilities increase, GIS software has evolved to leverage new paradigms.)
@snapend

@snap[south-west span-40]
@box[bg-blue text-white waved box-padding](Expensive memory<br/>Less disk storage<br/>Slow networks<br/>Mainframe or desktop<br/>Extensive training<br/>Data silos)
@snapend

@snap[south span-20]
@fa[arrow-right]
@snapend

@snap[south-east span-40]
@box[bg-green text-white waved box-padding](Cheap memory<br/>More disk storage<br/>Fast networks<br/>Desktop or mobile<br/>Less training<br/>Data services)
+++

@snap[west span-40]
![services](images/services.jpg)
@snapend

@snap[east span-40]
@box[bg-blue text-white waved box-padding](GIS Services# -GIS servers provide data over the Internet<br/>-Accessible to many types of platforms<br/>-Clients only consume what is needed<br/>-Possible to do real-time updates)
@snapend
+++

@snap[west span-40]
![web maps](images/web-maps.jpg)
@snapend

@snap[east span-40]
@box[bg-blue text-white waved box-padding](Web Maps# -Web maps are maps that only use GIS services<br/>-They can be shared from platform to platform<br/>-Serve as basis for complex apps)
@snapend
+++
@snap[west span-40]
![Pro GUI](images/pro-gui.jpg)
@snapend

@snap[east span-40]
@box[bg-blue text-white waved box-padding](ArcGIS Pro GUI# **Projects** contain: <br/>-Maps<br/>-Tools<br/>-Databases<br/>-Layouts<br/>-Styles<br/>-Folders<br/>-Models<br/>-Tasks<br/>-Locators)
+++
@snap[west span-40]
![Panes](images/panes.jpg)
@snapend

@snap[east span-40]
@box[bg-blue text-white waved box-padding](Panes# -Panes contain commands and settings<br/>-Movable and stackable<br/>-May have tabs and panels with more functions)
+++
@snap[west span-40]
![Contents](images/contents.jpg)
@snapend

@snap[east span-40]
@box[bg-blue text-white waved box-padding](Contents Pane# Panels of the Contents pane: <br/>-List by Drawing Order<br/>-List by Source<br/>-List by Selection<br/>-List by Editing<br/>-List by Snapping</br>List by Labeling<br/>List by Charts)
+++
@snap[west span-40]
![geoprocessing](images/geoprocessing.jpg)
@snapend

@snap[east span-40]
@box[bg-blue text-white waved box-padding](Geoprocessing Pane# The geoprocessing pane contains toolboxes and tools for added functions that extends capabilities far beyond the GUI.)
+++
@snap[west span-40]
![tool](images/tool.jpg)
@snapend

@snap[east span-40]
@box[bg-blue text-white waved box-padding](Running a tool# Icons, tabs, and menus available on tools include: <br/>1. Go back to main pane<br/>2. Options menu<br/>3. View Help<br/>4. Environments tab<br/>5. Parameter Help<br/>6. Warning<br/>7. Error<br/>8. Run)
+++
Ribbon Menus

![ribbon](images/ribbons.jpg)

Each ribbon contains buttons and functions organized into logical groups
Some ribbons are always present; others appear only when appropriate (context sensitive)










 


	



