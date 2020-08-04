# Multi-modal product classification: Image visual features + Image textual fetaures

## Product detection as Image classification
From the given image dataset, we trained a 42-class Image classffier with ResNext_101_32x48d model pretrained on Imagenet dataset. Trained model can be downloaded from: 
https://drive.google.com/drive/u/1/folders/1UVnhpJOe0O5yESD473o43ZUfGF8VoXgx

Shopee Product Detection Challenge

Pre-trained model:

Classification accruacy (42 classees): *86.18%*

## Prodcut detection as Text classification
### Text detection and recognition
Significant images have text which can be identified using optical character recognition
We used:
1) Character-region awareness for text detection (CRAFT-PyTorch): https://github.com/clovaai/CRAFT-pytorch
2) Deep-text-recognition: https://github.com/clovaai/deep-text-recognition-benchmark

The above two repositories are merged to 1) identify text regions in an image, which futher is used to 2) detect text in the identified regions. The extracted text per image is combined to form a sentence. Doing this for all images will generate a new dataset consisting text (of an image) and its label (image product class). 

### Text classification
From the given text dataset, we formulate a text classification problem: 
- Input: Image text
- Output: Label representing product class

For this task, we fine-tune a *BERT* based classifier achieving *55%* accuracy. This is significant as compared to random baseline classifier giving ~2.38%. 

The pre-final layer BERT features can be downloaded from:
https://drive.google.com/drive/u/1/folders/1UVnhpJOe0O5yESD473o43ZUfGF8VoXgx

### Vision based Classification

### Fusion
The proper fusion of vision and text is expected to increase the performance. Please use both the datasets and see if it helps.
