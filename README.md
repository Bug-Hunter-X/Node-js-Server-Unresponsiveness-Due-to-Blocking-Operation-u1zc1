# Node.js Server Unresponsiveness

This repository demonstrates a common issue in Node.js where a long-running synchronous operation within the HTTP request handler blocks the event loop, causing the server to become unresponsive. The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The `server.js` file simulates a long-running operation (a 5-second CPU-bound loop) inside the request handler.  This blocks the event loop, preventing Node.js from processing other requests or events.  Any client trying to connect to the server during this time will experience a delay or timeout. 

## Solution

The `serverSolution.js` file demonstrates how to fix this by refactoring the long-running task to use asynchronous operations, avoiding blocking of the event loop.  It uses `setTimeout` to simulate an asynchronous task.