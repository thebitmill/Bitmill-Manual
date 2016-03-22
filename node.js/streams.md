# Streams

A very important concept to grasp is Streams. Everything in Node is essentially Streams. Learn to master them, and you master
the core of Node.

+ <https://github.com/substack/stream-handbook>


## Streams1 vs Streams2 vs Streams3

+ <https://strongloop.com/strongblog/whats-new-io-js-beta-streams3/>
+ <http://stackoverflow.com/questions/21538812/what-is-streams3-in-node-js-and-how-does-it-differ-from-streams2>

## Everything is A Stream

Even the front end. EDIT: Maybe this section should be somwehre else.

![Everything is A Stream](https://camo.githubusercontent.com/e581baffb3db3e4f749350326af32de8d5ba4363/687474703a2f2f692e696d6775722e636f6d2f4149696d5138432e6a7067)

+ [The introduction to Reactive Programming you've been missing](https://gist.github.com/staltz/868e7e9bc2a7b8c1f754) (by Andrew Stalzt, created of Cycle.js)


### NOT SURE WHAT THIS IS SHOULD BE HERE OR IN WEB AUDIO, THINK ROBIN WROTE IT

####Introduction

Streams are essentially data channels, simplex or duplex (single- or
bidirectional) coupled with events to notify the program about when there is a
readable chunk of data ('readable' event) or simply deliver the data along with
the event ('data' event). Other, pretty self explanatory events include 'end',
'error', and 'close'. A stream object also contains functions to control and
check behaviors like encoding type, data chunk size. 

#### Example use case

A readable stream can be piped into a writable stream so that once a data chunk
is processed it is instantly passed to  the next stream in the chain. This way
data can be processed and even sent back to a client before an entire 'object',
whatever it might be, has been received. Consider a remote server providing
transcoding of music (eg .wav to .mp3). The client starts uploading the raw
.wav file. This stream is received and piped into a stream that transcodes the
audio to mp3 on the fly (this is possible, since only a small chunk of sound is
needed at a time when transcoding), which is then piped back to the client. On
the client side, this stream is received and piped right to an <audio> element
(an audioContext, NOT SURE ABOUT TERMINOLOGY HERE!!!) and played back to
through the clients speakers. Doing the same thing but uploading the entire
file first, then transcoding, and finally downloading would take approx. twice
as long assuming that up/down bandwidth is equal and neglecting transcoding
time, ping. 
