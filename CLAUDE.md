# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Khmer handwritten digit recognition — an image classification project for classifying handwritten Khmer numerals (0–9) using machine learning/deep learning. The primary development environment is a Jupyter notebook (`main.ipynb`).

## Dataset Structure

```
dataset/
├── train/   # 141 images across digits 0-9
├── valid/   # 41 images across digits 0-9
└── test/    # 21 images across digits 0,1,4,5,6,7,8,9 (missing classes 2 and 3)
```

Each split contains subdirectories named `0/` through `9/` (one per digit class). Images are JPEG files. The dataset is small (~203 images total), so data augmentation will likely be necessary.

## Running

Open `main.ipynb` in Jupyter Notebook, JupyterLab, or VS Code with the Jupyter extension. No build system or requirements file exists yet — dependencies should be installed manually (e.g., `pip install jupyter numpy pillow matplotlib` plus a framework like `tensorflow` or `torch`).

## Architecture Notes

- This is an early-stage project with an empty notebook and an organized dataset
- The dataset follows the standard `ImageFolder` convention (class label = subdirectory name), compatible with `torchvision.datasets.ImageFolder` or `tf.keras.utils.image_dataset_from_directory`
- The test set is missing digit classes 2 and 3 — account for this when evaluating
