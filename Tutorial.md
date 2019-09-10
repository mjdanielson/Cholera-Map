<img src="https://github.com/mjdanielson/University-of-Buffalo/blob/master/Labs/Choropleth-Map/Images/Logo.png">


<h1 align="center"> Happy GIS Day! </h1>


In celebration of GIS Day, we thought it would be fun to recreate John Snow's 1854 map of cholera outbreaks in London using Mapbox Studio and GL-JS!

<p align="center">
  <img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/broad-street-pump2.jpg">
  </p>

<p align="center"> <i> 1854 London cholera outbreak </i> </p>

<h2 align="center"> <strong> Who is John Snow you ask? </strong></h2>

<p align="center">
<img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/Dr_John_Snow.jpg"> 
</p> 


Dr. John Snow is considered one of the fathers of modern epidemiology, in part because of his pioneering work during the 1854 London cholera outbreak. During the mid-1800’s the prevailing theory was that these outbreaks were caused by miasma (the spread of disease in the air due to decomposing particles). However, Snow was skeptical and mapped all the occurrences of cholera by home address (marked by the stacked black bars) as well as the location of public water pumps. By analyzing the spatial pattern, Snow was able to determine the water pump on Broad Street was the source of the outbreak.


<h1 align="center"> Mapping the 1854 London cholera outbreak tutorial</h1>

In this tutorial you will:

* Upload data as a tileset
* [Create a style](https://docs.mapbox.com/help/how-mapbox-works/map-design/#how-map-styles-work) for a basemap using [Cartogram](https://apps.mapbox.com/cartogram/#13.01/40.7251/-74.0051)
* [Add data](https://www.mapbox.com/help/uploads/) to a style
* [Manage and edit layers](https://www.mapbox.com/studio-manual/reference/styles/#style-editor) in your style
* Create a web map 
* Adding a legend 
* Adding basic interactivity to your map 

## Software requirements

* Mapbox account
* JSFiddle 

## Data

* [Cholera deaths](https://github.com/mjdanielson/Cholera-Map/blob/master/Data/Cholera_Deaths.geojson): Number of deaths attributed to cholera in 1854 by location. 

* [Location of pumps](https://github.com/mjdanielson/Cholera-Map/blob/master/Data/Cholera_Pumps.geojson)

## Upload data as a tileset

Let's upload our data to the [tileset editor](https://studio.mapbox.com/tilesets/).  At the top of the tileset editor page, select
  <img src="https://github.com/mjdanielson/University-of-Buffalo/blob/master/Labs/Choropleth-Map/Images/Tileset.png" title="Tileset Upload">. Select __Upload File__ and __Select a file__ and navigate to the file containing your census data tracts GeoJSON and select __Confirm__. 

  <p align= 'center'>
  <img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/Screen%20Shot%202019-09-05%20at%204.11.18%20PM.png" title="Tileset1">
  </p>

When you upload vector data to your Mapbox account, our servers convert it to a [vector tileset](https://docs.mapbox.com/help/glossary/tileset/) so it can be rendered quickly and efficiently in the Mapbox Studio style editor and with Mapbox GL JS. The tileset information page shows some useful information about the tileset that was created from your uploaded data. Feel free to explore the information page for each of your new tilesets. 

Upload the Cholera_Pump.geojson as a tileset. 


## Create a style for a basemap using Cartogram 
  
After you've inspected your data, it's time to create a new style so you can put it on the map! Go to the [Cartogram homepage](https://apps.mapbox.com/cartogram/#13.01/40.7251/-74.0051). Find a picture of John Snow's Broad Street Map that you like and upload to Cartogram. For this tutorial, we will be using the image below. 

<p align="center">
  <img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/broadstreet(source13)-large.jpg" width="500" height="474" title="Broad Street Pump"> 
</p>

Once you've uploaded your photo to Cartogram, start playing around with the settings for your buildings, land, font, and streets until you have your desired basemap style. 


<p align="center">
  <img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/cartogram.gif" width="576" height="261.6">
  </p>
   
 
When you've finished, select <img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/saved_style.png" width="148" height="20"> at the top of the screen. This should automatically take you to the Mapbox Studio editor. 

In the style editor, change the rename your Style. In this example, the Style name has been changed to 'John Snow Cholera'. 

<p align="center">
  <img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/Style_Name.png">
  </p>

### [Add data](https://www.mapbox.com/help/uploads/) to a style

To add and style the Cholera deaths data, you will need to add a new layer to the map. At the top of the layer panel, click <img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/Add_Layer.png">

<p align="center">
  <img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/Add_Layer.gif">
  </p>

The editor is now showing your map in “x-ray mode.” X-ray mode shows all the data in the sources added to the style, regardless of whether there is a layer to style it.

In the New layer panel, look in the list of Data sources for the Cholera Deaths source. Click the tileset and then select the source layer as the source for this new style layer.

The default Basic map view is not centered on London, England. Mapbox Studio recognizes that the data you have uploaded is focused on a different location, so it displays the message "This tileset isn't available from your map view." Click Go to data, and the map view will refocus on the United States. Zoom to your layer (London, England).

Each layer in Studio can be styled individually by clicking on the name of the layer in the Layer list. There are several layer types to choose from. Each layer type has a unique set of layer properties that can be specified. There are a few options for specifying property values. You can pick values individually, based on a data attribute, based on the zoom level, or the value of another property. For more information on layer types and their styling rules check out this [reference guide](https://docs.mapbox.com/studio-manual/reference/styles/).

## [Manage and edit layers](https://www.mapbox.com/studio-manual/reference/styles/#style-editor) in your style

Click the Style tab and the map will switch back to style mode displaying your new layer. You will see the point data on the map with a default style (black with 100% opacity). 

In the Mapbox Studio style editor, you create graduated points based on the number of cholera deaths by increasing or decreasing the radius size of the points. Change the name of your data layer to 'Cholera Death' and select __radius__ ,  __style across a data range__ and then select the __Deaths #__ field.

<p align = "center">
  <img src= "https://github.com/mjdanielson/Cholera-Map/blob/master/Images/Style_Radius.gif">
</p>


The rate of change should be set to __Linear__.

Now it's time to start adding stops! You will create several stops to break the cholera death data up into groups. We will be breaking the data out into 5 classes.

<p align = "center">
  <img src ="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/Cholera_Deaths_1.png">
  </p>
  
Once you've finished creating your graduated points, add the Cholera Pumps data to the map twice. Rename one layer 'Pumps' and the other 'Pumps Outline'.

Change the radius of the 'Pumps' layer to 4 and change the color to #7f0101. 

<p align = "center">
  <img src ="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/Pumps_Layer.png">
  </p>
  
Next, increase the radius of the 'Pumps Outline' layer to 6, change the color to #000000 and the stroke color to #7f0101. 

<p align = "center">
  <img src ="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/Pumps_Outline.png">
  </p>
  



  
## Publish your style 

Now that you've got your map looking good, it's time to publish! Click the Publish style button at the top of the toolbar on the right side of the screen, then click Publish again on the next prompt.

Hooray! Your style is now published! If you go back to your Styles page, you will see your new style at the top of the list.

You can use your ‘Share URL’ to open your style in a new browser tab and share it with collaborators for review.
  


