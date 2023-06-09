# Melanoma Detection Project
> Problem statement: To build a CNN based model which can accurately detect melanoma. Melanoma is a type of cancer that can be deadly if not detected early. It accounts for 75% of skin cancer deaths. A solution which can evaluate images and alert the dermatologists about the presence of melanoma has the potential to reduce a lot of manual effort needed in diagnosis.

**Data Summary:**

The dataset consists of 2357 images of malignant and benign oncological diseases, which were formed from the International Skin Imaging Collaboration (ISIC). All images were sorted according to the classification taken with ISIC, and all subsets were divided into the same number of images, with the exception of melanomas and moles, whose images are slightly dominant.

The data set contains the following diseases:
1. Actinic keratosis
2. Basal cell carcinoma
3. Dermatofibroma
4. Melanoma
5. Nevus
6. Pigmented benign keratosis
7. Seborrheic keratosis
8. Squamous cell carcinoma
9. Vascular lesion

**Project Pipeline**

- Data Reading/Data Understanding → Defining the path for train and test images 
- Dataset Creation→ Create train & validation dataset from the train directory with a batch size of 32. Also, make sure you resize your images to 180*180.
- Dataset visualisation → Create a code to visualize one instance of all the nine classes present in the dataset 
- Model Building & training : 
    - Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model, rescale images to normalize pixel values between (0,1).
    - Choose an appropriate optimiser and loss function for model training
    - Train the model for ~20 epochs
    - Write your findings after the model fit. You must check if there is any evidence of model overfit or underfit.
- Chose an appropriate data augmentation strategy to resolve underfitting/overfitting 
- Model Building & training on the augmented data :
    - Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model rescale images to normalize pixel values between (0,1).
    - Choose an appropriate optimiser and loss function for model training
    - Train the model for ~20 epochs
    - Write your findings after the model fit, see if the earlier issue is resolved or not?
- Class distribution: Examine the current class distribution in the training dataset 
    - Which class has the least number of samples?
    - Which classes dominate the data in terms of the proportionate number of samples?
- Handling class imbalances: Rectify class imbalances present in the training dataset with Augmentor library.
- Model Building & training on the rectified class imbalance data :
    - Create a CNN model, which can accurately detect 9 classes present in the dataset. While building the model, rescale images to normalize pixel values between (0,1).
    - Choose an appropriate optimiser and loss function for model training
    - Train the model for ~30 epochs
    - Write your findings after the model fit, see if the issues are resolved or not?

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
- General Information:
The project focuses on developing a CNN-based model for accurate melanoma detection. It aims to address the rising incidence of melanoma, a deadly form of skin cancer, by automating the detection process using deep learning techniques. The project utilizes a dataset of skin images obtained from the International Skin Imaging Collaboration (ISIC) to train and evaluate the model.

- Background:
Melanoma is a significant health concern, accounting for a large portion of skin cancer-related deaths. Early detection plays a vital role in improving patient outcomes. The project leverages the power of deep learning and computer vision to build a model capable of accurately detecting melanoma. By combining advanced algorithms with dermatological expertise, the project aims to enhance the efficiency and accuracy of melanoma diagnosis.

- Business Problem:
The primary business problem addressed by the project is the labor-intensive and subjective nature of melanoma diagnosis. Traditional diagnosis methods rely on visual inspection by dermatologists, which can be time-consuming and prone to human error. The project aims to automate the detection process, providing a tool that can evaluate skin images and alert dermatologists about the presence of melanoma. By reducing manual effort and facilitating early detection, the project has the potential to save lives and improve patient outcomes.

- Dataset:
The project utilizes a dataset obtained from the International Skin Imaging Collaboration (ISIC). This dataset consists of 2,357 images representing various oncological diseases, including melanoma, as well as benign and malignant skin conditions. The images are labeled with nine different classes, such as actinic keratosis, basal cell carcinoma, dermatofibroma, melanoma, nevus, pigmented benign keratosis, seborrheic keratosis, squamous cell carcinoma, and vascular lesion. The dataset provides the necessary information for training and evaluating the CNN model for accurate melanoma detection.

## Conclusions
- We can easily notice that the model is overfitting since overfitting is computed in relation to loss, and there is a change in loss functions between training and testing.
- Because there are enough features to remember the pattern and the neural network is extremely young (only 20 epochs), learning has only just begun, the accuracy is about 70%.
- After compiling the model using Adam optimizer, there is no much improvements in accuracy from the initial model. However, it's notiable that the overfitting issue fading away due to data augmentation.
- The distribution of classes in the training dataset:
    - Seborrheic keratosis has the least number of samples
    - Pigmented benign keratosis dominate the data in terms proportionate number of samples
- Rectify the class imbalance by using Augmentor:
    - The class rebalancing assisted in lowering data overfitting and therefore the loss. However, it had a negligible effect on accuracy.
    - We first attempted without the ImageDataGenerator, which resulted in data that was overfit at a high ratio. Then we added dropout and ImageDataGenerator, which minimized overfitting. Finally, we attempted Batch Normalization and Augumentation, which was quite beneficial in terms of carry forward.

## Technologies Used
- TensorFlow 2.6.0.
- Matplotlib 3.4.3.
- NumPy 1.21.2.
- Pandas 1.3.3.
- Pillow 8.3.2.
- Keras 2.6.0.
- Augmentor 0.2.8.

## Contact
Created by [@lukengo3008] - feel free to contact me!
