# React Native AsyncStorage TypeError: Cannot read properties of null (reading 'then')

This repository demonstrates a common error encountered when using AsyncStorage in React Native: a TypeError when attempting to access a property of null because the key being retrieved does not exist.

The `bug.js` file contains the problematic code, while `bugSolution.js` provides a corrected version that handles the case where the key is not found.

## Problem

The issue arises from directly chaining `.then()` onto the promise returned by `AsyncStorage.getItem()`. If the key does not exist, the promise resolves to `null`, and attempting to call `.then()` on `null` throws a TypeError.

## Solution

The solution involves checking if the retrieved value is null before attempting to access its properties or use conditional rendering based on its existence.  The corrected code handles the null case gracefully.

## How to reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run the app on an emulator or physical device.  Observe the error in `bug.js`. 
4. Switch to the fixed code in `bugSolution.js` to see the correct behavior.