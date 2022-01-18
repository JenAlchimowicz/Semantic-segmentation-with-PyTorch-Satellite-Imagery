# Semantic-segmentation-with-PyTorch-Satellite-Imagery
<!-- <a href="#"><img src="https://img.shields.io/badge/PyTorch-v1.9.0-red.svg?logo=PyTorch&style=for-the-badge" /></a>
<a href="#"><img src="https://img.shields.io/badge/python-v3.6+-blue.svg?logo=python&style=for-the-badge" /></a> -->
This project has been developed for Kaggle Competition organised by CentraleSupelec Deep Learning course.

Final ranking: 1st place

## Project description
The task was to utilise deep learning to perform semantic segmentation on satellite imagery. The training dataset consisted of 261 images taken by small UAV in the area of Houston, Texas to assess the damages after Hurricane Harvey. Each pixel was segmented to one of 25 classes such as roof, trees, road, swimming pool, vehicle or flooded (full list at the end of the file). Final score was calculated using the [Dice Coefficient](https://en.wikipedia.org/wiki/Sørensen–Dice_coefficient). The image below shows an example of an original image (left), corresponding mask (middle) and the model's prediction (right).

![Alt text](utils/segmentation_mask_example.png?raw=true "Title")

## Tags
Deep Learning, Semantic Segmentation, Satellite Imagery, UNet from scratch, custom DataLoaders, DeepLabv3+, PSPNet, Dice coefficient, Focal Loss, Transfer Learning

## Project in a nutshell:
1. Pre-processing I - new samples have been created for under represented classes
2. Pre-processing II - images and corresponding masks have been resized from 4000x3000 to 368x368 for faster processing
3. DataLoader - a custom implementation of DataLoaders allowed for uniform application of transformations (flips, rotations, altering brightness) to the images and corresponding masks
4. Model I - UNet has been built from scratch as a benchmark model
5. Model II - DeepLabv3+ architecture implemented from [segmentation models](https://github.com/qubvel/segmentation_models.pytorch) library
6. Model II - PSPNet architecture implemented from the same [segmentation models](https://github.com/qubvel/segmentation_models.pytorch) library
7. Training - models have been trained using Google Colab GPUs
  - Loss function - CrossEntropy or Focal Loss
  - Dynamic learning rate
  - Adam optimizer
  - Pre-trained encoder weights from imagenet
9. Evaluation - model performance was evaluated using Dice Score and Accuracy
10. Results - the best model, DeepLabv3+, achieved Dice Score of 0.775 on 112 test images

# Full list of classes
All classes in the dataset:
- 0: Background
- 1: Property Roof
- 2: Secondary Structure
- 3: Swimming Pool
- 4: Vehicle
- 5: Grass
- 6: Trees / Shrubs
- 7: Solar Panels
- 8: Chimney
- 9: Street Light
- 10: Window
- 11: Satellite Antenna
- 12: Garbage Bins
- 13: Trampoline
- 14: Road/Highway
- 15: Under Construction / In Progress Status
- 16: Power Lines & Cables
- 17: Water Tank / Oil Tank
- 18: Parking Area - Commercial
- 19: Sports Complex / Arena
- 20: Industrial Site
- 21: Dense Vegetation / Forest
- 22: Water Body
- 23: Flooded
- 24: Boat
