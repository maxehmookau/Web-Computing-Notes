Lecture 8 - HTTP
===

>The most common form of web-based applications occur as web browsers using HTTP to communicate with web servers. For example, when you type a URL of the form
http://www.somewhere.com/index.html in to a web browser you are making a request to find a website called 'www.somewhere.com' and fetch the HTML document 'index.html' located there.


Brief Look at HTTP
--
>If a user on a client machine types a URL in to the location box on their browser, an HTTP request is generated. Let's have a closer look at what the HTTP request looks like though.

A TCP connection is made to a specific `port` (usually 80) and then any server `listening` on that port will receive a string detailing the nature of the request. This includes which type of HTTP request it is.

There are 8 types:

* GET
* HEAD 
* POST 
* PUT 
* DELETE
* TRACE
* CONNECT
* OPTIONS

These are referred to as HTTP `methods`. The most important of which are `GET` and `POST`. Typing in an address bar or clicking a link will generate a `GET` request. Filling out a form will generate a `POST` request. 

A typical `GET` request is as follows:

    GET /pages/My%20First%20Webpage HTTP/1.1
    Host: www.somewhere.com
    Connection: Keep-Alive
    User-Agent: Mozilla/4.0 (
      compatible; 
      MSIE 4.01; 
      Windows NT)
    Accept: image/gif, image/x-xbitmap, 
       image/jpeg, image/pjpeg

Once received and processed, a HTTP server then replies with a `HTTP Response`. This contains information such as the status of the request and other information such as the time and date. The `response code` tells the client how the server responded to the request, usually in the form of a three digit code. The most common of these codes are:

* 200 OK - This is good. 
* 404 Not Found - The requested URL does not exist.
* 301 Moved Permanently
* 302 Moved Temporarily
* 303 See Other - The resource has moved and its position is in the header.
* 500 Server Error - There's an internal error in the server code. 

   
    HTTP/1.1 200 OK
    Date: Fri, 31 Dec 1999 23:59:59 GMT
    Content-Type: text/html
    Content-Length: 1354

Using the GET Method
--
> The way in which parameters are passed from a client application to a HTTP server depends upon which HTTP method is being used.

When using the `GET` method, the parameters are encoded in the URL string using key/value pairs. 

    ?name=max&age=21

being a good example. 

Using the POST Method
--

`POST` complements `GET` nicely as it is for actions where information is posted to the server rather than when the server is queried for information. It hides the parameters from the URL and puts them in the body of the request instead but the data is still stored as a key/value pair.  

Scripting Web Applications
--

This is all well and good <script> but why not use `AJAX`?