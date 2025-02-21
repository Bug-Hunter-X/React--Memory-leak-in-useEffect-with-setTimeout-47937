# React UseEffect setTimeout Memory Leak

This repository demonstrates a common error in React applications involving the improper use of `setTimeout` within the `useEffect` hook.  The provided code showcases a memory leak due to the absence of a cleanup function. The solution shows how to properly clean up the `setTimeout` to prevent the leak.

## Bug

The primary issue is within the `MyComponent` component.  The `useEffect` hook sets up a `setTimeout` that increments a counter. However, this `setTimeout` is not cleaned up, leading to multiple timers running and causing a memory leak.

## Solution

The solution addresses this by using the return value of `useEffect` to implement a cleanup function. This cleanup function clears the `setTimeout` before the component unmounts or when the effect is replaced with a new one.