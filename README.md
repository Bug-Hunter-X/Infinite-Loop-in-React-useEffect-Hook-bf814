# React useEffect Infinite Loop Bug

This repository demonstrates a common error in React's `useEffect` hook: creating an infinite loop by modifying a dependency variable within the effect itself.

## Bug Description

The `MyComponent` component uses `useState` to track a `count` variable. The `useEffect` hook intends to increment the count, but incorrectly includes `count` as a dependency.  This creates an infinite loop because each update of `count` triggers another execution of the `useEffect` which again updates `count`, perpetuating the loop.

## Bug Solution

The solution involves carefully managing dependencies.  If the effect needs to be triggered only once after the component mounts, use an empty dependency array `[]`.

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the continuously incrementing counter and high CPU usage.