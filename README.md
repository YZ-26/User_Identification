# User Identification through Iris Features via Deep Convolutional Neural Networks

## Project Overview
This project aims to enhance iris recognition accuracy by integrating the Daugman method with convolutional neural networks (CNNs), specifically using the EfficientNetB1 model for feature extraction and classification. 

## Dataset
We use the CASIA-Iris Thousand dataset, containing 20,000 iris images from 1,000 subjects, captured with near-infrared technology.

## Methodology
Our approach involves preprocessing iris images using the WAHET technique, employing EfficientNetB1 for its efficiency and accuracy, and fine-tuning the model for closed set recognition.

## Model Architecture
Below is the architecture of the EfficientNetB1 model adapted for iris recognition. For a detailed view, see the architecture diagram included in the repository.

![image](https://github.com/YZ-26/User_Identification/assets/122618521/35a6c314-b0cf-430d-a46e-db9c8b6ee90e)


## Training and Evaluation
The model is trained on a segmented portion of the dataset, utilizing the Adam optimizer and categorical cross-entropy loss, with a focus on achieving high accuracy in closed set recognition.

## Results
Our implementation achieves notable accuracy, demonstrating the potential of combining traditional iris recognition methods with advanced CNN models for biometric identification.

## Future Work
Further research will explore enhancing the algorithm and expanding to open set recognition capabilities.

## How to Use
Before using download the segmented Iris images from the shared folder of the ...........
