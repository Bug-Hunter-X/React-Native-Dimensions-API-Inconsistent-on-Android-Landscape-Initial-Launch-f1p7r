# React Native Dimensions API Inconsistent on Android Landscape Initial Launch

This repository demonstrates a bug related to the `Dimensions` API in React Native. On Android devices, when the application is launched in landscape orientation for the first time, the `Dimensions.get('window')` method may return incorrect dimensions (flipped or zero values). Subsequent orientation changes typically fix the issue.

## Bug Description:
The `Dimensions.get('window')` API returns incorrect screen width and height values on the first landscape launch on some Android devices.  This results in layout issues and incorrect rendering in the application.

## Reproduction Steps:
1. Run the provided example application on an Android device (emulator or physical device).
2. Launch the app in landscape orientation.
3. Observe that the dimensions reported by `Dimensions.get('window')` are likely incorrect.
4. Rotate the device to portrait and then back to landscape.  The values should now be correct.

## Solution:
The provided solution uses `Dimensions.addEventListener` to listen for changes in screen orientation and dimensions.  While not ideal, it handles cases where the initial dimensions are wrong and ensures that the dimensions are always correct after the initial screen orientation event.

## How to use:
1. Clone the repository.
2. Navigate into the cloned directory using the command line.
3. Run `npm install` to install the necessary packages.
4. Run `npx react-native run-android` to run the application on an Android device.
