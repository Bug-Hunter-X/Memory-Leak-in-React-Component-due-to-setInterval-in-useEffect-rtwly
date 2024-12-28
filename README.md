# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications: memory leaks caused by the improper use of `setInterval` within the `useEffect` hook.  The `setInterval` function, without proper cleanup, continues running even after the component is unmounted, potentially leading to memory leaks and performance issues.

## Bug Description
The provided `MyComponent` uses `setInterval` to update the count every second. However, it fails to clear the interval when the component unmounts, resulting in a persistent interval that continues consuming resources even after the component is no longer rendered.

## Solution
The solution involves adding a cleanup function to the `useEffect` hook. This function is responsible for clearing the interval using `clearInterval` before the component unmounts, preventing the memory leak.