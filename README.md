# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  the lack of proper error handling for invalid input. Specifically, the example shows a route that retrieves a user by ID but fails to handle cases where the ID is not a valid integer.

## Bug Description
The `/users/:id` route attempts to parse the `id` parameter as an integer using `parseInt()`.  However, it doesn't check if the result of `parseInt()` is actually a number. If a non-numeric ID is provided, `parseInt()` will return `NaN`, causing the `users.find()` method to fail silently or throw an error, depending on the implementation.

## Solution
The solution involves adding input validation to ensure the `userId` is a number before attempting to use it.  This prevents unexpected errors and provides a more robust and user-friendly experience.

## How to reproduce
1. Clone the repository.
2. Run `npm install` to install dependencies.
3. Run `node bug.js`.
4. Send a GET request to `/users/abc` (or any non-numeric ID).

You'll likely see an error in the console, or unexpected behavior, highlighting the bug.