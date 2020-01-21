+++
title = "Basic Node and Express"
date = "2020-01-20"
draft = false
pinned = false
image = "/img/nodejs.png"
+++
##  Start a Working Express Server
***In Express***, `routes` takes the following structure: ``app.METHOD(PATH, HANDLER)``. ***METHOD*** is an **http** method in lowercase. **PATH** is a relative path on the server (it can be a string, or even a regular expression). **HANDLER** is a function that Express calls when the route is matched.

**Handlers** take the form ``function(req, res) {...}``, where req is the request object, and res is the response object. For example, the handler

We Use the ``app.get()`` method to serve the string "..." to ***GET*** requests matching the / (root) path.
```js
app.get("/", (req, res)=> res.send("Hello Express"))
```
##  Serve an HTML File
You ***respond*** to requests with a file using the ``res.sendFile(path)`` method. You can put it inside the ``app.get('/', ...)`` route handler. Behind the scenes, this method will set the appropriate headers to instruct the browser on how to handle the file we want to send, according to its type. Then it will read and send the file. This method needs an absolute file path. We recommend you to use the Node global variable ``__dirname`` to calculate the path like this:

    absolutePath = __dirname + relativePath/file.ext

```js
app.get("/", (req, res)=> {
  res.sendFile(__dirname + "/views/index.html");
});
```
##  Serve Static Assets
To serve static files such as images, CSS files, and JavaScript files, use the express.static built-in middleware function in Express.

```js
express.static(root, [options])
```

[middleware](https://expressjs.com/en/guide/writing-middleware.html) are functions that intercept route handlers, adding some kind of information. A [middleware](https://expressjs.com/en/guide/writing-middleware.html) needs to be mounted using the method ``app.use(path, middlewareFunction)``. The first path argument is optional. If you don’t pass it, the [middleware](https://expressjs.com/en/guide/writing-middleware.html) will be executed for all requests.

* To use multiple static assets directories, call the express.static [middleware](https://expressjs.com/en/guide/writing-middleware.html) function multiple times:
```js
app.use(express.static('public'))
app.use(express.static('files'))
```
* However, the path that you provide to the express.static function is relative to the directory from where you launch your node process. If you run the express app from another directory, it’s safer to use the absolute path of the directory that you want to serve:

```js
app.use('/static', express.static(path.join(__dirname, 'public')))

```
##  Serve JSON on a Specific Route

```js
app.get('/json', (req, res)=>{
    res.json({
      message: "Hello json"
      });
})
```
##  Implement a Root-Level Request Logger middleware

Here we Build a simple ***logger***. For every request, it should log to the console a string ***taking the following format:*** ``method path - ip``. An example would look like this: ``GET /json - ::ffff:127.0.0.1.`` We can get the request method (http verb), the relative route path, and the caller’s ip from the request object using ``req.method, req.path and req.ip.`` Remember to call ``next()`` when you are done, or your server will be stuck forever. Be sure to have the ‘Logs’ opened, and see what happens when some request arrives.
```js
app.get("/json", (req, res, next)=>{
  console.log(`${req.method} ${req.path} - ${req.ip}`);
  next();
});

```
## Chain middleware to Create a Time Server

Middleware can be mounted at a specific route using ``app.METHOD(path, middlewareFunction)``. Middleware can also be chained inside route definition.

### Requirements
In the route ``app.get('/now', ...)`` chain a middleware function and the final handler. In the middleware function you should add the current time to the request object in the ``req.time`` key. You can use new ``Date().toString()``. In the handler, respond with a JSON object, taking the structure {time: req.time}.

```js
app.get('now', (req,res,next){
  req.time = new Date().toString()
  next();
}, (req,res)=>{
  res.send({ 
    time: req.time
  })
}
```
## Get Route Parameter Input from the Client
```js
app.get("/:word/echo", (req,res)=>{
  res.json({echo: req.params.word })
})
```
## Get Query Parameter Input from the Client
***Route parameters*** are named segments of the ***URL***, delimited by slashes (/). Each segment captures the value of the part of the URL which matches its position. The captured values can be found in the ``req.params`` object.

### Requirements
Build an echo server, mounted at the route **GET** ``/:word/echo.`` Respond with a JSON object, taking the structure ``{echo: word}``. You can find the word to be repeated at ``req.params.word``. You can test your route from your browser's address bar, visiting some matching routes, e.g. your-app-rootpath/freecodecamp/echo.
```js
app.get("/:word/echo", (req,res)=>{
  res.json({echo: req.params.word })
})
```
## Get Query Parameter Input from the Client
Another common way to get ***input*** from the client is by encoding the data after the route path, using a query string. **The query string** is delimited by a question mark (**?**), and includes ``field=value`` couples. Each couple is separated by an ampersand (**&**). Express can parse the data from the query string, and populate the object ``req.query``. Some characters, like the percent (**%**), cannot be in URLs and have to be encoded in a different format before you can send them. If we use the API from JavaScript, you can use specific methods to encode/decode these characters.

### Requirements
Build an ***API endpoint***, mounted at GET /name. Respond with a JSON document, taking the structure ``{ name: 'firstname lastname'}``. The first and last name parameters should be encoded in a query string e.g. ``?first=firstname&last=lastname``.

Here we are  receiving data from a POST request, at the same /name route path.we can use the method ``app.route(path).get(handler).post(handler)``. This syntax allows you to chain different verb handlers on the same path route. You can save a bit of typing, and have cleaner code.
```js
app.get("/name", (req,res)=>{
  const firstName = req.query.first;
  const lastName = req.query.last;
  res.send({"name": firstName + " " + lastName})
```
## Use body-parser to Parse POST Requests

Besides ***GET***, there is another common ***HTTP verb***, it is POST. **POST** is the default method used to send client data with HTML forms. In REST convention, POST is used to send data to create new items in the database (a new user, or a new blog post).

In these kind of requests, the data doesn’t appear in the URL, it is hidden in the request body. This is a part of the HTML request, also called ***payload***. Since HTML is text-based, even if you don’t see the data, it doesn’t mean that it is secret. The raw content of an HTTP POST request is shown below:

  POST /path/subpath HTTP/1.0
  From: chiar.evdi@gmail.com
  User-Agent: someBrowser/1.0
  Content-Type: application/x-www-form-urlencoded
  Content-Length: 20
  name=Chiar+Evdi&age=31

```js
app.post('/name', (req, res)=> {
  var firstName = req.body.first;
  var lastName = req.body.last;
  res.send({"name": firstName + " " + lastName})
});
```
## Get Data from POST Requests
Mount a POST handler at the path /name. It’s the same path as before. We have prepared a form in the html frontpage. It will submit the same data of exercise 10 (Query string). If the body-parser is configured correctly, you should find the parameters in the object req.body. Have a look at the usual library example:

  route: POST '/library'
  urlencoded_body: userId=546&bookId=6754
  req.body: {userId: '546', bookId: '6754'}

> Respond with the same JSON object as before: {name: 'firstname lastname'}. Test if your endpoint works using the html form we provided in the app frontpage.

###  Other http methods 
* POST (sometimes PUT) - Create a new resource using the information sent with the request,
* GET - Read an existing resource without modifying it,
* PUT or PATCH (sometimes POST) - Update a resource using the data sent,
* DELETE => Delete a resource.
