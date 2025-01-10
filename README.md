# Expo Linking.getInitialURL() Inconsistently Returns Null on Android

This repository demonstrates a bug in Expo's `Linking.getInitialURL()` function on Android.  The function intermittently returns `null`, even when the app is launched via a deep link. This inconsistency makes deep link handling unreliable and leads to unexpected application behavior.

## Bug Description

The `Linking.getInitialURL()` function, intended to retrieve the initial URL used to launch the application, sporadically returns `null` on Android devices. This behavior is inconsistent and unpredictable, making it challenging to implement robust deep link functionality. 

## Reproduction

1. Clone this repository.
2. Run the app on an Android emulator or device.
3. Try launching the app using a deep link.  Observe that `getInitialURL()` sometimes returns the expected URL and other times returns `null`.

## Solution

The provided solution employs a retry mechanism with a small delay. This approach attempts to retrieve the URL multiple times before giving up. While it doesn't solve the root cause, it significantly improves the reliability of deep link handling.

## Potential Causes

The exact cause of this inconsistent behavior is unclear. It could be related to underlying Android system limitations or interactions with other Expo modules. 