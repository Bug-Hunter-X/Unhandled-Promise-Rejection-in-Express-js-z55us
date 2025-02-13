# Unhandled Promise Rejection in Express.js

This repository demonstrates a common error in Express.js applications: unhandled promise rejections.  Asynchronous operations within request handlers may throw errors, leading to incomplete response cycles and potential application crashes.  The solution shows how to properly handle these rejections to ensure robust application behavior.

## Bug

The `bug.js` file showcases an Express.js application with an asynchronous operation (`doSomethingAsync`) inside a request handler. This operation has a 50% chance of failing and throwing an error.  Crucially, the error is logged but not handled effectively; the response to the client remains incomplete.

## Solution

The `bugSolution.js` file corrects this by implementing proper error handling within the `.catch` block of the promise. It ensures a response is sent to the client, regardless of success or failure of the asynchronous operation, avoiding an unhandled rejection.