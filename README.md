# Diabetic Retinopathy Detection Using Deep Learning

## Abstract
Diabetic Retinopathy (DR) is a severe eye condition caused by diabetes, leading to blindness if not diagnosed and treated early. Timely detection is critical but often challenging due to the manual, time-consuming diagnostic process. To address this, I developed a deep learning-based solution leveraging Convolutional Neural Networks (CNNs) to automate the detection process using fundus images. Utilizing publicly available datasets and EfficientNet models pretrained with ImageNet weights, my approach achieved a maximum accuracy of **87.66%** for binary classification (DR or No DR) and **53.39%** for multi-class classification, significantly aiding healthcare professionals.

---

## Project Motivation
Diabetic Retinopathy is a growing global health concern, with the prevalence of diabetes expected to increase substantially in both developed and developing nations by 2030. The manual process of DR diagnosis is resource-intensive and prone to human error, making it insufficient to meet the rising demand for ophthalmic care. This project was inspired by my desire to improve diagnostic efficiency, accuracy, and accessibility through cutting-edge deep learning techniques.

---

## Datasets and Preprocessing

### Training Dataset
I used the **2015 Diabetic Retinopathy Detection dataset** from Kaggle, containing **35,127 fundus images** labeled into five classes:  
- **Label 0**: No DR  
- **Label 1**: Mild DR  
- **Label 2**: Moderate DR  
- **Label 3**: Severe DR  
- **Label 4**: Proliferative DR  

| Label | Level of DR           | Number of Images |
|-------|------------------------|------------------|
| 0     | No DR                 | 25,810           |
| 1     | Mild                  | 5,292            |
| 2     | Moderate              | 2,443            |
| 3     | Severe                | 873              |
| 4     | Proliferative DR      | 708              |

[Link to Training Dataset](https://www.kaggle.com/competitions/diabetic-retinopathy-detection/data)

![image](https://github.com/user-attachments/assets/3a0a843b-6aef-4ff9-ad0a-74fd656e049f)

The training dataset included images captured with cameras of varying aspect ratios, which caused some images to have significant black regions that were irrelevant for prediction. Additionally, the images lacked uniformity in shape and size. To overcome these challenges, I applied preprocessing techniques to standardize the dataset and ensure consistency across all images. Using the albumentations library, I also performed image augmentation to enhance normalization and improve the model’s performance. The processed outcomes are displayed below:

![image](https://github.com/user-attachments/assets/90526043-2667-4c37-bb59-f4815ad92360)


### Test Dataset
I used the **2019 APTOS Blindness Detection dataset** for testing, with **3,663 fundus images** labeled similarly to the training dataset.  
[Link to Test Dataset](https://www.kaggle.com/competitions/aptos2019-blindness-detection/)

### Preprocessing
- Removed irrelevant black regions from fundus images.
- Standardized image shapes using the albumentations library.
- Applied image augmentation techniques for dataset normalization.

---

## Methodology
1. **Model Architecture**: Convolutional Neural Networks (CNNs) with EfficientNet as the backbone.
2. **Transfer Learning**: Pretrained ImageNet weights were utilized for initializing the model.
3. **Model Variants**: EfficientNet-B2, B3, and B4 were tested.  
   - **EfficientNet-B3** performed best for binary classification (DR or No DR).  
   - **EfficientNet-B2** achieved the highest accuracy for multi-class classification.
4. **Training Platform**: Google Colab was used to train and optimize the models.

EfficientNet, known for its scalability and state-of-the-art performance, proved effective in both binary and multi-class classification tasks.

---

## Results
- **Binary Classification (DR or No DR)**:  
  - Best Accuracy: **87.66%** (EfficientNet-B3)
- **Multi-class Classification (Levels of DR)**:  
  - Best Accuracy: **53.39%** (EfficientNet-B2)
![image](https://github.com/user-attachments/assets/3a0753d9-d938-4677-b5c9-e4c3587a42ff)

---

## Discussion
The results demonstrate the potential of deep learning in automating DR detection. While binary classification accuracy was high, multi-class classification results indicate scope for improvement through hyperparameter optimization and dataset balancing.

---

## Conclusion
This project successfully leveraged CNNs to automate the detection of Diabetic Retinopathy, significantly reducing the reliance on manual diagnostics. The achieved accuracy highlights the practicality of deep learning in improving ophthalmic care. Future work will focus on optimizing model performance and extending the approach to other ophthalmic diseases.

---

## Technologies Used
- **Deep Learning Framework**: TensorFlow/Keras
- **Architecture**: EfficientNet (B2, B3, B4)
- **Preprocessing**: albumentations library
- **Platform**: Google Colab
- **Programming Language**: Python
- **Datasets**: Kaggle (2015, 2019)

---

## Resources
- **Dataset Links**:  
  - [2015 Diabetic Retinopathy Detection](https://www.kaggle.com/competitions/diabetic-retinopathy-detection/data)  
  - [2019 APTOS Blindness Detection](https://www.kaggle.com/competitions/aptos2019-blindness-detection/)  
- **EfficientNet Research**:  
  - [Paper](https://arxiv.org/abs/1905.11946)  
