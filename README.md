# Fine-Tuning BLIP for Image Captioning

This project fine-tunes a pretrained BLIP (Bootstrapping Language-Image Pretraining) model for the task of generating descriptive captions for street-view images. Given a limited dataset of 95 images, we leverage transfer learning to adapt the model's language generation capabilities while freezing the vision encoder to prevent overfitting.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Results](#results)
- [Notes and Future Work](#notes-and-future-work)
- [Acknowledgements](#acknowledgements)

## Overview

- **Approach:**  
  We use transfer learning to fine-tune the BLIP model. The vision encoder (including embeddings, transformer layers, and normalization) is frozen, while the text decoder and cross-modal attention layers are fine-tuned on our dataset.
  
- **Dataset:**  
  95 street-view images with associated caption annotations are used for training and validation.
  
- **Evaluation:**  
  We assess performance using loss curves along with external metrics: BLEU, METEOR, and CIDEr.

## Features

- Fine-tuning a state-of-the-art vision-language model (BLIP) on a small, domain-specific dataset.
- Custom data loader and transformation pipeline using PyTorch.
- Evaluation of generated captions with BLEU, METEOR, and CIDEr metrics.
- Visualization of sample predictions on the validation set.
- Options to freeze specific layers to mitigate overfitting.

## Installation

This project requires Python 3.7+ along with several libraries. You can install the dependencies as follows:

### Using `pip`

Install the required packages with:
```bash
pip install torch torchvision transformers datasets pillow nltk
