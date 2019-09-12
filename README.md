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
* Add basic interactivity to your map 

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


## Create a web map 

Now that we have edited our layers and created a style, let's create a web map! 

For this part of the lesson, we will be using a program called JSFiddle. You can sign up for a free acount at: https://jsfiddle.net/

JSFiddle is a simple tool for building and testing code for web development. We recommend using JSFiddle in a Chrome browser

For simplicity, we recommend that you change the editor layout settings in JSFiddle to display by ‘tabs’.

Initialize your map by copying the following code into the HTML tab of your JSFiddle:

```
<!DOCTYPE html>
<html>

  <head>
    <meta charset='utf-8' />
    <title>Cholera Map</title>
    <meta name='viewport' content='initial-scale=1,maximum-scale=1,user-scalable=no' />
    <script src='https://api.tiles.mapbox.com/mapbox-gl-js/v1.3.1/mapbox-gl.js'></script>
    <link href='https://api.tiles.mapbox.com/mapbox-gl-js/v1.3.1/mapbox-gl.css' rel='stylesheet' />
    <style>
      body {
        margin: 0;
        padding: 0;
      }

      #map {
        position: absolute;
        top: 0;
        bottom: 0;
        width: 100%;
      }

    </style>
  </head>

  <body>
  </body>

</html>

```

### Add a title and info box(front-end UI):

Add the following code between the <body> opening and </body> closing tags:

```
<div id='map'></div>
<div class='map-overlay' id='features'> <h2>Broad Street, 1854</h2></div>
```

Next, you will also want to apply some CSS to visualize what the layout looks like. This creates the visual rules for our front-end elements (legend, title box, information box). Under the opening ```<style>``` tag at the top of your code, add the following: 
  
```  
h2,
h3 {
  margin: 10px;
  font-size: 1.2em;
}

h3 {
  font-size: 1em;
}

p {
  font-size: 0.85em;
  margin: 10px;
  text-align: left;
}

/**
* Set rules for how the map overlays
* information box will be displayed
* on the page. */

.map-overlay {
  position: absolute;
  bottom: 0;
  right: 0;
  background: rgba(255, 255, 255, 0.7);
  margin-right: 20px;
  font-family: Courier, sans-serif;
  overflow: auto;
  border-radius: 3px;
}

#features {
  top: 0;
  height: 200px;
  margin-top: 20px;
  width: 350px;
}



/* Styling your pop-up */
.mapboxgl-popup-close-button {
  display: none;
}

.mapboxgl-popup-content {
  font: 400 12px/20px 'Courier', Sans-serif;
  padding: 2;
  /*controling transparency and color of pop-up */
  background-color: rgba(255,255,255,.75);
}

.mapboxgl-popup-content-wrapper {
  padding: 2%;
}


```

Hit run to see your changes. 

In the next step, you will add the map to your page and the project will start taking shape.

### Initialize the map 

For the next step you will need a [Mapbox access token](https://docs.mapbox.com/help/how-mapbox-works/access-tokens/) and your [style ID](https://docs.mapbox.com/help/glossary/style-id/). Without this, the rest of the code will not work. 

For the next step you will need a [Mapbox access token](https://docs.mapbox.com/help/how-mapbox-works/access-tokens/) and your [style ID](https://docs.mapbox.com/help/glossary/style-id/). Without this, the rest of the code will not work. 

<p align = "center">
  <img src="https://github.com/mjdanielson/University-of-Buffalo/blob/master/Labs/Choropleth-Map/Images/Access_Token.png">
</p>

<p align = "center">
<img src="https://github.com/mjdanielson/University-of-Buffalo/blob/master/Labs/Choropleth-Map/Images/Style_ID.gif">
</p>

Add the following code after <div class='map-over' id='legend'></div> and before the closing </body> tag

```
<script>
mapboxgl.accessToken = 'pk.eyJ1IjoibWpkYW5pZWxzb24iLCJhIjoiY2p2bzFlbnZ5MW5pbTN5cGJ2YWp2MW9vaiJ9.kAaZq3iyJwvrMLK7XDs_qw';
var map = new mapboxgl.Map({
    container: 'map', // container id
    style: 'your-style-url', // replace this with your style URL
    center: [,], // starting position [lng, lat] - adjust the starting position to be centered on Soho, London (-0.137,  51.513) 
    zoom: 3 // starting zoom - change the starting zoom position to 15.5 
});
</script>
```

Add your style id to the map variable. Edit the line of code that has the comment 'replace this with your style URL'.

```
style: 'your-style-url', // replace this with your style URL
```

Next, we want to center our map on our data. Locate the line of code that is telling the map where to center the view. Try changing the center location by picking a new coordinate using http://geojson.io/ (or looking at the bottom of the right-hand panel in the Mapbox Studio style editor). Change the coordinates in your code and run your changes.

```
center: [,], // starting position [lng, lat] 
```

Change the zoom level to 15.5.

```
zoom: 3 // starting zoom - change the starting zoom position to 15.5
```

Hit run to see your changes. 

<p align="center">
  <img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/Map-V1.png">
  </p>

### Add additional information

With some projects, this is where you'd stop: you put a map on a page! But for this map, you will add two pieces of additional information that will make the map even more useful: an information window that gives the user a brief history of the cholera outbreak of 1854 and a pop up that displays the number of cholera deaths for whatever graduated point the cursor is hovering on.

### Add the information box 

Add the following code to your <div> element containing your map overlay class. This text should go after your 'Broad Street, 1854' header. 
  
  
```
<p>During the mid-1800’s in London, Dr. John Snow mapped all the occurrences of cholera by home address, as well as the location of public water pumps. </p>
<p>By analyzing the spatial pattern, Snow was able to determine the water pump on Broad Street was the source of the outbreak. 
</p>
```

### [The load event](https://docs.mapbox.com/help/tutorials/choropleth-studio-gl-pt-2/#the-load-event)

What is a callback?

Initializing the map on the page does more than create a container in the map div. It also tells the browser to request the Mapbox Studio style you created in part 1. This can take variable amounts of time depending on how quickly the Mapbox server can respond to that request, and everything else you're going to add in the code relies on that style being loaded onto the map. As such, it's important to make sure the style is loaded before any more code is executed.

Fortunately, the map object can tell your browser about certain events that occur when the map's state changes. One of these events is load, which is emitted when the style has been loaded onto the map. Through the map.on method, you can make sure that none of the rest of your code is executed until that event occurs by placing it in a [callback function](https://github.com/maxogden/art-of-node#callbacks) that is called when the load event occurs.

To make sure the rest of the code can execute, it needs to live in a callback function that is executed when the map is finished loading.

Add the load event before the closing script tag </script>

```
map.on('load', function() {
  // the rest of the code will go in here
});
```


### Add a popup! 

When the cursor is hovering over a graduate point a popup will display the number of cholera related deaths recorded in that region. 

To do this, add a listener for the mousemove event, identify which graduated point is at the location of the cursor if any, and create a popup:

```
var features = map.queryRenderedFeatures(e.point, {
    layers: ['Cholera Deaths'] // replace this with the name of the layer
  });
  
  if (!features.length) {
    return;
  }
  var feature = features[0];

});


//initialize popup 

var popup = new mapboxgl.Popup({ 
		closeButton: false,
                closeOnClick: true,
});

 // When a click event occurs on a feature in the Cholera Deaths layer, open a popup at the
// location of the click, with description HTML from its properties.

map.on('mouseenter', 'Cholera Deaths', function (e) {
//change the cursor style as a UI indicator
map.getCanvas().style.cursor = 'pointer';

// Create variables for your tabular information 
var aggregate = e.features[0].properties.Deaths;

// Populate the popup and set its coordinates
// based on the feature found.
popup.setLngLat(e.lngLat)
.setHTML(aggregate)
.addTo(map);
});

 
// Change it back to a pointer when it leaves.
map.on('mouseleave', 'Cholera Deaths', function () {
map.getCanvas().style.cursor = '';

```


### Mission Complete!

You have successfully recreated John Snow's famous map! Congratulations and happy GIS day! The final map can be accessed [here](https://mjdanielson.github.io/Cholera-Map/). 


<p align="center">
	<img src="https://github.com/mjdanielson/Cholera-Map/blob/master/Images/Final.png">
	</p>
