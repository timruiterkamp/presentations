# Presentation 3

## HTTP

http://text.example.com:3000 = protocol( http ), subdomain ( text ), domain( example.com ), port( 3000 ) = Server side
Users/search?q=test&w-all = path( users/ search ), query( test & w-all ) domain side

###Client
user-agent
web-browser
request

### Server

waiting requests
sends response
multiple machines(can be 1 can exist of multiple )

### exists of

* method (Get)
* / (path)
* HTTP/1.1 (version)
* Total: GET / HTTP/1.1

* **Headers**
* Host: developer.mozzila.org
* Accept-language: fr
* Content-type: text/html
* Content-length: 229780

### Status codes

* 200 = OK,
* 201 = Created
* 204 = Ok, but no content

* information
  * 1.. (example: 101 switching protocols)
* Succes
  * 2.. (200 OK, 201 created)
* Redirect
  * 3.. (301 moved permanently)
* Client error
  * 4.. (404 page not found)
* Server error
  * 5.. (501 server error)

### http methods

* Put: create or replace a resource (used to place information in a specific place)
* Post: Used to add to a list / Put: used to replace in a list
* GET: Get list of all elements
* PATCH: Update specific element in list( {age: 21 })
* Delete: delete element in list

## Server

### Routes

```javascript
var router = {
  "/about": "this is my website \n",
  "/": "hello world"
};

var http = require("http");
var path = require("path");
var buf = require("buffer");
var mime = {
  '.html': 'text/html'
  '.css': 'text/css'
}

http.createServer(onrequest).listen(8000);

function onrequest(req, res) {
  var route = req.url;

  if (route === "/") {
    route = "index.html";
  }

  fs.readFile(path.join("static", route), onread);
  function onread(err, buff) {
    res.setHeader("content-type", "text/html");

    if (err) {
      res.statusCode = 404;
      res.end("not found. \n");
    } else {
      var extension = path.extname(route);
      var type = mime[extension] || 'text/plain';
      res.statusCOde = 200;
      res.end(buf);
    }
  }
}
```

```javascript
var http = require("http");

http
  .request("http://example.com", onresponse)
  .on("error", onerror)
  .end();

function onerror(err) {
  console.error("something went wrong!", err);
}

function onresponse(res) {
  res.on("data", ondata).on("end", onend);

  function ondata(buf) {
    bufs.push(buf);
  }

  function onend() {
    console.log(Buffer.concat(bufs).toString());
  }
}
```
