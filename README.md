# JavaScript Closure Issue in setTimeout

This repository demonstrates a common closure issue encountered when using JavaScript's `setTimeout` function within a loop.

## The Problem
The code in `bug.js` intends to log the numbers 0 through 9, each after a one-second delay.  Due to how closures work with `setTimeout` and the loop variable, this does not happen.  All the `setTimeout` callbacks will eventually log 10 because the loop completes before the `setTimeout` callbacks are even executed.  By the time they are executed, `i` will be 10. 

## The Solution
The solution, found in `bugSolution.js`, utilizes an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop. This ensures that each `setTimeout` callback has its own copy of `i`, preserving the intended value.

## How to Run
1. Clone this repository.
2. Open `bug.js` and `bugSolution.js` in a JavaScript environment (browser console, Node.js, etc.).
3. Run each file separately to observe the different outputs.