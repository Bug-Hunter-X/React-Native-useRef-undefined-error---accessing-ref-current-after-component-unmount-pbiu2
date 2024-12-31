# React Native useRef undefined Error

This repository demonstrates a common issue encountered when using the `useRef` hook in React Native: accessing `ref.current` after the component has unmounted.  The example showcases the problem and provides a solution to prevent the error.

## Problem

When a React Native component unmounts, its state and refs become invalid. Attempting to access `ref.current` from a callback (such as a `setTimeout` or an event handler) after the component has been unmounted will often result in an undefined value, causing errors.

## Solution

The solution involves using a cleanup function within the `useEffect` hook to ensure that any references to the ref are released before the component unmounts, preventing the error from occuring.