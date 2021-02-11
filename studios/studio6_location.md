# Location and Mapping

Mapping - like critical or counter mapping - and location are a crucial part of digital activism, and have long been central to activist movements. This ranges from the live-time use of bluetooth and proximity in the HK Umbrella movements, to anti-kettling protest apps like Sukey to broader critical mapping projects like Ushahidi or the SF-based Anti-Eviction project.

See more examples here (there are sooooo many!):
- https://www.ushahidi.com
-https://www.aaas.org/programs/scientific-responsibility-human-rights-law/geospatial-technologies-and-human-rights-zimbabwe
-https://gentrificationproject.lib.miamioh.edu/home/
-https://www.scmp.com/news/hong-kong/article/1659236/mapping-out-protest-sites-history
-https://stlaw.maps.arcgis.com/apps/MapTour/index.html?appid=f7cdf93edd0b4079a379f9f6aba6c547
-https://sukey.org


But maps and location are pretty rigid in their thinking: they work off a limited number of ways of understanding where we are and what is happening: lists of places and place names (UC Berkeley, Safeway); addresses and numbering systems (4595 Telegraph Ave); and, universal coordinate systems (37.05, -122.97).

In this workshop, based off another from my Locative Media class, we're going to explore the basics of location and web mapping. For a more detailed tutorial, see: https://clancy-wilmott.gitbook.io/locative-media/lab-3-web-mapping/what-is-web-mapping

## Sign up for Mapbox

Go to https://www.mapbox.com . Sign up for a free account, if you haven't already!

> **Mapbox Studio**
>
>Mapbox Studio is not a total web mapping program, like ArcGIS or CartoDB. Instead, what it offers is a base map, a place to put datasets and a number of APIs which allow its geographic capacities to speak to your web or mobile applications. This means that unlike traditional GIS programs, you can't just drop your data onto a map and have it displayed automatically. Instead, you need to make your base map and clean your data
Mapbox Studio has three main sections: Styles, Tilesets and Datasets. Styles allows you to customise your base map. Tilesets turns your geographic data into square tileset. Datasets is a place to hold your geodata.

![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MA1ZLWfS6tOE920_V26%2F-MA1h6ZABsFfUUX9psh4%2Fimage.png?alt=media&token=2b7077a0-6dce-4041-9a20-bff8cd89e76c)

On the front **Account** page, you will have an Access Token - don't forget where this is! You'll need it!

## Make a HTML Document

Open Atom on your computer.

Select File-->New File to open a new file. Then select File-->Save As.

Name it `studio5.html`

Now, copy and paste the code below into your index.html file (you'll remember that this is the basic structure of a html file):
```html
<!DOCTYPE html>
<!--This is how you comment for html-->
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8">
    <title> My Map </title>
    <!--This where you put all your dependencies-->
  </head>
  <body>
    <p> Hello World </p>
  </body>
</html>
```
Check it worked by going to **Packages-->Preview HTML-->Enable Preview**.

![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MAH9VxKlyV8sEFsLeN1%2F-MAHHOJNt4U_q3Gp8UHf%2FScreen%20Shot%202020-06-20%20at%2016.11.51.png?alt=media&token=c7b7a469-9c1d-47a1-9fc1-0be06d8a3da5)

## Add a Map!

Now we need to add a map using the Mapbox GL JS library, which is a JavaScript library that acts as a translator between our code and Mapbox! To do this, we need three things:
1. a link in the `<head>` to the Mapbox GL JS library dependencies so our code knows where to find them
2. a html "box" or `<div>` in the `<body>` where the map will go.
3. a javascript `<script>` section in the `<body>` which will link to our access token and set up our map.

#### 1. Add Dependencies

Copy and paste the below into the `<head>` section:

``` html
<script src='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.js'></script>
<link href='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.css' rel='stylesheet' />
```

Well done! Now your code should look something like this:
``` html
<!DOCTYPE html>
<!--This is how you comment for html-->
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8">
    <title> My Map </title>
    <!--This where you put all your dependencies-->
    <script src='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.js'></script>
    <link href='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.css' rel='stylesheet' />
  </head>
  <body>
    <p> Hello World </p>
  </body>
</html>
```

#### 2. Create a map `<div>`

Delete the "Hello World" `<p>` tag. Then, copy and paste the below `<div>` into the `<body>` section:
``` html
<div id='map'></div>
```
Now, let's add some CSS to the `<head>` with a `<style>` tag to style it:
``` html
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
```
This width is set to "100%" of the page width, whatever that might be. If you wanted a smaller map, you could style it with, for example, `width: 400px; height: 300px;`

Excellent. You should now have a blank page, because we haven't put anything in our map <div> yet!

#### 3. Bring in your JS map!

Now, in the `<body>` section, let's bring in our map. To do this, create a `<script>` section under your `<div>`:
``` js
<script>

//variables (var) up the top

// map.on(functions) at the bottom!


</script>
```
I've created two comments in the script, to help us navigate the two main ways in which we will use Java (and the order is important!).
- `var` is a way of setting up a variable - or the thing that we want to effect or use.
- `x.on(load, move, open)` are triggers to make something happen!

Now, paste the following into `<script>` tag:

``` js
mapboxgl.accessToken = 'YOUR_ACCESS_TOKEN'; // Add your access token here
// Below, we set up a 'map' variable which is a new map, with a standard style
```
Replace 'YOUR_ACCESS_TOKEN' with uour access token! Head back to **mapbox.com** and copy your Access Token:

![](https://gblobscdn.gitbook.com/assets%2F-M9O5Xh6H5-Kcfi8ek2i%2F-MAH9VxKlyV8sEFsLeN1%2F-MAHBOhuuO39iJlovZj5%2Fimage.png?alt=media&token=d8ba61f3-79da-45a8-b7f8-8c3ffffc93fd)

Then, paste it into the section that says `'YOUR_ACCESS_TOKEN'` so that the line looks like this:
```js
mapboxgl.accessToken = 'pk.eyJ1IjoiY2xhbmN5d2lsbW90dCIsImEiOiJjandmY3Ryc2MxaThkNDBtZ2dmcG9zOWJzIn0.wLqA-pIsMZcIl5uUgb49-Q';
```

Now, below that in `<script>`, let's set up our first `var`:
``` js
var map = new mapboxgl.Map({
  container: 'map', // container id
  style: 'mapbox://styles/mapbox/light-v10', // stylesheet location
  center: [-122.25, 37.87], // starting position
  zoom: 12 // starting zoom
});
```

Your code should now look something like this:
```html
<!DOCTYPE html>
<!--This is how you comment for html-->
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8">
  <title> My Map </title>
    <!--This where you put all your dependencies-->
    <script src='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.js'></script>
    <link href='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.css' rel='stylesheet' />
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
    <div id='map'></div>
    <script>
    mapboxgl.accessToken = 'pk.eyJ1IjoiY2xhbmN5d2lsbW90dCIsImEiOiJjandmY3Ryc2MxaThkNDBtZ2dmcG9zOWJzIn0.wLqA-pIsMZcIl5uUgb49-Q';
    //variables (var) up the top
    var map = new mapboxgl.Map({
      container: 'map', // container id
      style: 'mapbox://styles/mapbox/light-v10', // stylesheet location
      center: [-122.25, 37.87], // starting position
      zoom: 12 // starting zoom
    });
    // map.on(functions) at the bottom!


    </script>
  </body>
</html>

```

## 3. Centre Your Map on You!

Your map probably shows UC Berkeley, which would be fine, if we were all there, but we aren't.

#### Fixed Centre
An easy way to change it is by going to https://gps-coordinates.org/where-am-i.php and changing the `center: [-122.25, 37.87]` coordinates to your own. Remember, the formula is `center: [lon, lat]`

#### Dynamic Geolocation Fanciness!

So let's use the GL JS "geolocate" function to go automatically to where we are, and move the map if we move (like if we were on a phone!).

Geolocation has two sections. Let's start by setting up a variable.
In your `<script>` section, under your `var = map` variable, create this below by copying and pasting:
```js
var geolocate = new mapboxgl.GeolocateControl({
  positionOptions: {
    enableHighAccuracy: true
  },
  trackUserLocation: true
});
```
Now, a little more complicated, we need to set up a few map.on(functions) to set up triggers to make our variable work!

First, let's add the geolocate control to the map, by putting the below in your function section of your `<script>` tag:
```js
map.addControl(geolocate);
```
Next, let's make a map.on(function), to start the geolocation when the map loads:
``` js
map.on('load', function() {
  geolocate.trigger();
});
```
Your code should look something like this:
``` html
<!DOCTYPE html>
<!--This is how you comment for html-->
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8">
  <title> My Map </title>
    <!--This where you put all your dependencies-->
    <script src='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.js'></script>
    <link href='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.css' rel='stylesheet' />
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
    <div id='map'></div>
    <script>
    mapboxgl.accessToken = 'pk.eyJ1IjoiY2xhbmN5d2lsbW90dCIsImEiOiJjandmY3Ryc2MxaThkNDBtZ2dmcG9zOWJzIn0.wLqA-pIsMZcIl5uUgb49-Q';
    //variables (var) up the top
    var map = new mapboxgl.Map({
      container: 'map', // container id
      style: 'mapbox://styles/mapbox/light-v10', // stylesheet location
      center: [-122.25, 37.87],
      zoom: 12 // starting zoom
    });
    var geolocate = new mapboxgl.GeolocateControl({
      positionOptions: {
        enableHighAccuracy: true
      },
      trackUserLocation: true
    });
    // map.on(functions) at the bottom!
    map.addControl(geolocate);
    map.on('load', function() {
      geolocate.trigger();
    });
    </script>
  </body>
</html>

```
Nothing will happen. This is fine! Our `center: [-122.25, 37.87],` is overriding the geolocation, which is good for now, because we need it (and once geolocation works, the map freaks out and you can't see it in Preview HTML). We'll delete it at the end, once we've done the next bit!

## 4. Add Data

Let's add some data. Let's make some data. Geodata comes in many forms - we've already seen it as CSV in spreadsheets, it can be in panda form as geopandas for python, but since we're scripting in JavaScript, we should use a js data format. The most common js data format is JSON, which stands for JavaScript Object Notation. We're using the geographic add-on, which is called, you guessed it, geoJSON.

Go to http://geojson.io/ and navigate to near whereever you are.

#### 1. Create Points
Using the little marker button on the top right, drop some markers down. If you look to the right, you'll see the website automatically formatting the geoJSON out for you (this is wonderful).

#### 2. Add Data
But, what is a point without context? If you go to the "table" tab (oh yes, tables!), you can add a new column. Create one, call it "Title" and fill in the rows.

#### 3. Tidy the quotation marks.
Our Java uses single quotations and their formatting uses double. So, we need to beautify.

Go to https://csvjson.com/json_beautifier and copy and paste your geojson from geojson.io into the left section.  On the options side, select SINGLE quotes and "No Quotes" "On Keys". Then select "Beautify"

You should now have some pretty nice data that looks like this

``` js
{
  type: 'FeatureCollection',
  features: [
    {
      type: 'Feature',
      properties: {
        Title: 'San Pablo Creek'
      },
      geometry: {
        type: 'Point',
        coordinates: [
          -122.23371505737305,
          37.9192844858339
        ]
      }
    },
    {
      type: 'Feature',
      properties: {
        Title: 'Briones Reservoir'
      },
      geometry: {
        type: 'Point',
        coordinates: [
          -122.18461990356444,
          37.92321155405647
        ]
      }
    },
    {
      type: 'Feature',
      properties: {
        Title: 'Lafayette Reservoir'
      },
      geometry: {
        type: 'Point',
        coordinates: [
          -122.13809967041017,
          37.88325400922058
        ]
      }
    }
  ]
}
```
#### 4. Set up a variable for our geoJSON

Now, let's set up a variable for our geoJSON data. In the variables section, create a variable:
``` js
var geojson = // paste geojson here
;
```
and then paste in your geojson so it looks like this:
``` js
var geojson = {
  type: 'FeatureCollection',
  features: [
    {
      type: 'Feature',
      properties: {
        Title: 'San Pablo Creek'
      },
      geometry: {
        type: 'Point',
        coordinates: [
          -122.23371505737305,
          37.9192844858339
        ]
      }
    },
    {
      type: 'Feature',
      properties: {
        Title: 'Briones Reservoir'
      },
      geometry: {
        type: 'Point',
        coordinates: [
          -122.18461990356444,
          37.92321155405647
        ]
      }
    },
    {
      type: 'Feature',
      properties: {
        Title: 'Lafayette Reservoir'
      },
      geometry: {
        type: 'Point',
        coordinates: [
          -122.13809967041017,
          37.88325400922058
        ]
      }
    }
  ]
};
```
Your entire code should look like this:
``` js
<!DOCTYPE html>
<!--This is how you comment for html-->
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8">
  <title> My Map </title>
    <!--This where you put all your dependencies-->
    <script src='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.js'></script>
    <link href='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.css' rel='stylesheet' />
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
    <div id='map'></div>
    <script>
    mapboxgl.accessToken = 'pk.eyJ1IjoiY2xhbmN5d2lsbW90dCIsImEiOiJjandmY3Ryc2MxaThkNDBtZ2dmcG9zOWJzIn0.wLqA-pIsMZcIl5uUgb49-Q';
    //variables (var) up the top
    var map = new mapboxgl.Map({
      container: 'map', // container id
      style: 'mapbox://styles/mapbox/light-v10', // stylesheet location
      center: [-122.25, 37.87],
      zoom: 12 // starting zoom
    });
    var geolocate = new mapboxgl.GeolocateControl({
      positionOptions: {
        enableHighAccuracy: true
      },
      trackUserLocation: true
    });
    var geojson = {
      type: 'FeatureCollection',
      features: [
        {
          type: 'Feature',
          properties: {
            Title: 'San Pablo Creek'
          },
          geometry: {
            type: 'Point',
            coordinates: [
              -122.23371505737305,
              37.9192844858339
            ]
          }
        },
        {
          type: 'Feature',
          properties: {
            Title: 'Briones Reservoir'
          },
          geometry: {
            type: 'Point',
            coordinates: [
              -122.18461990356444,
              37.92321155405647
            ]
          }
        },
        {
          type: 'Feature',
          properties: {
            Title: 'Lafayette Reservoir'
          },
          geometry: {
            type: 'Point',
            coordinates: [
              -122.13809967041017,
              37.88325400922058
            ]
          }
        }
      ]
    };
    // map.on(functions) at the bottom!
    map.addControl(geolocate);
    map.on('load', function() {
      geolocate.trigger();
    });
    </script>
  </body>
</html>
```
#### 5. Add markers
Now, we need to attach some markers to the coordinates in the geoJSON. We want these markers to appear as a layer when the map loads, so we are going to put them inside the `map.on('load'...` function under `geolocate.trigger()`. Here is our code:
```js
map.addLayer({
  id: 'geojson',
  type: 'symbol',
  source: {
    type: 'geojson',
    data: geojson
  },
  layout: {
    'icon-image': 'park-15', // more icons here: https://labs.mapbox.com/maki-icons/editor/
    'icon-allow-overlap': true
  },
  paint: { }
})
```
You should have some little tree markers on your map. You can change these using the Maki icons in the comments.

#### 6. Add pop-ups

Finally, markers are nice, but we don't know what they mean! So, let's end by adding a pop-up which displays our title information. Same as usual, we require a `var` and some `function` action.

Set up your variable by adding the below code to your variable section. Mapbox has a handy prebuilt pop-up so we don't need to style it:
``` js
var popup = new mapboxgl.Popup();
```
Next, let's use a more complicated function to trigger our pop-ups. This function basically, whenever the mouse moves, searches the layer with our markers, when it finds one, searches for its feature details, uses them to build a pop-up, and then plants it at the those coordinates (slightly offset).

At the bottom on the `function` section, copy and paste the below code:

``` js
map.on('mousemove', function(e) {
  var features = map.queryRenderedFeatures(e.point, { layers: ['geojson'] });
  if (!features.length) {
    popup.remove();
    return;
  }
  var feature = features[0];

  popup.setLngLat(feature.geometry.coordinates)
  .setHTML(feature.properties.Title)
  .addTo(map);

});
```
Your complete code should look like this:
``` js
<!DOCTYPE html>
<!--This is how you comment for html-->
<html lang="en" dir="ltr">
<head>
  <meta charset="utf-8">
  <title> My Map </title>
    <!--This where you put all your dependencies-->
    <script src='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.js'></script>
    <link href='https://api.mapbox.com/mapbox-gl-js/v1.11.0/mapbox-gl.css' rel='stylesheet' />
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
    <div id='map'></div>
    <script>
    mapboxgl.accessToken = 'pk.eyJ1IjoiY2xhbmN5d2lsbW90dCIsImEiOiJjandmY3Ryc2MxaThkNDBtZ2dmcG9zOWJzIn0.wLqA-pIsMZcIl5uUgb49-Q';
    //variables (var) up the top
    var map = new mapboxgl.Map({
      container: 'map', // container id
      style: 'mapbox://styles/mapbox/light-v10', // stylesheet location
      center: [-122.25, 37.87],
      zoom: 12 // starting zoom
    });
    var geolocate = new mapboxgl.GeolocateControl({
      positionOptions: {
        enableHighAccuracy: true
      },
      trackUserLocation: true
    });
    var geojson = {
      type: 'FeatureCollection',
      features: [
        {
          type: 'Feature',
          properties: {
            Title: 'San Pablo Creek'
          },
          geometry: {
            type: 'Point',
            coordinates: [
              -122.23371505737305,
              37.9192844858339
            ]
          }
        },
        {
          type: 'Feature',
          properties: {
            Title: 'Briones Reservoir'
          },
          geometry: {
            type: 'Point',
            coordinates: [
              -122.18461990356444,
              37.92321155405647
            ]
          }
        },
        {
          type: 'Feature',
          properties: {
            Title: 'Lafayette Reservoir'
          },
          geometry: {
            type: 'Point',
            coordinates: [
              -122.13809967041017,
              37.88325400922058
            ]
          }
        }
      ]
    };
    var popup = new mapboxgl.Popup();
    // map.on(functions) at the bottom!
    map.addControl(geolocate);
    map.on('load', function() {
      geolocate.trigger();
      map.addLayer({
        id: 'geojson',
        type: 'symbol',
        source: {
          type: 'geojson',
          data: geojson
        },
        layout: {
          'icon-image': 'park-15', // more icons here: https://labs.mapbox.com/maki-icons/editor/
          'icon-allow-overlap': true
        },
        paint: { }
      })
    });
    map.on('mousemove', function(e) {
      var features = map.queryRenderedFeatures(e.point, { layers: ['geojson'] });
      if (!features.length) {
        popup.remove();
        return;
      }
      var feature = features[0];

      popup.setLngLat(feature.geometry.coordinates)
      .setHTML(feature.properties.Title)
      .addTo(map);
    });
    </script>
  </body>
</html>

```
## 5. Delete Fixed Centre!

Finally, delete `center: [-122.25, 37.87],`, watch your map freak out, and then try opening your map.html file in your Chrome browser! :-) :-) :-)
