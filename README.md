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

                           | T1-weighted Image          |  T2-weighted Image        |  Mask Image
:-------------------------:|:-------------------------:|:-------------------------:
Oligoastrocytoma           |![](images/README/dataset_example.png)  |  ![](images/README/dataset_example_mask.png)
Oligodendroglioma          |
Astrocytoma                |

### Pre-processing

The basic data augmentation methods listed below were used:
- [Horizontally Flip](https://docs.opencv.org/3.4/d2/de8/group__core__array.html#gaca7be533e3dac7feb70fc60635adf441)
- [Vertically Flip](https://docs.opencv.org/3.4/d2/de8/group__core__array.html#gaca7be533e3dac7feb70fc60635adf441)

### Model Architecture

![Model Architecture](images/model_architecture.png)

### References 
[Original Paper](https://arxiv.org/abs/2005.09007v3)
