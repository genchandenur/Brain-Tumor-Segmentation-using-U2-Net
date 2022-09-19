<p>
<h1 align="center">Brain Tumor-Segmentation using U<sup>2</sup>Net</h1>

    
</p>


[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1uoWpr5xInCuPNAo9EJB3OoPn4xdzwCtc?usp=sharing)

**Background:** The rate of people suffering from cancer is increasing day by day. Manual segmentation of brain tumors for cancer diagnosis from large volumes of MRI images generated in the clinical routine is a specialized, difficult and time-consuming task. Therefore, manual tumor segmentation is often fraught with intra-rater and inter-rater variability, resulting in imprecise boundary delimitation. Automated brain tumor image segmentation is needed.

**Goal:** Automatic brain tumor segmentation is an important task in medical image processing. Early diagnosis of brain tumors is important for clinical evaluation and treatment planning. U2-Net, a two-level nested U-structure architecture, was used for the brain tumor segmentation task in this repository.
    
## Overview
- [Dataset](#Dataset)
- [Data Augmentation](#Data-Augmentation)
- [Model Architecture](#Model-Architecture)
- [Training Process](#Training-Process)
- [Results](#Results)
- [References](#References)

### Dataset
The dataset used in this project was provided from the public collections of the [The Cancer Imaging Archive (TCIA)](https://www.cancerimagingarchive.net/). A dataset was created by combining 2 public collections.
1. This dataset contains T2-weighted and post-contrast T1-weighted images for each of the 159 subjects. Segmentation of tumors in three axial slices that include the one with the largest tumor diameter and ones below and above are provided in NiFTI format.

For a detailed information about the dataset please refer to this [site](https://wiki.cancerimagingarchive.net/display/Public/LGG-1p19qDeletion).

2. This dataset contains skull-stripped and co-registered multimodal (i.e. T1, T1-Gd, T2, T2-FLAIR) magnetic resonance imaging (MRI) volumes and both computer-aided and manually-corrected segmentation labels in NIfTI format for each of the 65 subjects. T1-weighted and T2-weighted MRI were included in this study.

For a detailed information about the dataset please refer to this [site](https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=24282668#24282668197861a846e445a795694ff2a50eb66c).

<p align="center">
<img src="images/dataset-images.png" height="500" />
</p>

### Data Augmentation

The basic data augmentation methods listed below were used:
- [Horizontally Flip](https://docs.opencv.org/3.4/d2/de8/group__core__array.html#gaca7be533e3dac7feb70fc60635adf441)
- [Vertically Flip](https://docs.opencv.org/3.4/d2/de8/group__core__array.html#gaca7be533e3dac7feb70fc60635adf441)

### Model Architecture

Model architecture is shown in the figure below. 
![Model Architecture](images/model_architecture.png)

### Training Process

The model was trained on Tesla P100 GPU offered by Google Colab Pro. Training took about 1 hour with **U2NETP** architecture and about 1 hour 30 minutes for **U2NET** architecture. 

The graphs show epoch-dice loss (left) and epoch-loss (right) over 100 epochs are given below for train (blue) and validation (red).

![](images/epoch_dice_loss.PNG)               ![](images/epoch_loss.PNG)

The graphs also show evaluation dice loss (left) per iteration and loss per iteration (right) over 100 epochs are given below.

![](images/evaluation_dice_loss_vs_iterations.PNG)               ![](images/evaluation_loss_vs_iterations.PNG)

#### Metrics
To quantify the performance of our image segmentation, **Dice Score** is used. The algorithm is validated by calculating the Dice score, which is a measure of how similar the objects are. So it is the size of the overlap of the two segmentations divided by the total size of the two objects. That is, the score for a particular class c is the size of the overlap between the predicted region and its true counterpart. 

<p align="center">
<img src="images/dice-score-formula.png" height="70" />
</p>



### Results
Some of the results are as follows.

- Download pre-trained U2NET models: [u2net.h5](https://drive.google.com/file/d/1fMtz5qBZ22nYv1E_6gymT4uMNK7L3qDO/view?usp=sharing)
- Download pre-trained U2NETP models: [u2netp.h5](https://drive.google.com/file/d/1NiXnHvNB-rtdDx7tkjyhJiYtcJ33Mzx1/view?usp=sharing)

.             |  .
:-------------------------:|:-------------------------:
![](images/1.png)  |  ![](images/2.png)
![](images/3.png)  |  ![](images/4.png)
![](images/5.png)  |  ![](images/6.png)
![](images/7.png)  |  ![](images/8.png)
![](images/9.png)  |  ![](images/10.png)
![](images/11.png)  |  ![](images/12.png)
![](images/13.png)  |  ![](images/14.png)

### References 
[U2-Net: Going Deeper with Nested U-Structure for Salient Object Detection](https://arxiv.org/abs/2005.09007v3)
