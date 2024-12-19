# React useEffect Hook: Missing Dependency Leads to Infinite Loop

This repository demonstrates a common React bug caused by a missing dependency in the `useEffect` hook.  The `useEffect` hook is designed to perform side effects (like data fetching or logging) after component rendering.  However, if a dependency that changes in the component is missing from the dependency array, the effect runs repeatedly, causing unexpected behavior or even infinite re-renders.

## Bug Description

The provided `bug.js` file contains a `MyComponent` that uses `useEffect` to log the current count.  However, the `count` variable is not included in the dependency array of the `useEffect` hook.  This means that the effect will run on every render, regardless of whether `count` has changed, leading to an infinite loop.  The solution is to include `count` in the dependency array, so that the effect only runs when `count` is updated.