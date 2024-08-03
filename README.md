# User Identification through Iris Features via Deep Convolutional Neural Networks

A more detailed description of the project with results is available in the [Report](./Report.pdf) file.


## Project Overview
This project aims to enhance iris recognition accuracy by integrating the Daugman method based on the Weighted Adaptive Hough Transform and Ellipsopolar Transform (WAHET) strategy with convolutional neural networks (CNNs), specifically using the EfficientNetB1 model for feature extraction and classification. 
It incorporates a reference to the work by Hafner A., et al. titled "Deep Iris Feature Extraction," published in 2021.

## Dataset
The CASIA-Iris Thousand dataset was used in this study. The CASIA-Iris-Thousand
dataset, developed by the Chinese Academy of Sciences' Institute of Automation (CASIA),
includes 20,000 photos of 1,000 people's iris. The photos were captured using an IKEMB-100
near-infrared (NIR) camera. Each participant submitted ten photographs of their left and ten
photographs of their right eyes. Notably, spectacles and mirror reflections appear in several of
the images, encouraging variation within each class. Two examples from the dataset are
illustrated in figure below.

<p align="center">
  <img src="https://github.com/YZ-26/User_Identification/assets/122618521/ee8ea6a2-242b-4402-9f35-1c719b43ed14" alt="User Identification Image">
</p>

## Methodology
### &nbsp;&nbsp;&nbsp;&nbsp;A. Preprocessing
The central emphasis of this project was on closed set recognition.
Drawing inspiration from the study presented in (Hafner et. al, 2021) I employed the
same WAHET (Weighted Adaptive Hough Transform and Ellipsopolar Transform) technique to
segment the irises from the eye images and normalize them to the size 64x256. I categorized the left and right irises of the same individual as a single class.
Consequently, my dataset, CASIA-Iris-Thousand, consists of 1000 classes corresponding to
1000 subjects. Furthermore, I opted for a combination of left and right iris images. Given that
each individual possesses 10 images for each of their left and right irises, I paired each left iris
image with a unique right iris image, making certain that the selected right iris image was not
matched with any other left iris image (one-to-one relationship). So, I stacked two copies of
this left iris image on the top, followed by two copies of the right iris image at the bottom receiving a size of 256x256. The
output of this preprocessing stage is shown in the figure below.

<p align="center">
  <img src="https://github.com/YZ-26/User_Identification/assets/122618521/6ef9b3d9-73e1-4dfb-bdf0-fd3b025422ed)" alt="Preprocessed image">
</p>

### &nbsp;&nbsp;&nbsp;&nbsp;B. Recognition
For the closed set recognition I utilized a pre-trained CNN model, particularly
EfficientNetB1. For the training and evaluation of my selected model on closed set recognition, we
randomly selected 750 subjects from a total of 1000 classes. Consequently, we adjusted the
final layer of EfficientNetB1 to have 750 outputs, adapting from its original configuration which,
being pre-trained on the ImageNet dataset, had 1000 outputs. Thus, the preprocessed irises are
inputted into the network, and the classes that correspond to the maximum value on the output
layers are assigned to the input irises. The proposed architecture of my model is shown in the
figure below.

![image](https://github.com/YZ-26/User_Identification/assets/122618521/35a6c314-b0cf-430d-a46e-db9c8b6ee90e)

## Notes
I have employed images already pre-segmented and treated with the WAHET transform to conserve time. They are available [here](https://drive.google.com/file/d/172GZgrAzNrA146BjFpF1vXtAH-zWymlA/view?usp=sharing).
