# Android Classifier App

This folder contains an experimental binary classifier utilizing TensorFlow for Android
devices.

## Description

Inference is done using the TensorFlow Android Inference Interface,
which may be built separately if you want a standalone library to drop into your
existing application. Object tracking and YUV -> RGB conversion is handled by
libtensorflow_demo.so.

A device running Android 5.0 (API 21) or higher is required to run the demo due
to the use of the camera2 API, although the native libraries themselves can run
on API >= 14 devices.

## Current Classifier:

__Myco Detect__  
Uses the [Google Inception](https://arxiv.org/abs/1409.4842)
model to classify camera frames in real-time, displaying the top results
in an overlay on the camera image.

## Running the Demo

Once the app is installed it can be started via the "Myco Detect" ![Myco Detect](./res/drawable-mdpi/ic_launcher.png) icon.

While running the activities, pressing the volume keys on your device will
toggle debug visualizations on/off, rendering additional info to the screen
that may be useful for development purposes.

## Android Studio

Android Studio may be used to build the demo in conjunction with Bazel. First,
make sure that you can build with Bazel following the above directions. Then,
look at [build.gradle](build.gradle) and make sure that the path to Bazel
matches that of your system.

At this point you can add the `./android` directory as a new
Android Studio project. Click through installing all the Gradle extensions it
requests, and you should be able to have Android Studio build the demo like any
other application (it will call out to Bazel to build the native code with the
NDK).