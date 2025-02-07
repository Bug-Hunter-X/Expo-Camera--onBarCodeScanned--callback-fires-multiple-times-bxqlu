# Expo Camera Multiple Barcode Scan Issue

This repository demonstrates a bug in Expo's `Camera` component where the `onBarCodeScanned` callback fires multiple times for a single barcode scan. This issue occurs when scanning barcodes rapidly, leading to data duplication or unexpected behavior.

## Problem

The `onBarCodeScanned` callback is triggered multiple times for one barcode scan. This is likely due to a race condition within Expo's internal handling of barcode scanning events.

## Solution

The provided solution implements a debounce mechanism to prevent the callback from firing multiple times within a short period.  This ensures that only one scan event is processed, resolving the data duplication issue.

## Reproduction

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `expo start` to start the Expo development server.
4. Scan a barcode multiple times in quick succession to observe the multiple triggers in the original `bug.js` file. Then compare with the fix in `bugSolution.js`.