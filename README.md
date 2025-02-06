# Express.js Server Unresponsiveness with Long-Running Requests

This repository demonstrates a common issue in Express.js applications where long-running requests can cause the server to appear unresponsive.  The example uses a `setTimeout` function to simulate a request that takes 5 seconds to process. This demonstrates how a synchronous request can block all other incoming requests. A solution is presented that addresses the issue.

## Bug

The provided `bug.js` file contains an Express.js application with a single route that simulates a long-running operation. Due to this synchronous operation, any other incoming request is blocked until the response for the first request is sent. 

## Solution

The `bugSolution.js` file offers a solution that uses asynchronous middleware. Using techniques like promises or async/await ensures that the server does not hang during lengthy operations. The main change is replacing the synchronous response with a call that correctly handles the async function.