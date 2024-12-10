# React useEffect Hook Memory Leak

This repository demonstrates a common mistake when using the `useEffect` hook in React with `setInterval`.  Forgetting to return a cleanup function in the `useEffect` hook leads to memory leaks and unpredictable behavior.

## Bug

The `bug.js` file contains a component that uses `setInterval` to update a counter every second. However, it lacks a cleanup function to clear the interval when the component unmounts.

## Solution

The `bugSolution.js` file demonstrates the correct implementation, including a cleanup function to prevent memory leaks.  The cleanup function is responsible for calling `clearInterval` to stop the interval when the component is no longer needed.

## How to reproduce the bug

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the counter increasing every second.
5. Open the developer tools in your browser and check for memory leaks using your browser's performance tools. When you navigate away from the page, the interval will continue to run in the background, causing a memory leak.