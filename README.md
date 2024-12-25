# React 19 useEffect Cleanup Function Issue

This repository demonstrates a problem with the useEffect cleanup function in React 19.  The cleanup function, intended to run before component unmount, is not consistently called under certain circumstances (e.g., rapid state changes or nested unmounts).  The solution demonstrates a workaround using a ref to ensure proper cleanup.

## Problem Description

The original `MyComponent` uses `useEffect` with a cleanup function.  However, in certain scenarios, particularly when the component unmounts quickly, the cleanup function ('Component unmounting...') may not be logged to the console. This indicates that the cleanup function isn't being executed, potentially leading to memory leaks or other issues.

## Solution

The solution involves using a `useRef` hook to manage the cleanup function and ensure it is executed regardless of timing or other factors affecting component unmount.

## How to reproduce the bug

1. Clone the repo.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console logs.  The lack of consistent 'Component unmounting...' logs signals the bug.
5. Check the solution component for a corrected implementation.