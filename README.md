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

Step 05: Run the app

node app.js

7. How to make an HTTP POST request using Node.js?
![image](https://user-images.githubusercontent.com/75446294/139559027-be8bce40-7779-4a21-9298-104fd9549ac0.png)
![image](https://user-images.githubusercontent.com/75446294/139559036-5bd49763-e48a-49e8-83b4-1bf40eac738b.png)

8. What does the runtime environment mean in Node.js?
The Node.js runtime is the software stack responsible for installing your web service's code and its dependencies and running your service.

The Node.js runtime for App Engine in the standard environment is declared in the app.yaml file:

runtime: nodejs10

The runtime environment is literally just the environment your application is running in. This can be used to describe both the hardware and the software that is running your application. How much RAM, what version of node, what operating system, how much CPU cores, can all be referenced when talking about a runtime environment.

9. How do Node.js works?

![image](https://user-images.githubusercontent.com/75446294/139559077-0cb6511d-0d89-45a7-af98-a481081db98b.png)
Node is completely event-driven. Basically the server consists of one thread processing one event after another.

A new request coming in is one kind of event. The server starts processing it and when there is a blocking IO operation, it does not wait until it completes and instead registers a callback function. The server then immediately starts to process another event (maybe another request). When the IO operation is finished, that is another kind of event, and the server will process it (i.e. continue working on the request) by executing the callback as soon as it has time.

So the server never needs to create additional threads or switch between threads, which means it has very little overhead. If you want to make full use of multiple hardware cores, you just start multiple instances of node.js

Node JS Platform does not follow Request/Response Multi-Threaded Stateless Model. It follows Single Threaded with Event Loop Model. Node JS Processing model mainly based on Javascript Event based model with Javascript callback mechanism.

Single Threaded Event Loop Model Processing Steps:

Clients Send request to Web Server.
Node JS Web Server internally maintains a Limited Thread pool to provide services to the Client Requests.
Node JS Web Server receives those requests and places them into a Queue. It is known as “Event Queue”.
Node JS Web Server internally has a Component, known as “Event Loop”. Why it got this name is that it uses indefinite loop to receive requests and process them.
Event Loop uses Single Thread only. It is main heart of Node JS Platform Processing Model.
Even Loop checks any Client Request is placed in Event Queue. If no, then wait for incoming requests for indefinitely.
If yes, then pick up one Client Request from Event Queue
Starts process that Client Request
If that Client Request Does Not requires any Blocking IO Operations, then process everything, prepare response and send it back to client.
If that Client Request requires some Blocking IO Operations like interacting with Database, File System, External Services then it will follow different approach
Checks Threads availability from Internal Thread Pool
Picks up one Thread and assign this Client Request to that thread.
That Thread is responsible for taking that request, process it, perform Blocking IO operations, prepare response and send it back to the Event Loop
Event Loop in turn, sends that Response to the respective Client.

10. What is the difference between Node.js, AJAX, and JQuery?
Node.js is a javascript runtime that makes it possible for us to write back-end of applications.

Asynchronous JavaScript and XML(AJAX) refers to group of technologies that we use to send requests to web servers and retrieve data from them without reloading the page.

Jquery is a simple javascript library that helps us with front-end development.

11.  What are the core modules of Node.js?
They are defined within the Node.js source and are located in the lib/ folder, and Node.js has several modules compiled into the binary.

Core modules are always preferentially loaded if their identifier is passed to require(). For instance, require('http') will always return the built in HTTP module, even if there is a file by that name.

Core modules can also be identified using the node: prefix, in which case it bypasses the require cache. For instance, require('node:http') will always return the built in HTTP module, even if there is require.cache entry by that name.

12. What is callback function in Node.js?
In node.js, we basically use callbacks for handling asynchronous operations like — making any I/O request, database operations or calling an API to fetch some data. Callback allows our code to not get blocked when a process is taking a long time.

![image](https://user-images.githubusercontent.com/75446294/139559107-2179b598-001c-432a-9658-93bbb6d9c3e1.png)

13. What is NPM?
NPM stands for Node Package Manager, responsible for managing all the packages and modules for Node.js.

Node Package Manager provides two main functionalities:

Provides online repositories for node.js packages/modules, which are searchable on search.nodejs.org
Provides command-line utility to install Node.js packages and also manages Node.js versions and dependencies  

14. Which database is more popularly used with Node.js?
MongoDB is the most common database used with Node.js. It is a NoSQL, cross-platform, document-oriented database that provides high performance, high availability, and easy scalability.

15. What are some of the most commonly used libraries in Node.js?
There are two commonly used libraries in Node.js:

ExpressJS - Express is a flexible Node.js web application framework that provides a wide set of features to develop web and mobile applications.
Mongoose - Mongoose is also a Node.js web application framework that makes it easy to connect an application to a database.

16. What is the command used to import external libraries?
The “require” command is used for importing external libraries. For example - “var http=require (“HTTP”).”  This will load the HTTP library and the single exported object through the HTTP variable.

Now that we have covered some of the important beginner-level Node.js interview questions let us look at some of the intermediate-level Node.js interview questions.

![image](https://user-images.githubusercontent.com/75446294/139559152-6b829a27-4a92-4caa-9165-dfb2da1a43d9.png)

17. What is an EventEmitter in Node.js?
EventEmitter is a class that holds all the objects that can emit events
Whenever an object from the EventEmitter class throws an event, all attached functions are called upon synchronously
![image](https://user-images.githubusercontent.com/75446294/139559175-90e0cb83-ee78-4cb6-a05e-93ca7b797f1e.png)

18. What is the package.json file?
The package.json file is the heart of a Node.js system. This file holds the metadata for a particular project. The package.json file is found in the root directory of any Node application or module

This is what a package.json file looks like immediately after creating a Node.js project using the command: npm init

You can edit the parameters when you create a Node.js project.

![image](https://user-images.githubusercontent.com/75446294/139559185-46d4e009-8941-47aa-bcee-6914c8e3f6c4.png)

19. What are streams in Node.js?
Streams are objects that enable you to read data or write data continuously.

There are four types of streams:

Readable – Used for reading operations

Writable − Used for write operations

Duplex − Can be used for both reading and write operations

Transform − A type of duplex stream where the output is computed based on input

20. How do you create a simple server in Node.js that returns Hello World?
simple-server

Import the HTTP module
Use createServer function with a callback function using request and response as parameters.
Type “hello world." 
Set the server to listen to port 8080 and assign an IP address

![image](https://user-images.githubusercontent.com/75446294/139559204-34420d81-eb66-4b98-9f6c-c22345306f47.png)
![image](https://user-images.githubusercontent.com/75446294/139559209-bdf242e1-c627-4d30-82a4-79769b966123.png)

21. What is a callback function in Node.js?
A callback is a function called after a given task. This prevents any blocking and enables other code to run in the meantime.

In the last section, we will now cover some of the advanced-level Node.js interview questions.

22. What is a test pyramid? How can you implement it when talking about HTTP APIs?
The "Test Pyramid" is a metaphor that tells us to group software tests into buckets of different granularity. It also gives an idea of how many tests we should have in each of these groups. It shows which kinds of tests you should be looking for in the different levels of the pyramid and gives practical examples on how these can be implemented.

![image](https://user-images.githubusercontent.com/75446294/139559243-f45e462d-738d-41f5-96ff-4933f293e3a3.png)

23. How can you make sure your dependencies are safe?
The only option is to automate the update / security audit of your dependencies. For that there are free and paid options:

npm outdated
Trace by RisingStack
NSP
GreenKeeper
Snyk
npm audit
npm audit fix

24. How to debug an application in Node.js?
node-inspector:

![image](https://user-images.githubusercontent.com/75446294/139559282-88da4213-a9ce-4984-974a-87b0f6b5323d.png)

Run

![image](https://user-images.githubusercontent.com/75446294/139559290-e970e41c-a3f0-4418-abe5-c15c219be4fd.png)

Debugging:

1. Debugger
2. Node Inspector
3. Visual Studio Code
4. Cloud9
5. Brackets

Profiling:

![image](https://user-images.githubusercontent.com/75446294/139559300-1208ca6b-f5fa-4722-8e54-6edbd00326a4.png)

Heapdumps:

. node-heapdump with Chrome Developer Tools

Tracing:

.Interactive Stack Traces with TraceGL

Logging:
 Libraries that output debugging information

1. Caterpillar
2. Tracer
3. scribbles
 Libraries that enhance stack trace information:

. Longjohn

25. What are some of the most popular packages of Node.js?

1.Async: Async is a utility module which provides straight-forward, powerful functions for working with asynchronous JavaScript.
2. Browserify: Browserify will recursively analyze all the require() calls in your app in order to build a bundle you can serve up to the browser in a single <script> tag.
3. Bower: Bower is a package manager for the web. It works by fetching and installing packages from all over, taking care of hunting, finding, downloading, and saving the stuff you’re looking for.
4. Csv: csv module has four sub modules which provides CSV generation, parsing, transformation and serialization for Node.js.
5. Debug: Debug is a tiny node.js debugging utility modelled after node core's debugging technique.
6. Express: Express is a fast, un-opinionated, minimalist web framework. It provides small, robust tooling for HTTP servers, making it a great solution for single page applications, web sites, hybrids, or public HTTP APIs.
7. Grunt: is a JavaScript Task Runner that facilitates creating new projects and makes performing repetitive but necessary tasks such as linting, unit testing, concatenating and minifying files (among other things) trivial.
8. Gulp: is a streaming build system that helps you automate painful or time-consuming tasks in your development workflow.
9. Hapi: is a streaming build system that helps you automate painful or time-consuming tasks in your development workflow.
10. Http-server: is a simple, zero-configuration command-line http server. It is powerful enough for production usage, but it's simple and hackable enough to be used for testing, local development, and learning.
11. Inquirer: A collection of common interactive command line user interfaces.
12. Jquery: jQuery is a fast, small, and feature-rich JavaScript library.
13. Jshint: Static analysis tool to detect errors and potential problems in JavaScript code and to enforce your team's coding conventions.
14. Koa: Koa is web app framework. It is an expressive HTTP middleware for node.js to make web applications and APIs more enjoyable to write.
15. Lodash: The lodash library exported as a node module. Lodash is a modern JavaScript utility library delivering modularity, performance, & extras.
16. Less: The less library exported as a node module.
17. Moment: A lightweight JavaScript date library for parsing, validating, manipulating, and formatting dates.
18. Mongoose: It is a MongoDB object modeling tool designed to work in an asynchronous environment.
19. MongoDB: The official MongoDB driver for Node.js. It provides a high-level API on top of mongodb-core that is meant for end users.
20. Npm: is package manager for javascript.
21. Nodemon: It is a simple monitor script for use during development of a node.js app, It will watch the files in the directory in which nodemon was started, and if any files change, nodemon will automatically restart your node application.
22. Nodemailer: This module enables e-mail sending from a Node.js applications.
23. Optimist: is a node.js library for option parsing with an argv hash.
24. Phantomjs: An NPM installer for PhantomJS, headless webkit with JS API. It has fast and native support for various web standards: DOM handling, CSS selector, JSON, Canvas, and SVG.
25. Passport: A simple, unobtrusive authentication middleware for Node.js. Passport uses the strategies to authenticate requests. Strategies can range from verifying username and password credentials or authentication using OAuth or OpenID.
26. Q: Q is a library for promises. A promise is an object that represents the return value or the thrown exception that the function may eventually provide.
27. Request: Request is Simplified HTTP request client make it possible to make http calls. It supports HTTPS and follows redirects by default.
28. Socket.io: Its a node.js realtime framework server.
29. Sails: Sails : API-driven framework for building realtime apps, using MVC conventions (based on Express and Socket.io)
30. Through: It enables simplified stream construction. It is easy way to create a stream that is both readable and writable.
31. Underscore: Underscore.js is a utility-belt library for JavaScript that provides support for the usual functional suspects (each, map, reduce, filter...) without extending any core JavaScript objects.
32. Validator: A nodejs module for a library of string validators and sanitizers.
33. Winston: A multi-transport async logging library for Node.js
34. Ws: A simple to use, blazing fast and thoroughly tested websocket client, server and console for node.js
35.Xml2js: A Simple XML to JavaScript object converter.
36.Yo: A CLI tool for running Yeoman generators
27. Zmq: Bindings for node.js and io.js to ZeroMQ .It is a high-performance asynchronous messaging library, aimed at use in distributed or concurrent applications.
