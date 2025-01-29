# Unhandled Error in Express.js Route Handler

This repository demonstrates a common error in Express.js route handlers:  failure to handle invalid input.  Specifically, the provided code lacks error handling for cases where the user ID is not a valid integer.

## Bug

The `bug.js` file contains an Express.js route that attempts to retrieve a user based on their ID.  However, it fails to handle scenarios where `req.params.id` is not a valid integer, leading to potential crashes or unexpected behavior.

## Solution

The `bugSolution.js` file shows a corrected version of the route handler, incorporating error handling to address non-numeric user IDs.  It checks if `parseInt(userId)` returns `NaN` and sends an appropriate error response in such cases.  This prevents crashes and provides a more robust and user-friendly experience.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js`. 
4. Make a request to `/users/abc` - the application will throw an error. 
5. Run `node bugSolution.js`. 
6. Make a request to `/users/abc` - the application should return a 400 error code. 