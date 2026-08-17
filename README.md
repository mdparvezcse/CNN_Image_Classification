CNN Image Classification – Fashion-MNIST

This project implements a Convolutional Neural Network (CNN) using PyTorch to classify Fashion-MNIST images into 10 different clothing categories.

How the Model Works

The complete workflow is:

Input Image → Preprocessing → CNN Layers → Feature Extraction → Classification → Prediction**

1. Dataset

The model uses the **Fashion-MNIST** dataset containing 70,000 grayscale images.

Each image:

Size: 28 × 28 pixels
Channels: 1 (grayscale)
Classes: 10

Classes include T-shirt/top, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag, and Ankle boot.

2. Preprocessing

Before entering the CNN, images are:

1. Resized to 28 × 28
2. Converted into PyTorch tensors
3. Normalized using mean `0.5` and standard deviation `0.5`

For custom real-world images, they are first converted to grayscale.

### 3. CNN Architecture

text
Input: 1 × 28 × 28
        ↓
Conv2D: 1 → 32
        ↓
ReLU
        ↓
MaxPool 2×2
        ↓
Conv2D: 32 → 64
        ↓
ReLU
        ↓
MaxPool 2×2
        ↓
Flatten: 64 × 7 × 7 = 3136
        ↓
Fully Connected: 3136 → 128
        ↓
ReLU
        ↓
Output: 128 → 10


4. Feature Extraction

The first convolutional layer learns simple features such as **edges, textures, and shapes**.

The second convolutional layer learns more complex features from the features extracted by the first layer.

5. Pooling

The MaxPooling layers reduce the spatial size of the feature maps.

text
28 × 28 → 14 × 14 → 7 × 7


This reduces computation while keeping important features.

6. Classification

After feature extraction, the feature maps are flattened into 3,136 values.

The fully connected layers process these features and produce 10 output values, one for each Fashion-MNIST class.

The class with the highest output value becomes the final prediction.

7. Training

The model is trained using mini-batches of 64 images.

For each batch:

  text
Input Images
     ↓
Forward Propagation
     ↓
Prediction
     ↓
Calculate Cross-Entropy Loss
     ↓
Backpropagation
     ↓
Adam Optimizer
     ↓
Update Model Weights


This process is repeated for **10 epochs**.

 8. Model Evaluation

The model is evaluated using:

* Training Accuracy
* Validation Accuracy
* Test Accuracy
* Loss
* Confusion Matrix

Final performance:

| Metric              |     Result |
| ------------------- | ---------: |
| Training Accuracy   | **97.86%** |
| Validation Accuracy | **91.88%** |
| Test Accuracy       | **91.32%** |

 9. Real-World Testing

After training, the model is also tested with **10 custom clothing images**.

The images are converted to grayscale, resized to 28×28, normalized, and passed through the trained CNN.

The model returns:

* Predicted class
* Confidence score

Real-world images can be harder because their backgrounds, lighting, colors, and viewpoints are different from the original Fashion-MNIST images.



Main Output

The project produces:

* Training/validation loss graph
* Training/validation accuracy graph
* Confusion matrix
* Misclassified image examples
* Custom image predictions
* Trained  model


