
# Canvas API

Basically all realtime games, and even more graphically advanced turnbasedones
will be made using the awesome Canvas API. Certain javascriptlibraries like
Raphael.js use Canvas API to draw vectors.

## Canvas vs. SVG

In many occasions one has to decide whether to use SVG or Canvas. They can
often be used to achieve the same thing, but have very different usages. With
SVG it is very easy to attach events to different objects, but animating large
SVG sections is painfully slow.

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

# Storage API

Frikkin awesome, offline games and apps made playfully easy. The Storage API
enables local storage on the client of up to 4mb per website.

# WebSockets

The possibilities are endless! This is going to be usedfor multi player in
games, communication channels etc.

# Web Workers API

The web workers API brings multi-threading to the web. Modern CPUs are
comprised of a processor cluster, usually 4-8 cores in one. One core can only
run one "thread" which is analogous to a string of instructions, executed one
by one and in succession. Many tasks that a computer preforms can be divided
such that they can be delegated to multiple processing facilities (in our case
cores) and those facilities can do their work without knowing anything about
what the other cores/processors are doing. This is called having a
paralellizable problem, and is the arena where web workers shine. Many, if not
most, computationally heavy problems are paralellizable which makes web workers
ideal for more advanced web games and applications such as 3D animation, video
processing, image manipulation and so on.

+ <http://www.html5rocks.com/en/tutorials/workers/basics/>

# Web Audio API

The Web Audio API exposes recording and playback hardware in a way that is safe
for the web, i.e the user has to confirm that they allow the hardware to be
used. The hardware can then be manipulated by javascript in the form of a
stream or passed straight to an <audio> element.

## AudioContext

An audio context is more or less the software equivalent of a mixer combined
with sound effect boxes. It routes sound from a hardware input or software
source through any number of intermediate nodes or "processors" connected in
parallel or serial configurations. 

## AudioNodes

The AudioNodes are the fundamental parts of any Web Audio app, they provide
hardware inputs, sources ("playing" an audio file from a stand-alone node
acting like an input), effects, Fourier transforms, volume control and for
anything not covered by a default node type there is the ScriptProcessor node
that allows developers to create their own nodes using JavaScript.

Nodes have inputs and outputs, just like a regular hardware effects box would
and function in much the same way. 

### Example Configuration of Nodes

![An example configuration of nodes](http://i.imgur.com/7dpmm44.png)

## Read More

+ [Full W3 WebAudio Spec](http://www.w3.org/TR/webaudio/)
+ [W3 WebAudio Spec, AudioNode Section](http://www.w3.org/TR/webaudio/#AudioNode-section)
+ [W3 WebAudio Spec, AudioContext Section](http://www.w3.org/TR/webaudio/#AudioContext-section)
+ [HTML5 Rocks: Getting Started With Web Audio](http://www.html5rocks.com/en/tutorials/webaudio/intro/)
+ [HTML5 Rocks: Quick Guide To The Audio Element](http://www.html5rocks.com/en/tutorials/audio/quick/)
+ [MDN: Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
+ [MDN: Audio Element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)
+ [W3Schools: Audio Element](http://www.w3schools.com/tags/tag_audio.asp)
