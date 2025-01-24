# Node.js Port Already in Use Error

This repository demonstrates a common error in Node.js: attempting to start a server on a port that is already in use.  The `bug.js` file contains the problematic code, while `bugSolution.js` provides a solution.

## Problem

The `bug.js` script creates a simple HTTP server using the `http` module.  If you attempt to run this script while another process is already using port 8080, the script will throw an error.

## Solution

The `bugSolution.js` script addresses this issue by adding error handling. It uses the `listen` function's callback to gracefully handle the `EADDRINUSE` error, retrying after a short delay if necessary.

## How to Reproduce

1.  Clone this repository.
2.  Run `node bug.js`.  This should work if port 8080 is free.
3.  While the server is running, run `node bug.js` again in a separate terminal. This will cause the error.
4. Run `node bugSolution.js` to see the solution in action.