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
