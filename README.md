# MNIST Digit Recognition

A deep learning project that recognizes handwritten digits (0 to 9) using a Convolutional Neural Network (CNN) built with TensorFlow/Keras. The model reaches **99.04% accuracy** on the MNIST test set.

## Dataset

MNIST in CSV format from Kaggle ("MNIST in CSV" dataset by Dariel Dato-on).

- 60,000 training images and 10,000 test images
- Each image is 28 x 28 pixels, grayscale
- Each row has a `label` (the digit) followed by 784 pixel values (0 to 255)

## Approach

1. **Load and explore** the data (shape, missing values, digit counts, sample images)
2. **Preprocess** the images:
   - scale pixel values from 0-255 to 0-1
   - reshape each row into a 28 x 28 x 1 image
   - split the training data into 54,000 training and 6,000 validation images
3. **Build a CNN:**
   - Conv2D (32 filters) and MaxPooling
   - Conv2D (64 filters) and MaxPooling
   - Flatten, Dropout (0.3), Dense (128), Dense (10, softmax)
   - 225,034 parameters in total
4. **Train** for 8 epochs with the Adam optimizer (batch size 128)
5. **Evaluate** on the 10,000 test images with accuracy, a classification report and a confusion matrix, and inspect the wrong predictions

## Results

| Metric | Value |
|---|---|
| Training accuracy (epoch 8) | 0.9931 |
| Validation accuracy (epoch 8) | 0.9885 |
| **Test accuracy** | **0.9904** |
| Test loss | 0.0264 |

- 96 of the 10,000 test images were misclassified.
- Every digit has an F1-score between 0.984 and 0.996.
- The digits 5, 6 and 9 were the hardest for the model, because they can look similar to other digits such as 3 and 4.

## Tech Stack

- Python
- TensorFlow / Keras
- scikit-learn
- pandas and NumPy
- matplotlib
- Google Colab

## How to Run

1. Clone this repository:

```
git clone https://github.com/zainabbatool-bit/mnist-digit-recognition.git
cd mnist-digit-recognition
```

2. Install the requirements:

```
pip install -r requirements.txt
```

3. Download the "MNIST in CSV" dataset from Kaggle and place `mnist_train.csv` and `mnist_test.csv` in the project folder.

4. Open `MNIST_Digit_Recognition.ipynb` in Jupyter Notebook, VS Code or Google Colab and run all cells. In Colab, upload the two CSV files first.

## Project Structure

```
mnist-digit-recognition/
├── MNIST_Digit_Recognition.ipynb   # Full project notebook
├── requirements.txt                # Libraries needed
└── README.md
```

## Author

**Zainab Batool**

- GitHub: [zainabbatool-bit](https://github.com/zainabbatool-bit)
- LinkedIn: [Zainab Batool](https://www.linkedin.com/in/zainab-batool-b4661734a)