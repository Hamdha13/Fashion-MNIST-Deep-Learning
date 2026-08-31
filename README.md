# Fashion MNIST Deep Learning Classification

A deep learning project for classifying Fashion MNIST images into 10 different clothing categories using **Convolutional Neural Networks (CNNs)**, **data augmentation**, **hyperparameter experimentation**, and **MobileNetV2 transfer learning and fine-tuning**.

---

## 📌 Project Overview

The objective of this project is to build and evaluate deep learning models for image classification using the Fashion MNIST dataset.

The project starts with a custom CNN and progressively improves the model through:

* Weight initialization experiments
* Activation function comparison
* Batch Normalization
* Dropout
* Learning-rate experimentation
* Model capacity comparison
* Data augmentation
* Transfer learning using MobileNetV2
* Fine-tuning of pretrained layers
* Confusion matrix analysis
* Classification reports
* ROC curve analysis

This provides a practical comparison between a CNN trained from scratch and a pretrained ImageNet model adapted to Fashion MNIST.

---

## 📊 Dataset

The project uses the **Fashion MNIST** dataset provided by TensorFlow/Keras.

Fashion MNIST contains:

* **70,000** grayscale images
* Image size: **28 × 28 pixels**
* **10** clothing categories
* Training set: **60,000 images**
* Test set: **10,000 images**

### Classes

| Label | Class       |
| ----: | ----------- |
|     0 | T-shirt/top |
|     1 | Trouser     |
|     2 | Pullover    |
|     3 | Dress       |
|     4 | Coat        |
|     5 | Sandal      |
|     6 | Shirt       |
|     7 | Sneaker     |
|     8 | Bag         |
|     9 | Ankle boot  |

---

## 🧠 Models and Experiments

### 1. Custom CNN

A CNN was built from scratch using:

* Convolutional layers
* ReLU activation
* Max Pooling
* Fully Connected (Dense) layers
* Softmax output layer

The baseline architecture was used as the starting point for subsequent experiments.

---

### 2. Hyperparameter Experiments

Several experiments were conducted to understand how different architectural and training choices affect model performance.

#### Weight Initialization

Different kernel initialization strategies were evaluated to determine their effect on convergence and validation performance.

#### Activation Functions

Different activation functions were compared, with **ReLU** providing strong performance for the CNN architecture.

#### Batch Normalization

Batch Normalization was introduced to improve training stability and help the network converge more effectively.

#### Dropout

Dropout was used as a regularization technique to reduce overfitting.

#### Learning Rate

Different learning rates were tested to identify a suitable optimization setting.

#### Model Capacity

CNN architectures with different numbers of filters were compared:

* Small: `(8, 16)`
* Baseline: `(32, 64)`
* Large: `(128, 256)`

The experiments demonstrated the relationship between model capacity, number of parameters, and validation performance.

---

## 🔄 Data Augmentation

Data augmentation was introduced to improve generalization.

The model uses:

* Random horizontal flipping
* Random rotation
* Random zoom

These transformations generate slightly modified training images, helping the model become less dependent on the exact appearance of the original training samples.

---

## 🚀 Transfer Learning with MobileNetV2

The project also investigates **transfer learning using MobileNetV2 pretrained on ImageNet**.

Since Fashion MNIST images are:

* Grayscale
* 28 × 28 pixels

while MobileNetV2 expects:

* RGB images
* Larger input dimensions

the images were adapted by:

1. Normalizing pixel values
2. Converting grayscale images to 3-channel RGB
3. Resizing images to the MobileNetV2 input size

The pretrained MobileNetV2 feature extractor was initially kept **frozen**, and a new classification head was trained for the Fashion MNIST classes.

---

## 🔧 Fine-Tuning

After evaluating the frozen-base transfer learning approach, fine-tuning was explored.

In fine-tuning, selected layers of the pretrained MobileNetV2 network are **unfrozen** and trained together with the classification head using a smaller learning rate.

This allows the pretrained feature representations to adapt more specifically to Fashion MNIST while retaining useful features learned from ImageNet.

---

## 📈 Model Evaluation

The models are evaluated using multiple metrics rather than accuracy alone.

### Evaluation Metrics

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix
* ROC Curve
* Training and validation loss
* Training and validation accuracy

The confusion matrix is used to identify which clothing categories are commonly confused with one another.

---

## 📁 Project Structure

```text
Fashion-MNIST-Deep-Learning/
│
├── README.md
├── requirements.txt
│── FASHION_MNIST_DL_DEMO_31_08.ipynb
│
├── results/
│   ├── confusion_matrix.png
│   ├── ROC_curve.png
│   ├── training_history.png
```

---

## 🛠️ Technologies Used

* **Python**
* **TensorFlow**
* **Keras**
* **NumPy**
* **Pandas**
* **Scikit-learn**
* **Matplotlib**
* **Seaborn**
* **Jupyter Notebook / Google Colab**

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/Hamdha13/Fashion-MNIST-Deep-Learning.git
```

Navigate into the project:

```bash
cd Fashion-MNIST-Deep-Learning
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

---

## ▶️ Running the Project

Open the notebook:

```text
notebooks/FASHION_MNIST_DL_DEMO_31_08_26.ipynb
```

The notebook can be run using:

* Jupyter Notebook
* JupyterLab
* Google Colab
* VS Code with the Jupyter extension

Run the cells sequentially to reproduce the preprocessing, training, experiments, visualizations, and evaluation results.

---

## 📌 Key Findings

The experiments demonstrate several important deep learning concepts:

* Increasing model capacity can improve performance, but adding parameters does not always guarantee better validation accuracy.
* Batch Normalization can improve training stability.
* Dropout helps reduce overfitting by regularizing the network.
* Data augmentation can improve generalization by exposing the model to variations of training images.
* Transfer learning allows pretrained feature representations to be reused for a new classification task.
* A frozen pretrained backbone and a fine-tuned backbone represent different levels of adaptation to the target dataset.
* Evaluation using precision, recall, F1-score, confusion matrices, and ROC curves provides a more complete understanding of model performance than accuracy alone.

---

## 📊 Results

The project compares the performance of the different approaches using validation and test-set metrics.

| Model         | Approach                            |                     Accuracy |
| ------------- | ----------------------------------- | ---------------------------: |
| Custom CNN    | Trained from scratch                |                         ~89% |
| Augmented CNN | CNN + Regularization + Augmentation |                        ~89%+ |
| MobileNetV2   | Frozen pretrained base              |                         ~92% |
| MobileNetV2   | Fine-tuning                         | *Add your final result here* |

> **Note:** Results may vary slightly depending on random initialization, training configuration, and hardware.

---

## 🔍 Feature Map Visualization

Intermediate CNN activations are visualized to understand what different convolutional layers learn.

Early layers generally respond to simple patterns such as:

* Edges
* Lines
* Corners
* Basic textures

Deeper layers combine these patterns to represent more complex structures associated with clothing shapes and regions.

---

## 🎯 Learning Objectives

Through this project, the following concepts were explored:

* Image preprocessing
* CNN architecture design
* Convolution and pooling
* Activation functions
* Weight initialization
* Batch Normalization
* Dropout
* Hyperparameter tuning
* Data augmentation
* Model regularization
* Transfer learning
* Fine-tuning
* Feature extraction
* Model evaluation
* Confusion matrix analysis
* ROC curve analysis
* Feature-map visualization

---

## 👩‍💻 Author

**Hamdha S**

B.Tech Artificial Intelligence and Data Science Student

---

## ⭐ Acknowledgements

* TensorFlow / Keras for the Fashion MNIST dataset and deep learning framework
* The Fashion MNIST dataset creators
* ImageNet pretrained models used through MobileNetV2
