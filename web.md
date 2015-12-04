#### cookie vs session
- The data of cookie is stored in local browser, thus it is not safe.
- The data of session is stored in the server for some time. It is safe but might hurt the preformance of the server.

#### What is MVC?
- Model: managing data; 
- Controller: application logic; 
- View: presenting data

#### GET vs POST?
- GET: retrieve representations of resources; no side effects; no data in request body. 
- POST: upload data from the browser to server; returns information from the server; side effects are likely; data contained in the request body.

#### AngularJS
- client-side templating. templates, which are HTML documents defining the UI, are loaded from server; once in the browser, Angular merges template with data, defining a vew.

- template data binding. Use $scope to expose model data to view. Views dynamically load template fragment via routes

#### Synchronous vs Asynchronous I/O
- In synchronous I/O, a thread starts an I/O operation and immediately enters a wait state until the I/O request has completed. 
- A thread performing asynchronous I/O sends an I/O request to the kernel by calling an appropriate function. If the request is accepted by the kernel, the calling thread continues processing another job until the kernel signals to the thread that the I/O operation is complete. It then interrupts its current job and processes the data from the I/O operation as necessary. 

#### NodeJS
- It is fast due to V8 engine.
- Event loop. It is a single thread that performs all I/O operations asynchronously. Traditionally, I/O operations either run synchronously (blocking) or asynchronously by spawning off parallel threads to perform the work. This old approach consumes a lot of memory and is notoriously difficult to program. In contrast, when a Node application needs to perform an I/O operation, it sends an asynchronous task to the event loop, along with a callback function, and then continues to execute the rest of its program. When the async operation completes, the event loop returns to the task to execute its callback.
- In other words, reading and writing to network connections, reading/writing to the filesystem, and reading/writing to the database–all very common tasks in web apps–execute very, very fast in Node. Node allows you to build fast, scalable network applications capable of handling a huge number of simultaneous connections with high throughput.
- The Event Loop is a queue of callback functions. When an async function executes, the callback function is pushed into the queue. The JavaScript engine doesn't start processing the event loop until the code after an async function has executed. This means that JavaScript code is not multi-threaded even though it appears to be so. 
- The event loop is a first-in-first-out (FIFO) queue, meaning that callbacks execute in the order they were added onto the queue.
```javascript
console.log( "a" );
setTimeout(function() {
    console.log( "c" )
}, 500 );
setTimeout(function() {
    console.log( "d" )
}, 500 );
setTimeout(function() {
    console.log( "e" )
}, 500 );
console.log( "b" );
// a b c d e
```



#### AngularJS vs ExpressJS
#### Client-side rendering vs Server-side rendering
