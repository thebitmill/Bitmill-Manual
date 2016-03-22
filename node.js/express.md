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

## HTTP Protocol

Below are some references I still regularly return to to brush up on certain
details.

Wikipedia

+ [Hypertext Transfer Protocol](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol)
+ [List of HTTP header fields](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields)
+ [List of common internet media types](https://en.wikipedia.org/wiki/Internet_media_type#List_of_common_media_types)
+ [List of HTTP status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)

HTTP Protocol (W3C)

+ [HTTP/1.1: Sec. 5 Request](https://www.w3.org/Protocols/rfc2616/rfc2616-sec5.html)
+ [HTTP/1.1: Sec. 6 Response](https://www.w3.org/Protocols/rfc2616/rfc2616-sec6.html)
+ [HTTP/1.1: Sec. 9 Method Definitions](https://www.w3.org/Protocols/rfc2616/rfc2616-sec6.htmlhttp://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html)
+ [HTTP:/1.1: Sec. 10 Status Code Definitions](https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html)
+ [HTTP/1.1: Sec. 14 Header Field Definitions](https://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html)

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
