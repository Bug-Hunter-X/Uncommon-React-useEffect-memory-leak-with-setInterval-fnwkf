# Uncommon React useEffect Memory Leak with setInterval

This repository demonstrates a subtle memory leak in a React component that uses `setInterval` within a `useEffect` hook without proper cleanup.

The bug is that the `setInterval` function keeps running even after the component unmounts, leading to memory leaks. The solution involves using the return value of `useEffect` to clear the interval.

## Bug

The `bug.js` file contains the buggy component. The `setInterval` function continues to increment the count even after the component is unmounted, resulting in a memory leak and unpredictable behavior.

## Solution

The `bugSolution.js` file provides the corrected component. The `setInterval` is cleared using the return function of the `useEffect` hook.