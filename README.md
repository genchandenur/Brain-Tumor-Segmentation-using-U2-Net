# Brain-Tumor-Segmentation-using-U2-Net



## Overview
- [Dataset](#Dataset)
- [Pre-processing](#Pre-processing)
- [Model Architecture](#Model-Architecture)
- [Training Process](#Training-Process)
- [Results](#Results)
- [Usage](#Usage)
- [References](#References)

### Dataset
The dataset used in this project was provided from the public collections of the [The Cancer Imaging Archive (TCIA)](https://www.cancerimagingarchive.net/).
This dataset contains T2-weighted and post-contrast T1-weighted images for each of the 159 subjects. Segmentation of tumors in three axial slices that include the one with the largest tumor diameter and ones below and above are provided in NiFTI format.

For a detailed information about the dataset please refer to this [site](https://wiki.cancerimagingarchive.net/display/Public/LGG-1p19qDeletion).

| Parameters  | Dice_ET | Dice_WT | Dice_TC | Sensitivity_ET | Sensitivity_WT | Sensitivity_TC | Specificity_ET | Specificity_WT  |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |  | 
| Mean  | 0.80661  | 0.89414  | 0.85721  | 0.81519  | 0.9251  | 0.84795  | 0.99971  |  
| StdDev  | 0.23953  | 0.08177  | 0.12749  | 0.25155  | 0.07596  | 0.16678  | 0.00043  |
| Median  | 0.87871  | 0.91993  | 0.91058  | 0.89553  | 0.94956  | 0.90561  | 0.99985  |
| 25quantile  | 0.80214  | 0.87042  | 0.82128  | 0.82766  | 0.90596 | 0.81328  | 0.99957  |
| 75quantile  | 0.92648  | 0.94299  | 0.93417  | 0.94811  | 0.97373 | 0.95586  | 0.99996  |


### Pre-processing

The basic data augmentation methods listed below were used:
- [Horizontally Flip](https://docs.opencv.org/3.4/d2/de8/group__core__array.html#gaca7be533e3dac7feb70fc60635adf441)
- [Vertically Flip](https://docs.opencv.org/3.4/d2/de8/group__core__array.html#gaca7be533e3dac7feb70fc60635adf441)

### Model Architecture

![Model Architecture](images/model_architecture.png)

### References 
[Original Paper](https://arxiv.org/abs/2005.09007v3)
