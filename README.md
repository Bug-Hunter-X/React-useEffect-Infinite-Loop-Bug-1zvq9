# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: an infinite loop caused by an incorrectly specified dependency array.

## Bug Description

The `useEffect` hook is used to perform side effects after a component renders.  However, if the dependency array is missing or incomplete, the effect can trigger continuously, leading to an infinite loop and potentially crashing the application.

In this example, the `count` variable is updated within the effect, but `count` is not included in the `useEffect`'s dependency array. This means the effect runs after every render, regardless of whether `count` has changed, causing an infinite loop.

## Solution

The solution is to correctly specify the dependencies in the `useEffect` hook. By including `count` in the dependency array `[count]`, the effect only runs when the `count` variable changes.