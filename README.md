# Fashion-MNIST Clothing Classifier

A deep-learning image-classification project that compares a baseline fully connected neural network, a custom Convolutional Neural Network (CNN), and MobileNetV2 transfer learning on the Fashion-MNIST dataset.

## Project Objective

The objective is to classify grayscale clothing images into one of ten categories and investigate how model architecture affects classification performance.

The project compares:

- Baseline fully connected neural network
- Custom Convolutional Neural Network (CNN)
- Frozen MobileNetV2 feature extractor
- Fine-tuned MobileNetV2

## Dataset

Fashion-MNIST contains 70,000 grayscale images:

- 60,000 training images
- 10,000 testing images
- Image dimensions: 28 × 28 pixels
- Number of classes: 10

### Clothing Categories

| Label | Category |
|---|---|
| 0 | T-shirt/top |
| 1 | Trouser |
| 2 | Pullover |
| 3 | Dress |
| 4 | Coat |
| 5 | Sandal |
| 6 | Shirt |
| 7 | Sneaker |
| 8 | Bag |
| 9 | Ankle boot |

## Project Workflow

1. Load and explore Fashion-MNIST.
2. Inspect class and pixel distributions.
3. Normalize the images.
4. Create training, validation, and testing sets.
5. Train a baseline neural network.
6. Build and train a custom CNN.
7. Apply MobileNetV2 transfer learning.
8. Fine-tune the final MobileNetV2 layers.
9. Evaluate all models.
10. Save the best-performing model.

## Model Architectures

### 1. Baseline Neural Network

The baseline model flattens each 28 × 28 image into 784 pixel values and processes them using fully connected layers.

### 2. Custom CNN

The CNN uses convolution, batch normalization, max pooling, and dropout to learn spatial features such as edges, shapes, and clothing patterns.

### 3. MobileNetV2

MobileNetV2 was loaded with ImageNet weights. Fashion-MNIST images were resized to 96 × 96 and converted from one grayscale channel to three channels.

Two transfer-learning phases were tested:

- Frozen feature extraction
- Partial fine-tuning using a small learning rate

## Results

| Model | Test Accuracy |
|---|---:|
| Baseline Neural Network | 87.66% |
| Custom CNN | 93.14% |
| Frozen MobileNetV2 | 89.23% |
| Fine-tuned MobileNetV2 | See notebook |

The custom CNN achieved the highest test accuracy among the models with reported results.

It improved accuracy by 5.48 percentage points compared with the baseline model and reduced the classification error by approximately 44.4%.

## Key Findings

- CNNs perform better than fully connected networks for image data because they preserve spatial relationships.
- The custom CNN achieved the best performance among the models with reported results.
- Transfer learning did not automatically outperform the custom model.
- ImageNet and Fashion-MNIST have significantly different visual characteristics.
- Smaller task-specific models may be more effective and efficient for simple grayscale datasets.
- Visually similar categories such as shirts, T-shirts, coats, and pullovers were the most difficult to distinguish.

## Research Extension

This project may be extended into a comparative research study of deep-learning architectures for fashion image classification.

Planned research objectives:

- Compare accuracy and loss across all evaluated architectures.
- Analyze confusion matrices and misclassification patterns.
- Evaluate model size, training time, and inference performance.
- Investigate why a task-specific CNN may outperform ImageNet-based transfer learning on Fashion-MNIST.

Research findings and conclusions will be updated after completing the experiments and analysis.

## Technologies

- Python
- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

## Repository Structure

```text
Fashion-MNIST-Clothing-Classifier/
├── Fashion_MNIST_Clothing_Classifier.ipynb
├── fashion_mnist_cnn_best.keras
├── requirements.txt
├── README.md
├── LICENSE
└── outputs/
```

## Future Improvements

- Complete the fine-tuned MobileNetV2 evaluation.
- Add confusion matrices and classification reports.
- Compare training time, inference speed, and model size.
- Develop a simple web application for uploading clothing images and predicting their categories.
- Complete the comparative research paper based on experimental results.

## Conclusion

This project demonstrates the application of deep learning to clothing image classification using Fashion-MNIST. The custom CNN achieved 93.14% test accuracy, demonstrating the effectiveness of task-specific convolutional architectures for this dataset.

The project also explores transfer learning with MobileNetV2 and highlights the importance of evaluating different architectures rather than assuming that a more complex model will always perform better.


## Research Status

Research paper based on this project: **In Progress**
