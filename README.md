# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in the request handler blocks the event loop, leading to server unresponsiveness.  The `server.js` file shows the problematic code, while `serverSolution.js` provides a corrected version using asynchronous operations.

## Problem

The original `server.js` uses a `while` loop to simulate a 5-second task.  This blocks the event loop, preventing Node.js from handling subsequent requests.  Any client attempting to connect during this time will experience a timeout or hang.

## Solution

The `serverSolution.js` file demonstrates a solution using asynchronous operations.  While this example uses `setTimeout`, real-world scenarios might involve database queries, file I/O, or other asynchronous operations.  By using asynchronous approaches, the event loop remains responsive, and the server can continue handling other requests while the long-running task executes in the background.