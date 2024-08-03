# CarDamage_Detection

The objective is to develop and implement a deep learning model that classifies car images to determine whether a car is damaged or not.  By leveraging a labeled dataset of car images, the model is trained to distinguish between damaged and undamaged cars and categorize them as either damaged(0) or whole(1).

This automated classification system is designed to enhance efficiency and accuracy in applications such as insurance claims processing, vehicle inspections, and automated damage assessment, ultimately providing a reliable tool for detecting car damage.

## Dataset
* The images in the dataset are collected from various sources, including insurance company databases, vehicle inspection reports, and publicly available car images.
* The dataset includes a diverse range of car models, colors, and types, ensuring robustness and generalizability of the model.
* Each image in the dataset is manually labeled by experts to ensure accuracy. The labels indicate whether a car is damaged (0) or whole (1).
* Damage categories include minor dents, scratches, broken parts, and severe damage. For simplicity, the labels are binary (0 for damaged, 1 for whole).
* The dataset is organized into two main directories: validation and Training. Each directory is divided into two sub categories: Damaged and Whole. Each contains a large number of images corresponding to the respective category.

## Data Preprocessing

* Resizing: The images are resized to a consistent size suitable for input to the deep learning model. This ensures uniformity and helps the model learn features effectively.
* Normalization: The pixel values of the images are normalized to a range of 0 to 1. This helps in faster convergence during training.
* Data Augmentation: Various augmentation techniques are applied to increase the diversity of the training data and improve the model's robustness:
  - Rotation Range: Randomly rotates images within a range of 40 degrees.
  - Width Shift Range: Randomly shifts images horizontally by 20% of the total width.
  - Height Shift Range: Randomly shifts images vertically by 20% of the total height.
  - Shear Range: Applies random shear transformations within a range of 20 degrees.
  - Horizontal Flip: Randomly flips images horizontally.
  - Fill Mode: Fills in new pixels created during transformations, using the nearest pixel value.

## Model Architecture

The model employs the VGG16 convolutional neural network (CNN) architecture to analyze and classify the car images. VGG16 is a well-known deep learning model for image classification tasks. Key layers include convolutional layers, pooling layers, and fully connected layers.

1. Convolutional Layers:
   * VGG16 consists of 13 convolutional layers with small receptive fields (3x3).
   * These layers extract features from the input images by applying convolution operations.
2. Pooling Layers:
   * The model includes 5 max-pooling layers, each following a set of convolutional layers.
   * Max-pooling reduces the spatial dimensions of the feature maps while retaining important features.
3. Fully Connected Layers:
   * The top of the network consists of 3 fully connected layers.
   * The first two layers have 512 neurons each, followed by the output layer with a sigmoid activation function for binary classification.
4. Transfer Learning:
   The pre-trained VGG16 model (trained on the ImageNet dataset) is used, and the top layers are fine-tuned to adapt to the car damage detection task.This approach leverages the rich feature representations learned by VGG16 on a large-scale dataset.

# Results

The trained model demonstrates an accuracy of 77.9% in classifying car images as damaged or whole. This means that the model correctly identifies whether a car is damaged or intact in approximately 77.9% of the cases. A confusion matrix is printed to visualize the performance of the classification model. It shows the number of true positives, true negatives, false positives, and false negatives.

A subset of images is selected to visualize the model’s predictions. Sample predictions are plotted along with the labels of true and predicted values. These plots help in visually assessing the model's performance and identifying any potential patterns or errors in the predictions.


