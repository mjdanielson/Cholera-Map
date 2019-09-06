<img src="https://github.com/mjdanielson/University-of-Buffalo/blob/master/Labs/Choropleth-Map/Images/Logo.png">


<h1 align="center"> Happy GIS Day! </h1>


In celebration of GIS Day, we thought it would be fun to recreate John Snow's map of 1894 map of cholera outbreaks in London using Mapbox Studio and GL-JS!

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

Once you've uploaded your photo to Cartogram, start playing around with the settings for your buildings, land, font, and streets until you have your desired basemap style. When you've finished, select <img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/saved_style.png" width="148" height="20"> at the top of the screen. This should automatically take you to the Mapbox Studio editor. 

<p align="center">
  <img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/cartogram.gif">
  </p>
