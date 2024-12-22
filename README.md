# Node.js Server Hang Issue

This repository demonstrates a common issue in Node.js where long-running requests can cause the server to become unresponsive.  The `server.js` file contains a simple HTTP server that simulates a 5-second delay in processing a request. This delay blocks the event loop, preventing other requests from being handled. The solution is shown in `serverSolution.js`.

## How to Reproduce

1. Clone this repository.
2. Run `node server.js`.
3. Send multiple requests to `http://localhost:3000/`.  You'll notice that subsequent requests will hang until the first request completes.

## Solution

The solution involves using asynchronous operations or worker threads to offload long-running tasks from the main event loop.  See `serverSolution.js` for an example using asynchronous callbacks.