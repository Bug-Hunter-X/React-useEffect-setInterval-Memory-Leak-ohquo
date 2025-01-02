# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving the use of `setInterval` within the `useEffect` hook without proper cleanup.  This leads to a memory leak because the interval continues to run even after the component unmounts.

## Bug Description
The `MyComponent` uses `setInterval` to update a counter every second.  However, it's missing the cleanup function in `useEffect` to stop the interval when the component unmounts. This results in the interval continuing to run, causing a memory leak.

## Solution
The solution involves using the return value of `useEffect` to implement a cleanup function that clears the interval when the component is unmounted.