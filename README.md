
## Abstract

We have performed semantic segmentation on Dubai's Satellite Imagery Dataset by using transfer learning on an InceptionResNetV2 encoder-based UNet CNN model.
In order to artificially increase the amount of data and avoid overfitting, We preferred using data augmentation on the training set.
The model has achieved ~81% dice coefficient and ~86% accuracy on the validation set.

Dataset Link: https://www.kaggle.com/datasets/humansintheloop/semantic-segmentation-of-aerial-imagery

Model Link: https://drive.google.com/file/d/1Y5yWuJVVVFAnKjsC6z_RRxf1z955eH0D/view

## Approach


### Data Augmentation using Albumentations Library

<p align="justify">
<a href="https://albumentations.ai/">Albumentations</a>  is a Python library for fast and flexible image augmentations. Albumentations efficiently implements a rich variety of image transform operations that are optimized for performance, and does so while providing a concise, yet powerful image augmentation interface for different computer vision tasks, including object classification, segmentation, and detection.
</p>

<p align="justify">
There are only 72 images (having different resolutions) in the dataset, out of which I have used 56 images (~78%) for training set and remaining 16 images (~22%) for validation set. It is a very small amount of data, in order to artificially increase the amount of data and avoid overfitting, I preferred using data augmentation. By doing so I have increased the training data upto 9 times. So, the total number of images in the training set is 504 (56+448), and 16 (original) images in the validation set, after data augmentation.
</p>

Data augmentation is done by the following techniques:

- Random Cropping
- Horizontal Flipping
- Vertical Flipping
- Rotation
- Random Brightness & Contrast
- Contrast Limited Adaptive Histogram Equalization (CLAHE)
- Grid Distortion
- Optical Distortion
