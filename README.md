# Fine-Tuning BLIP for Image Captioning

This project fine-tunes a pretrained BLIP (Bootstrapping Language-Image Pretraining) model for the task of generating descriptive captions for street-view images. Given a limited dataset of 95 images, we leverage transfer learning to adapt the model's language generation capabilities while freezing the vision encoder to prevent overfitting.

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)

## Overview

- **Approach:**  
  We use transfer learning to fine-tune the BLIP model. The vision encoder (including embeddings, transformer layers, and normalization) is frozen, while the text decoder and cross-modal attention layers are fine-tuned on our dataset.
  
- **Dataset:**  
  95 street-view images with associated caption annotations are used for training and validation.
  
- **Evaluation:**  
  We assess performance using loss curves along with external metrics: BLEU, METEOR, and CIDEr.


## Installation

This project requires Python 3.7+ along with several libraries. You can install the dependencies as follows:

### Using `pip`

Install the required packages with:
```bash
pip install torch torchvision transformers datasets pillow nltk
```

Since the project uses the pycocoevalcap library for CIDEr score calculation (which is not available on PyPI), install it directly from GitHub:

```bash
pip install git+https://github.com/salaniz/pycocoevalcap.git
```

## Usage 

- **Data Preparation**
  Place your street-view images in a dedicated folder
  Create a JSON file (e.g., image_captions.json) with entries formatted as:
  ```js
  [
  {
    "image": "G0302024.JPG",
    "captions": [
      "a photo of a street with a motorcycle parked on the side of the road"
    ]
  },
  {
    "image": "G0394874.JPG",
    "captions": [
      "a motorcycle parked on the side of a road"
    ]
  },
  {
    "image": "G0488439.JPG",
    "captions": [
      "a street in a small town with a motorcycle parked on both sides of the road"
    ]
  }
  ]

BLIP_Model.ipynb is the main file containing all the codes for this project.
