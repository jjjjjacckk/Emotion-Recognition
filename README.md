# Emotion Recognition
Emotion Recognition Model using the fer2013 dataset, built with Keras and OpenCV, with a 70% accuracy
* Data processing files borrowed from [here](https://github.com/oarriaga/face_classification)
* MTCNN package borrowed from [here](https://github.com/ipazc/mtcnn/tree/master/mtcnn)

## Usage
- To run the program, open command line and type:
    ```bash
    $ python3 emotion_color_demo.py
    ```
- To run the program with the MTCNN face detection neural network instead of OpenCV's Haar Feature Classifer, run: 
    ```bash
    $ python3 mtcnn_demo.py
    ```
- To train your own model, download the fer2013 package from [here](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data)
Create a "datasets" folder and unzip the file under it:
    ```bash
    $ tar -xzf fer2013.tar
    ```
- Run the training program:
    ```bash
    $ python3 train_emotion_classifer.py
    ```
    
## Troubleshooting
1. Model address error: 
    - python can't find your model: `fer2013_my_smallerCNN_new_trained.hdf5`
    - Error Message:
        ```bash
        OSError: SavedModel file does not exist at: saved_model_dir/{saved_model.pbtxt|saved_model.pb}
        ```
    - Solution: Change path to abosolute path
        > (e.g.) I put these files in 'Desktop'
        ```python3=
        # change '../' to your computer path
        detection_model_path = '../Emotion-Recognition/trained_models/detection_models/haarcascade_frontalface_default.xml'
        emotion_model_path = '../Emotion-Recognition/trained_models/emotion_models/fer2013_my_smallerCNN_new_trained.hdf5'

        # solution: 
        detection_model_path = '/Users/<YOU_CONPUTER_NAME>/Desktop/Emotion-Recognition/trained_models/detection_models/haarcascade_frontalface_default.xml'
        emotion_model_path = '/Users/<YOU_CONPUTER_NAME>/Desktop/Emotion-Recognition/trained_models/emotion_models/fer2013_my_smallerCNN_new_trained.hdf5'
        ```
