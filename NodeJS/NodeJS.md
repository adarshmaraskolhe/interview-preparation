# Node JS Interview Questions

## Q.1 What is node.js ?

**Answer:**  
Node.js is a runtime environment for javascript that allows you to run JavaScript code on the server side outside of a web browser.
*   **Built on Chrome’s V8 JavaScript engine:** - This gives Node.js high performance in executing JavaScript code.
*   **Non-blocking I/O and event-driven architecture:** - This makes it efficient and suitable for real-time applications like chat apps, online games, or live notifications.
*   **Used for backend development:** - While JavaScript is traditionally used on the client side (browser), Node.js lets you build the server side using JavaScript too.


## Q.2 Advantages of node.js

**Answer:**
*   **Fast Performance:** - Built on Chrome’s V8 engine, which compiles JavaScript to machine code.
Handles many operations (like file reads, network requests) asynchronously, making it highly efficient.
*   **Asynchronous & Non-Blocking I/O:** - Executes multiple tasks in parallel without waiting for one to finish.
Ideal for real-time applications (e.g., chats, live updates).
*   **Cross-Platform Development:** - Useful in building tools, desktop apps (with Electron), APIs, and even IoT solutions.


## Q.3 IS node.js single threaded ?

**Answer:**
Yes, Node.js is single-threaded 
* Node.js uses a single main thread to handle JavaScript execution.
* However, it uses non-blocking I/O and the event loop to efficiently manage multiple concurrent operations (like file access, network requests, etc.).

## Q.4 How node.js handles concurrency even after it is single threaded ?

**Answer:**
*   **Event Loop:** - The event loop is the core mechanism that enables Node.js to perform non-blocking operations. It continuously checks for tasks, executes them, and handles callbacks as asynchronous operations complete.
*   **Libuv & Thread Pool:** - Node.js uses a C++ library called libuv to handle asynchronous I/O operations. Although JavaScript runs on a single thread, libuv maintains a thread pool (usually 4 threads) that performs:

File system operations
DNS lookups
Compression
Crypto operations

These tasks are passed to the thread pool and do not block the main thread.


## Q.5 Module in node.js

**Answer:** 
In Node.js, a module is a reusable piece of code that can be exported from one file and imported into another. Modules help keep your code organized, maintainable, and encapsulated.

*   **Core Modules:** - Built into Node.js – no need to install.
Examples: http, fs, path, os.

*   **Third-party Modules:** - Installed via npm (Node Package Manager).
Example: express, lodash, mongoose.