
# Pneumonia Detection Using CNN

## Problem Statement

The objective of this project is to develop a Convolutional Neural Network (CNN)
to classify pediatric chest X-ray images into two classes:

- NORMAL
- PNEUMONIA

## Dataset

The dataset contains pediatric chest X-ray images divided into training,
validation, and testing sets.

The extracted dataset contained:

- Training images: 5,216
- Validation images: 16
- Testing images: 624
- Total valid images: 5,856

The dataset is divided into two classes:

- NORMAL
- PNEUMONIA

The dataset is imbalanced, with more Pneumonia images than Normal images.

## Methodology

The following steps were performed:

1. Loaded the chest X-ray dataset.
2. Resized all images to 224 × 224 pixels.
3. Normalized pixel values to the range [0, 1].
4. Applied data augmentation to the training images.
5. Built a CNN model using convolutional and max-pooling layers.
6. Added fully connected layers for classification.
7. Used Dropout to reduce overfitting.
8. Used Adam optimizer and Binary Crossentropy loss.
9. Trained the model for 15 epochs.
10. Evaluated the model using the test dataset.
11. Generated a classification report and confusion matrix.

## CNN Architecture

The CNN consists of:

- Input layer: 224 × 224 × 3
- Conv2D: 32 filters
- MaxPooling2D
- Conv2D: 64 filters
- MaxPooling2D
- Conv2D: 128 filters
- MaxPooling2D
- Flatten
- Dense: 128 neurons
- Dropout: 0.5
- Output layer: 1 neuron with sigmoid activation

Total trainable parameters: 11,169,089

## Data Augmentation

The following augmentation techniques were applied to training images:

- Rotation
- Width shifting
- Height shifting
- Zoom
- Horizontal flipping

Validation and test images were only normalized and were not augmented.

## Evaluation Metrics

The model was evaluated using:

- Accuracy
- Precision
- Recall
- F1-Score
- Confusion Matrix

## Results

The final evaluation results on the test dataset are:

| Metric | Score |
|---|---:|
| Accuracy | 81.89% |
| Precision | 78.79% |
| Recall | 97.18% |
| F1-Score | 87.03% |

### Confusion Matrix

| Actual / Predicted | NORMAL | PNEUMONIA |
|---|---:|---:|
| NORMAL | 132 | 102 |
| PNEUMONIA | 11 | 379 |

## Findings

The CNN achieved an overall test accuracy of 81.89%.

The model achieved a high recall of 97.18% for the Pneumonia class,
indicating that it correctly identified most Pneumonia images in the test set.

However, the recall for the Normal class was lower than that of the
Pneumonia class. This is likely influenced by the class imbalance in the
dataset.

Another limitation is that the extracted validation set contained only
16 images, which is very small. Therefore, validation performance may be
unstable and should be interpreted cautiously.

## Model Saving

The trained model was saved in Keras format:

`pneumonia_cnn_final.keras`

## Technologies Used

- Python
- TensorFlow / Keras
- NumPy
- Pandas
- Scikit-learn
- Matplotlib
- Seaborn
- Google Colab

## Conclusion

A CNN-based image classification model was successfully developed for
classifying pediatric chest X-ray images into Normal and Pneumonia classes.
The model achieved an accuracy of 81.89% and an F1-score of 87.03% on the
test dataset.

The results demonstrate that the CNN was able to learn useful visual
patterns from the chest X-ray images. However, the small validation set and
class imbalance are important limitations of this experiment.
