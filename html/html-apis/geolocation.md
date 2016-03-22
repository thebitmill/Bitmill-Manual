# Geolocation API

The geolocation api provides a way for developers to access the position of a
device. It is highly relevant in mobile development since it enables websites
to provide content based on location. Nearby open pizza places, sightseeing
stops, ATMs all became possible to provide via the web instead of apps with the
Geolocation api. Other uses, such as automatically filling in position on a
weather website, or connecting nearby people in a web game are also possible.

Using the Geolocation API is as simple as:

```
if (navigator.geolocation) {
	navigator.geolocation.getCurrentPosition(function (position) {
			console.log("Postion: ", position)
		}, function(error) {
			console.log("Error: ", error)
		});
} else {
	console.log('Error: Geolocation not supported');
}
```

See Also (TODO ensure these are still relevant)

+ [W3Schools: Geolocation](http://www.w3schools.com/html/html5_geolocation.asp)
+ [HTML5Rocks: Using Geolocation API to create a trip meter](http://www.html5rocks.com/en/tutorials/geolocation/trip_meter/)
+ [HTML5Demos: Geolocation](http://html5demos.com/geo)
+ [HTML5Rocks Playground: Get Current Position](http://playground.html5rocks.com/#get_current_position)
