# Express.js JSON Body Parsing Issue

This repository demonstrates a common issue encountered when working with JSON data in Express.js applications.  The server fails to parse incoming JSON requests if the `Content-Type` header is missing or is set incorrectly.

## Bug Description

The provided `bug.js` file demonstrates a simple Express.js server that attempts to parse JSON data from POST requests to the `/data` endpoint.  However, if the client does not send the correct `Content-Type: application/json` header, the `req.body` will be empty, leading to unexpected behavior or errors.

## Solution

The solution involves ensuring the `Content-Type` header is correctly set in the client's request. This is demonstrated in the corrected version `bugSolution.js`  which uses a library like axios to ensure correct headers are sent.  Alternatively, more robust handling within the Express.js server can check and correct the header, although setting the correct header from the client is generally preferred.

## How to reproduce

1. Clone this repo.
2. Run `npm install` to install necessary dependencies
3. Run `node bug.js` and `node bugSolution.js` to check the different versions
4. Send a POST request to `http://localhost:3000/data` with JSON data using a tool such as Postman or curl, ensuring you set the correct header, or omit it to check the bug.
