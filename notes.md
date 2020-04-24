# Modularity

**Modules** are files that contain specific code and can be loaded into other scripts. This is done by **importing** or **requiring** the modules into your script.

| Language | Code |
|--|--|
| Python | ``` from module import object as varName ``` |
| R | ``` library(tidyverse) ``` |
| JavaScript | ```const varName = require("./module") ```|

### After Importing JS Module
The export from a JS module is an object, where is then bound to your chosen varName. You can then access the module properties using dot notation.

## Creating JS Modules
```
module.exports = varToExport;
module.exports.fxn2 = fxn2(){};
module.exports = {fxn1: fxn1, param1: param1};
```

## Node core modules
### Events
```
const events = require("events");
let myEmitter = new events.EventEmitter();
myEmitter.on("event",fxn(){});
myEmitter.emit("event","values"); // Emit values of "event" type
```

### Util
```
const util = require("util");
util.inherits(objToInherit, thingToInherit);
```

### fs
fs is how Node interacts with your file system. ```const fs = require("fs");``` You can read and write files synchronously (blocking) or asynchronously (non-blocking). The arguments passed to the callback function depends on the method used but the first argument is always reserved for an exception.
* Read files: ```fs.readFileSync("file.txt", "encoding");```
* Read files: ```fs.readFile("file.txt", "encoding", callbackFxn(err,data){});```
* Write files: ```fs.writeFileSync("file.txt", dataVar);```
* Write files: ```fs.readFile("file.txt", dataVar, callbackFxn(err){});```
* Delete files: ``` fs.unlink("fileToDelete.txt"); ```
  * Gives an error if the file doesn't exist.
* Make folders: ``` fs.mkdirSync("folder"); || fs.mkdir("folder",callback(){}); ```
* Remove folders: ``` fs.rmdirSync("folder"); || fs.rmdir("folder", callback(){}); ```
  * Only works on empty directories
* Rename files/folders: ``` fs.rename("oldName", "newName", callbackFxn(err){}); ```

# Servers
Client computers communicate with server computers through **sockets** using specific **protocols**. Each communication involves a **request** and a **response**. Information is broken into **packets** and sent along the **socket**.
* Protocol: set of communication rules.
  * TCP: Transmission Control Protocol
  * HTTP: Hypertext Transfer Protocol
* Socket: connection between two computers.
* Port: specifies which part or program on a specific computer a request should be sent to.

### Creating a Server with Node JS
```
const http = require("http");
let myServer = http.createServer(fxn(req,resp){});
res.writeHead(headerInfo);
res.send(content);
server.listen(PORT, IP);
```

# Node Package Manager (NPM)
A collection of command line tools to help us install, update, and publish packages/modules.
```
>npm install package
>npm uninstall package
>npm init //create package.json file
>npm install package -save //will add the package as a dependency in your package.json file
>npm install //will install all dependencies listed in package.json
>npm install -g nodemon //globally installs nodemon
```
The **package.json** file keeps track of all **dependencies** for your application.

## Important packages
#### Express
Contains an easy, flexible routing system. Also integrates with template engines. Finally, contains a middleware framework.
```
app.get("/route/:key", (req,res) => {
  req.params.key;
  res.send("text"); OR res.sendFile(__dirname + "/file.html"); OR
  res.render("fileName", {key: req.params.key});
  });
```
#### Nodemon
Used for developing applications. Will monitor your core files and automatically restart the server if you make any changes. You then run your apps with ```nodemon app.js``` instead of ```node app.js```.

# Template Engines
Template engines, aka view engines, are programs that compile a template into an HTML document. This allows you to receive data from an external source and inject it into your HTML page.
### EJS
* Install ``` npm install ejs -save ```
* You then create a **index.ejs** file instead of index.html
```
app.set("view engine", "ejs");
res.render(); //will look in views folder
```
### PUG
* Intall ``` npm install pug -save ```
* Make file ``` touch index.pug ```




can only use pipe method on readStreams.

myReadStream.pipe(myWriteStream);

HTTP response object is a writeable-stream

content-type:
text/csv
text/css
text/html
text/markdown
application/ecmascript
application/javascript

https://www.iana.org/assignments/media-types/media-types.xhtml#text
