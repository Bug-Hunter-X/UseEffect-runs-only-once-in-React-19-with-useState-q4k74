# React useEffect Hook Runs Only Once

This repository demonstrates a common error in React 19 where the `useEffect` hook only runs once instead of after every render when used with `useState`.  The issue arises from incorrectly specifying the dependency array in `useEffect`.

## Problem

The provided `MyComponent` uses `useState` to track a count.  A `useEffect` hook is added to log the count to the console after each update. However, the `useEffect` only logs the initial count (0) even when the button is clicked and the count updates. This is because the `count` is missing from the dependency array.

## Solution

The solution is to correctly specify the dependencies in the `useEffect`'s second argument. By adding `count` to the dependency array, the effect will re-run whenever `count` changes.

## How to reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe that the console log only prints the initial count (0) even after multiple clicks.
5. Uncomment the solution to see that the log now prints every updated count.
