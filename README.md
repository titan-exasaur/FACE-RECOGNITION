
# Face Recognition System
This repository contains a complete face recognition system using OpenCV and deep learning. The system captures face images, extracts face embeddings, trains a face recognition model, and performs real-time face recognition.

# Table of Contents
- [Installation](#installation)
- [Usage](#usage)
  1. [Face Dataset Creation](#1-face-dataset-creation)
  2. [Extract Face Embeddings](#2-extract-face-embeddings)
  3. [Train Face Recognition Model](#3-train-face-recognition-model)
  4. [Real-time Face Recognition](#4-real-time-face-recognition)
- [Environment Setup](#environment-setup)
- [Explanation of Files](#explanation-of-files)

## Installation
1. Clone the repository:

```

git clone https://github.com/titan-exasaur/FACE-RECOGNITION.git
cd face_recognition_system

```

2. Install the required packages using environment.yaml:

```

conda env create -f environment.yaml
conda activate face_recognition

```


## Usage
#### 1. Face Dataset Creation 
Run the following script and follow the prompts to capture face images:

```
python 1_face_dataset.py
```

This script will:
* Create a directory face_dataset/.
* Capture 50 images of the user’s face from the webcam and store them in a subdirectory named after the user.
  
#### 2. Extract Face Embeddings 

Run the following script to extract face embeddings:

```
python 2_extract_face.py
```
This script will:
* Load a pre-trained face detector model.
* Process each image in the face_dataset/ directory.
* Extract the face embeddings and save them in output/embeddings.pickle.

#### 3. Train Face Recognition Model 

Run the following script to train the model:

```
python 3_train_face_model.py
```

This script will:
* Load the face embeddings from output/embeddings.pickle.
* Encode the labels.
* Train a Support Vector Machine (SVM) model for face recognition.
* Save the trained model and label encoder in output/recognizer.pickle and output/le.pickle respectively.
  
#### 4. Real-time Face Recognition 

Run the following script to start real-time face recognition:

```
python 4_inference.py
```

This script will:
* Load the pre-trained face detector, face embedding model, face recognition model, and label encoder.
* Start the webcam and process each frame to detect and recognize faces in real-time.
* Display the recognized faces along with their confidence scores.

# Environment Setup
The environment.yaml file contains the necessary dependencies to run the scripts. Create the environment using:

```
conda env create -f environment.yaml
conda activate face_recognition
```

# Explanation of Files
[1_face_dataset.py](https://github.com/titan-exasaur/FACE-RECOGNITION/blob/main/1_face_dataset.py) : Captures face images using the webcam and stores them in the face_dataset/ directory.

2_extract_face.py : Extracts face embeddings from the captured images using a pre-trained face detector and face embedding model. Saves the embeddings and labels in output/embeddings.pickle.

3_train_face_model.py : Trains a face recognition model using the extracted face embeddings. Saves the trained model and label encoder in output/recognizer.pickle and output/le.pickle.

4_inference.py : Performs real-time face recognition using the webcam. Loads the trained face recognition model and label encoder to recognize faces in the video stream.

environment.yaml : Contains the dependencies required to run the scripts. Use this file to set up the conda environment.


By following the above steps, you will have a fully functional face recognition system capable of capturing, training, and recognizing faces in real-time.
