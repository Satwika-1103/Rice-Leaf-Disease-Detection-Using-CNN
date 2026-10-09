# Rice Leaf Disease Detection Using Deep Learning

## Project Overview

This project uses deep learning and transfer learning to classify rice leaf images into three disease categories: **Bacterial Leaf Blight, Brown Spot, and Leaf Smut**.

The project explores image preprocessing, data augmentation, CNN architectures, model comparison, hyperparameter tuning, and fine-tuning a pretrained MobileNetV2 model.

## Objectives

* Analyze and preprocess rice leaf images.
* Apply data augmentation to increase training-image variety.
* Train and compare multiple deep learning models.
* Fine-tune MobileNetV2 and evaluate its classification performance.
* Identify a promising model for further validation and potential deployment.

## Dataset

The dataset contains **119 images** across three classes:

| Disease Class         | Number of Images |
| --------------------- | ---------------: |
| Bacterial Leaf Blight |               40 |
| Brown Spot            |               40 |
| Leaf Smut             |               39 |
| **Total**             |          **119** |

All images were resized to 224 × 224 pixels and pixel values were normalized to the range 0–1.

## Methodology

1. Image loading and exploratory data analysis
2. Image resizing and normalization
3. Train, validation, and test splitting
4. Data augmentation using rotation, shifting, zooming, and horizontal flipping
5. CNN model training
6. Transfer learning with MobileNetV2, ResNet50, and EfficientNetB0
7. Hyperparameter tuning and MobileNetV2 fine-tuning
8. Evaluation using accuracy, precision, recall, F1-score, and a confusion matrix

## Model Comparison

| Model                  | Test Accuracy |
| ---------------------- | ------------: |
| CNN                    |        55.56% |
| MobileNetV2            |        83.33% |
| ResNet50               |        33.33% |
| EfficientNetB0         |        33.33% |
| Fine-tuned MobileNetV2 |       100.00% |

The fine-tuned MobileNetV2 achieved the highest observed accuracy among the evaluated models on the 18-image test set.

## Best Model

The fine-tuned MobileNetV2 model used an ImageNet-pretrained base. The final tuning stage unfroze the last 20 layers and used a learning rate of 0.00001.

The model correctly classified all 18 test images in this experiment.

## Important Limitations

The dataset is small, and the test set contains only 18 images. The observed 100% test accuracy does not guarantee equivalent performance on new images or in real-world conditions. Additional validation on a larger, independent, and more diverse dataset is necessary before production deployment.

The test set was also evaluated during earlier tuning experiments, so the final result should be treated as preliminary rather than an unbiased estimate of generalization.

## Future Improvements

* Collect a larger and more diverse rice leaf dataset.
* Perform cross-validation and independent external testing.
* Evaluate images under varied lighting, backgrounds, cameras, and disease severity.
* Explore further model optimization and web or mobile deployment.

## Technologies Used

* Python
* Jupyter Notebook
* TensorFlow / Keras
* NumPy and Pandas
* OpenCV
* Matplotlib and Seaborn
* Scikit-learn

## Project File

Open the Jupyter Notebook in this repository to review the complete workflow, code, experiments, and evaluation results.

---

*This project was developed for learning and experimentation. Predictions should not be used as the sole basis for agricultural treatment decisions.*
