# Node.js

NodeJS is JavaScript running server-side. It is difficult to overstate how
fucking awesome this actually is. Used correctly, JavaScript is a brilliant
little language, and speaking exactly the same language in the browser and on
the server is simply amazing.

Furthermore, Node does not simply replace PHP, it also replaces Apache. If you
run a single Node web app on port 80 on a VPS and point a domain there, your
website would get served. However, if you need multiple Nodes on one server or
more efficient serving of static content, you will use
[Nginx](../deploying/nginx.md) as well. So in the end, Node.js and Nginx
completely replace Apache and PHP or whatever other language one would use.

Thanks to Google's V8 engine, JavaScript and Node are also incredibly fast.

## General Tips & Notes

## Non-blocking & Super-blocking

Node claims to be non-blocking. But this is only the case if it is built
correctly. One Node application is always single-threaded, so if you lock it up
doing something that takes a long time, it becomes super blocking. Essentially
not doing anything else until it is done doing whatever it should probably not
even have been doing in the first place.
