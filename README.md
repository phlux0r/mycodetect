# Overview

This repo is a fork of the code for the
["TensorFlow for poets 2" codelab](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets-2) adapted to perform a binary classification.

The code is adapted to provide a mycological classifier that can be used as an educational tool to provide a binary classification of `Active` and `Not Active` for a given specimen. You can take a guess on what _'active'_ means :).

__Please note that this is highly experimental and should not be used as an authoritative classification tool.__

# Making the project

The android project is in `/android`. Just load it into Android Studio and run. You can use the gradle build file also.

## Training the Classifier

Use the approach from the ["TensorFlow for poets" codelab](https://codelabs.developers.google.com/codelabs/tensorflow-for-poets) to train your classifier.
The images should be put into a structure like so:

    images/  
    |-----/Active/...  
    |-----/Not Active/...

The current version has been trained on 505 active and 760 not active images with 4000 training cycles. The accuracy is about 80-90%.
Accuracy can be improved by training on a much larger image set, therefore the ongoing effort would be to keep adding images to the set, especially the active set.

Currently, in real use, the classifier will report a significant number of false positives and some false negatives.

# Content

The `scripts` directory contains the original helpers to compact the Tensorflow Classification Model that is generated by the classfier training.
The compacted model and labels are put into the android/assets/ folder.

# Use

Start app, point camera to a specimen, read the probablilities.

