# HTTP

Copied from <https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Technical_overview>:

HTTP functions as a request–response protocol in the client–server computing
model. A web browser, for example, may be the client and an application running
on a computer hosting a website may be the server. The client submits an HTTP
request message to the server. The server, which provides resources such as
HTML files and other content, or performs other functions on behalf of the
client, returns a response message to the client. The response contains
completion status information about the request and may also contain requested
content in its message body.

Understanding the fundamentals of HTTP is both simple and important for.

There are 3 aspects of the protocol that are critical:

- HTTP functions as a request–response protocol in the client–server computing model
- Both responses and requests contain headers describing the entity, and
  expected behaviour, and an optional body containing data.
  response headers är viktiga)
- There are several request types, known as [Request
  Methods](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods)
  (or verbs), the two most common being GET and POST

Det är bra att läsa igenom Wiki artikeln om HTTP

- <https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol>

Det är också bra att bläddra igenom följande för att se vad som finns.

- <https://en.wikipedia.org/wiki/List_of_HTTP_header_fields>
- <https://en.wikipedia.org/wiki/List_of_HTTP_status_codes>

## HTTPS

HTTP has essentially been superseded by HTTPS, which is simply encrypted
HTTP. Standard port is 443 vs 80 for regular HTTP.

## HTTP/2

Standardized in 2015, [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) is now
supported by most major web browsers.

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
