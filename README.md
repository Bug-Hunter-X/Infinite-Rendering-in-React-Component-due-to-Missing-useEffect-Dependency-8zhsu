# React Infinite Rendering Bug

This repository demonstrates a common React bug: infinite rendering caused by a missing dependency in the `useEffect` hook.  The `MyComponent` initially renders correctly but enters an infinite loop because the `useEffect` hook doesn't specify `count` as a dependency. This means the effect runs after every render, causing `setCount` to update `count` in an infinite cycle. 

## Bug

The `bug.js` file contains the buggy `MyComponent`. When you increment the counter, it causes the component to re-render endlessly. This issue can significantly impact app performance.  The console will be flooded with log messages indicating this behavior.

## Solution

The `bugSolution.js` file demonstrates the fix for this error. By adding `count` to the dependency array of the `useEffect` hook, the effect now only runs when `count` changes and the component renders correctly.