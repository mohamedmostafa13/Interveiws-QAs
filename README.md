# Interveiws-QAs
#Node JS Section:

1.What is Node.js?

Node.js is an open-source server side runtime environment built on Chrome's V8 JavaScript engine. It provides an event driven, non-blocking (asynchronous) I/O and cross-platform runtime environment for building highly scalable server-side applications using JavaScript.

2.What are the benefits of using Node.js?

From a web server development perspective Node has a number of benefits:
. Great performance! Node was designed to optimize througput and scalability in web applications and is a good solution for many common web-development problems (e.g. real-time web applications).

. Code is written in "plain old JavaScript", which means that less time is spent dealing with "context shift" between languages when you're writing both client-side and server-side code.

. JavaScript is a relatively new programming languages and benefits from improvements in language design when compared to other traditional web-server languages (e.g. Python, PHP, etc.) Many other new and pouplar languages compile/convert into JavaScript so you can use TypeScript, CoffeeScript, ClojureScript, Scala, LiveScript, etc.

. The node package manager (NPM) provides access to hundres of thousands of resuable packages. It also has best-in-class dependency resolution and can also be used to automate most of the build toolchain.

. Node.js is portable. It is available on Microsoft Windows, macOS, Linux, Solaris, FreeBSD, OpenBSD, WebOS, and NonStop OS. Furthermore, it is well-supported by many web hosting providers, that often provide specific infrastrucutre and documentation for hosting Node sites.

. It has a very active third party ecosystem and developer community, with lots of people who are willing to help.

3. What is Node.js Process Model?
Node.js runs in a single process and the application code runs in a single thread and thereby needs less resources than other platforms. All the user requests to your web application will be handled by a single thread and all the I/O work or long running job is performed asynchronously for a particular request. So, this single thread doesn't have to wait for the request to complete and is free to handle the next request. When asynchronous I/O work completes then it processes the request further and sends the response.

4. What are the data types in Node.js?
Primitive Types

String

Number

Boolean

Undefined

Null

RegExp

Buffer: Node.js includes an additional data type called Buffer (not available in browser's JavaScript). Buffer is mainly used to store binary data, while reading from a file or receiving packets over the network.

5. How to create a simple server in Node.js that returns Hello World?
Step 01: Create a project directory

mkdir myapp
cd myapp
Step 02: Initialize project and link it to npm

npm init
This creates a package.json file in your myapp folder. The file contains references for all npm packages you have downloaded to your project. The command will prompt you to enter a number of things. You can enter your way through all of them EXCEPT this one:

entry point: (index.js)
Rename this to:

app.js
Step 03: Install Express in the myapp directory

npm install express --save
Step 04: app.js
![image](https://user-images.githubusercontent.com/75446294/139558870-8218a856-45cc-430d-b4ef-11503337a540.png)

var express = require('express');
var app = express();
app.get('/', function (req, res) {
  res.send('Hello World!');
});

app.listen(3000, function () {
  console.log('Example app listening on port 3000!');
});
Step 05: Run the app

node app.js
