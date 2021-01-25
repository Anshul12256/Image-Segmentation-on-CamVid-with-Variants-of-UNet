# Image Segmentation on CamVid with Variants of U-Net
  - This repository contains implementations of different U-Net [1] models for semantic segmentation of images on the CamVid [4] dataset. 
 - The Jupyter notebooks are executed on the online Google Colab environment. 

## U-Net Architecture

![Architecture of U-net](https://lmb.informatik.uni-freiburg.de/Publications/2015/RFB15a/u-net-architecture.png)

## Results

The Jupyter notebooks contains implementations from all the above mentioned files ([2], [3], [5]) and modifies them in order to achieve better results on the CamVid dataset.

 - Small U-Net: 16->32->64->128->256->128->64->32->16
 - U-Net: 64->128->256->512->1024->512->256->128->64
 - Extended U-Net: 16->32->64->128->256->512->1024->512->256->128->64->32->16

| Models | Validation IOU Score | Validation Accuracy |Epochs| Parameters|
|:-:|:-:|:-:|:-:|:-:|
| Small U-Net + ReLU |  52.74 % | 88.83 % | 77|1,941,632|
| Small U-Net + Leaky ReLU |54.38 %  | 89.58 % | 72|1,941,632|
| U-Net + ReLU |52.60 | 89.70 | 81 | 31,197,600 |
| Extended U-Net + ReLU | 54.50 | 89.91  | 84 |31,274,368 |
| Extended U-Net + ReLU + Dropout | 54.32 | 89.60 | 57 |31,274,368 |            

### Takeaways:
- Small U-Net + LeakyReLU is the best performing model in the Accuracy vs. Model size trade-off.
- Small U-Net models are ~93 % smaller in size than the U-Net and the Extended U-Net models and have near about same performance as those models.
- Extended U-Net has a 3% better IOU score than the standard U-Net model.

## References
<a id="1">[1]</a> O. Ronneberger and P.Fischer and T. Brox, 
U-Net: Convolutional Networks for Biomedical Image Segmentation - Medical Image Computing and Computer-Assisted Intervention (MICCAI),
http://lmb.informatik.uni-freiburg.de/Publications/2015/RFB15a

<a id="1">[2]</a> **IOU Score Implementation:**
Pavel Yakubovskiy,
Segmentation Models - GitHub,
https://github.com/qubvel/segmentation_models

<a id="1">[3]</a> **Data Parsing:**
Mukul Kumar,
https://www.kaggle.com/mukulkr/camvid-segmentation-using-unet

<a id="1">[4]</a> **CamVid Dataset:**
Brostow, Shotton, Fauqueur, Cipolla,
Segmentation and Recognition Using Structure from Motion Point Clouds, ECCV 2008

Brostow, Fauqueur, Cipolla
Semantic Object Classes in Video: A High-Definition Ground Truth Database  
http://mi.eng.cam.ac.uk/research/projects/VideoRec/CamVid

Can aslo be downloaded through Kaggle - https://www.kaggle.com/carlolepelaars/camvid

<a id="1">[5]</a> **Model Implementation Refrence:**
Abhinav Sagar
https://gist.github.com/abhinavsagar/fe0c900133cafe93194c069fe655ef6e

