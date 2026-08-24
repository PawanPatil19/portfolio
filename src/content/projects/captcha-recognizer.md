---
title: 'Captcha Recognizer'
description: 'A computer-vision experiment that segments CAPTCHA characters and trains a CNN to recognize letters and digits.'
pubDate: 'Sep 06 2024'
stack: ['Python', 'OpenCV', 'TensorFlow', 'Keras', 'Jupyter']
github: 'https://github.com/PawanPatil19/captcha-recognizer'
featured: false
---

An exploration of the full CAPTCHA-recognition pipeline, from isolating individual characters to training a model that classifies 26 letters and 10 digits.

## The pipeline

- Experimented with color-space, thresholding, contour, and watershed-based segmentation in Jupyter notebooks
- Normalized extracted characters into 40 × 40 grayscale inputs
- Trained a convolutional neural network with data augmentation, batch normalization, and learning-rate scheduling
- Stored the trained model and label mapping for repeatable inference

## What I learned

The classifier is only one part of the problem. Reliable character segmentation and consistent preprocessing have an equally large effect on end-to-end recognition quality.
