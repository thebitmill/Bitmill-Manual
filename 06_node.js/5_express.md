# Express

## HTTP Module & Why We Have Express

Node.js has a native module called http with which one can immediately create a
simple web server. Express uses the native Node module http to easily set up 

```js
var http = require("http");
var server = http.createServer(function(request, response) {
  response.writeHead(200, {"Content-Type": "text/html"});
  response.write("<h1>Fuck You World!</h1>");
  response.write("<h2>Who do you think you are?</h2>");
  response.end();
});
server.listen(80);
console.log("Server is listening");
```

However, that quickly becomes cumbersome. Instead, today we have Express which
has intelligently repackaged the whole http module and implemented so called
middlewar

## Background

Express has evolved from something that was (or maybe still is) called Connect.
Connect and Express both essentially set up all the basic tools needed to
server content according to the HTTP protocol. It is extremely beneficial to
take some time to learn the HTTP protocol properly. It is a very small protocol
definition, so one can quickly skim through it to get a general idea. Once you
start learning Express and come across references to the protocol that seem
alient, simply go back and relearn.


## Request & Response

The request and response are what gets sent to and returned from the HTTP
server respectively. Make sure you have read both sections 5 and 6 of the
HTTP:/1.1 protocol.

## Middleware

A middleware is in all it's simplicity merely a function. Each route (such as
'/', '/contact', or '/user-profile/bert') will have at least one middleware
function associated with it. A middleware function that is called will always
be passed 3 parameters: the request object, the response object, and a special
next function).

Middleware functions are NOT pure. They alter their arguments, namely the
response.

TODO check if the following link is still relevant to our interests.

+ <https://blog.safaribooksonline.com/2014/03/10/express-js-middleware-demystified/>

## Routing

+ <https://scotch.io/tutorials/learn-to-use-the-new-router-in-expressjs-4>

## Templating

Du kommer snabbt märka att du behöver göra ett val av "templating engine". Vi
använder för närvarande Dust.js, men kommer sannolikt att byta till Marko rätt
snart. Eftersom Marko är rätt nytt kan det vara dåligt med dokumentation.
Handlebars är nog det mest populära alternativet. Så kör Marko, Handlebars
eller Dust.

### Dust.js

I realised i forgot to mention which templating system we use, which is Dust
and we use it both server and client side. <http://www.dustjs.com/> is a pretty
good resource to get the basics, but it is far more powerful than the
documentation might suggest. We do not use the dustjs-helpers package available
in the NPM registry, but have rather begun creating our own package at
<https://github.com/thecodebureau/sprinkles>.
