# TypeScript setTimeout Closure Bug

This repository demonstrates a common closure-related bug in JavaScript/TypeScript when using `setTimeout` within a loop. The issue arises because the closure references the variable `i` after the loop has completed, leading to unexpected behavior.

## Problem

The `printNumbers2` function intends to print numbers from 1 to `n` with a one-second delay between each number. However, due to the asynchronous nature of `setTimeout` and the way closures work, it prints the final value of `i` (which is `n+1`) for each iteration.

## Solution

The solution involves using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop, capturing the current value of `i`. This ensures that each `setTimeout` callback has its own copy of `i`.

## How to run

1. Clone this repository.
2. Navigate to the repository directory.
3. Run `tsc` to compile the TypeScript code.
4. Run `node bug.js` to see the buggy output and `node bugSolution.js` to see the corrected output. 