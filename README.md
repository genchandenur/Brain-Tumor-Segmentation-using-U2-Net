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

| Parameters  | Sensitivity_ET | Sensitivity_WT | Sensitivity_TC | Specificity_ET | Specificity_WT | Specificity_TC | Hausdorff95_ET | Hausdorff95_WT | Hausdorff95_TC |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | 
| Mean  | 0.81519  | 0.9251  | 0.84795  | 0.99971  | 0.99884  | 0.99953  | 23.1904  | 5.56554  | 5.44695  |
| StdDev  | 0.25155  | 0.07596  | 0.16678  | 0.00043  | 0.00116  | 0.0007  | 85.62448  | 10.87704  | 9.90171  |
| Median  | 0.89553  | 0.94956  | 0.90561  | 0.99985  | 0.99918  | 0.9998  | 1.73205 | 3.16228  | 3  |
| 25quantile  | 0.82766  | 0.90596 | 0.81328  | 0.99957  | 0.99858  | 0.9995  | 1  | 2.23607  | 1.73205  |
| 75quantile  | 0.94811  | 0.97373 | 0.95586  | 0.99996  | 0.99958  | 0.9999  | 3  | 5.47723  | 5.47723  |



### Pre-processing

The basic data augmentation methods listed below were used:
- [Horizontally Flip](https://docs.opencv.org/3.4/d2/de8/group__core__array.html#gaca7be533e3dac7feb70fc60635adf441)
- [Vertically Flip](https://docs.opencv.org/3.4/d2/de8/group__core__array.html#gaca7be533e3dac7feb70fc60635adf441)

### Model Architecture

![Model Architecture](images/model_architecture.png)

### References 
[Original Paper](https://arxiv.org/abs/2005.09007v3)
