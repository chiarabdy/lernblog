+++
title = "Basic Node and Express"
date = "2020-01-20"
draft = false
pinned = false
image = "/img/nodejs.png"
+++
## Start a Working Express Server
***In Express***, `routes` takes the following structure: ``app.METHOD(PATH, HANDLER)``. ***METHOD*** is an **http** method in lowercase. **PATH** is a relative path on the server (it can be a string, or even a regular expression). **HANDLER** is a function that Express calls when the route is matched.

**Handlers** take the form ``function(req, res) {...}``, where req is the request object, and res is the response object. For example, the handler

We Use the ``app.get()`` method to serve the string "..." to ***GET*** requests matching the / (root) path.
```js
app.get("/", (req, res)=> res.send("Hello Express"))
```
## Serve an HTML File
You ***respond*** to requests with a file using the ``res.sendFile(path)`` method. You can put it inside the ``app.get('/', ...)`` route handler. Behind the scenes, this method will set the appropriate headers to instruct the browser on how to handle the file we want to send, according to its type. Then it will read and send the file. This method needs an absolute file path. We recommend you to use the Node global variable ``__dirname`` to calculate the path like this:

    absolutePath = __dirname + relativePath/file.ext

```js
app.get("/", (req, res)=> {
  res.sendFile(__dirname + "/views/index.html");
});
```
## Serve Static Assets
To serve static files such as images, CSS files, and JavaScript files, use the express.static built-in middleware function in Express.

```js
express.static(root, [options])
```

middleware are functions that intercept route handlers, adding some kind of information. A middleware needs to be mounted using the method ``app.use(path, middlewareFunction)``. The first path argument is optional. If you don’t pass it, the middleware will be executed for all requests.

* To use multiple static assets directories, call the express.static middleware function multiple times:
```js
app.use(express.static('public'))
app.use(express.static('files'))
```
* However, the path that you provide to the express.static function is relative to the directory from where you launch your node process. If you run the express app from another directory, it’s safer to use the absolute path of the directory that you want to serve:

```js
app.use('/static', express.static(path.join(__dirname, 'public')))

```
## Serve JSON on a Specific Route

```js
app.get('/json', (req, res)=>{
    res.json({
      message: "Hello json"
      });
})
```
## Implement a Root-Level Request Logger Middleware 
Here we Build a simple ***logger***. For every request, it should log to the console a string ***taking the following format:*** ``method path - ip``. An example would look like this: ``GET /json - ::ffff:127.0.0.1.`` We can get the request method (http verb), the relative route path, and the caller’s ip from the request object using ``req.method, req.path and req.ip.`` Remember to call ``next()`` when you are done, or your server will be stuck forever. Be sure to have the ‘Logs’ opened, and see what happens when some request arrives.
```js
app.get("/json", (req, res, next)=>{
  console.log(`${req.method} ${req.path} - ${req.ip}`);
  next();
});

```
## Chain Middleware to Create a Time Server
