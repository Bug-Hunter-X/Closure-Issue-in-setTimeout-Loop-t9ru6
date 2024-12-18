# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common issue in JavaScript related to closures and the `setTimeout` function within loops.  The example shows how the value of the loop variable 'i' is not correctly captured within the callback function of `setTimeout`, leading to unexpected behavior.

## Bug Description
The code uses a `for` loop to schedule multiple `setTimeout` calls. One might expect each callback to log a different value of `i`, from 0 to 9. However, due to closure behavior, all callbacks end up using the final value of `i` (which is 10) after the loop completes.

## Solution
The solution involves using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, thereby capturing the correct value of `i` for each callback.