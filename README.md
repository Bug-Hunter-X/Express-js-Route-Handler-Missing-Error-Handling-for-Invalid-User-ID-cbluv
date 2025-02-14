# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.  Specifically, the `/users/:id` route attempts to parse the `id` parameter as an integer but does not handle cases where the parameter is not a valid integer.

## Bug

The `bug.js` file contains the erroneous code.  It uses `parseInt` to convert the `id` parameter to an integer, but it doesn't check if the conversion was successful or if the resulting integer is valid within the context of the application (e.g., a negative ID).

## Solution

The `bugSolution.js` file provides a corrected version. It includes error handling to check for non-numeric IDs, returning appropriate HTTP error responses in case of invalid input.  This improves the robustness and reliability of the application.

## How to Reproduce

1. Clone this repository.
2. Run `npm install express` to install Express.js.
3. Run `node bug.js` (for the buggy code) or `node bugSolution.js` (for the corrected code).
4. Send requests to `/users/:id` with various `id` values (numeric, non-numeric, negative).

Observe the differences in how the two versions handle invalid input. The solution handles invalid input gracefully and avoids potential crashes or unexpected behavior.