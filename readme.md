
FINGERPRINT-BASED VOTING SYSTEM
===============================

This project implements a Fingerprint-Based Voting System using Convolutional Neural Networks (CNN) for pattern recognition and enforces a One-Person-One-Vote logic. Developed in Google Colab, it uses grayscale fingerprint images from multiple users to train a classifier and identify users during the voting process.

-------------------------------
DATASET STRUCTURE
-------------------------------
DATASET used : SOCOFing Dataset 
Dataset Link : [text](https://drive.google.com/drive/folders/17hi9Hs_3MHAbVaWfZ4AMIGLOkWzZBghe?usp=drive_link)
The dataset is stored in Google Drive in the following structure:

data/
├── user1/
│   ├── finger1.png
│   ├── ...
├── user2/
│   ├── finger1.png
│   ├── ...
├── user3/
│   ├── finger1.png
│   ├── ...

Each folder contains 8 grayscale fingerprint samples per user.

-------------------------------
FEATURES
-------------------------------

- Fingerprint recognition using CNN
- Automatic data loading and preprocessing
- Accurate classification and evaluation
- Confusion matrix visualization
- One-Person-One-Vote enforcement

-------------------------------
LIBRARIES USED
-------------------------------

- TensorFlow & Keras
- OpenCV
- NumPy
- Scikit-learn
- Seaborn & Matplotlib

-------------------------------
PROJECT SETUP
-------------------------------

1. Mount Google Drive:

    from google.colab import drive
    drive.mount('/content/drive')

2. Set Dataset Path:

    data_path = "/content/drive/MyDrive/data/"

-------------------------------
MODEL ARCHITECTURE
-------------------------------

- Input: 128x128 grayscale fingerprint images
- Conv2D (32 filters) + MaxPooling
- Conv2D (64 filters) + MaxPooling
- Flatten
- Dense (128) + Dropout (0.5)
- Output Layer (Softmax per user)

-------------------------------
MODEL EVALUATION
-------------------------------

- Accuracy: Prints the test set accuracy
- Confusion Matrix: Visualizes predictions vs. actual labels

    plt.figure(figsize=(8, 6))
    sns.heatmap(conf_matrix, annot=True, cmap='Blues')

-------------------------------
ONE-PERSON-ONE-VOTE LOGIC
-------------------------------

    def vote_with_cnn(image_path):
        # Reads fingerprint image and predicts the user
        # Records vote only if the user has not already voted

Example Usage:

    vote_with_cnn('/content/drive/MyDrive/data/user2/finger1.png')

-------------------------------
VOTING OUTPUT EXAMPLES
-------------------------------

    ✅ Vote recorded for user2
    ❌ user2 has already voted!
    ✅ Vote recorded for user1
    ✅ Vote recorded for user3

-------------------------------
FINAL NOTE
-------------------------------

This project showcases how biometric authentication and pattern recognition can be applied to secure voting systems. Designed for academic purposes and demonstration, not for real-world deployment without additional security measures.

-------------------------------
Team Members
-------------------------------
KAVANA R
AMOOLYA P N
SOUJANYA ORALAGI