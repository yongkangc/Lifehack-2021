# Distraction Detector

### Video Demo
[![Everything Is AWESOME](additional/demo.png)](https://youtu.be/SJ1-PvWhSbc "Everything Is AWESOME")


The Distraction Detector works as follows:

1. Uses the default OpenCV [Haar Cascade Face Detector](https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_frontalface_default.xml) to detect a person's face.

2. Within a detected face, the person's eyes are located using the OpenCV [Haar Cascade Eye Detector](https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_eye.xml).

3. For each detected eye, a pretrained Convolutional Neural Network(CNN) is used to predict whether a person is distracted or not(binary classifier). The [default CNN](https://github.com/ExtremelySunnyYK/Lifehack-2021/blob/main/src/cnn/distraction_model.hdf5) was trained on eye images created by the `get_data.py` script (which essentially saves detected eyes as individual images).

Below table contains all the important scripts in this repo.

| File  | Description  |
|---|---|
| [`get_data.py`](https://github.com/ExtremelySunnyYK/Lifehack-2021/blob/master/src/get_data.py)  | Creates training data for Distraction Classifier  |
| [`train.py`](https://github.com/johannesharmse/ExtremelySunnyYK/Lifehack-2021/master/src/cnn/train.py)  | Creates and trains Distraction Classifier using Keras  |
| [`distraction_detector.py`](https://github.com/ExtremelySunnyYK/Lifehack-2021/blob/master/src/distraction_detector.py)  | Detects distraction using OpenCV and Keras |