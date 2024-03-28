# Face-and-Hand-Landmarks-Detection-using-Python-Mediapipe-OpenCV
In this project, I use mediapipe python library to detect face and hand landmarks. I use a Holistic model from mediapipe solutions to detect all the face and hand landmarks. We will be also seeing how we can access different landmarks of the face and hands which can be used for different computer vision applications such as sign language detection, drowsiness detection, etc.

Mediapipe- is a cross-platform library developed by Google that provides amazing ready-to-use ML solutions for computer vision tasks.

OpenCV library in python is a computer vision library that is widely used for image analysis, image processing, detection, recognition, etc.

STEP-1: Import all the necessary libraries, In our case only two libraries are required.

STEP-2: Initializing Holistic model and Drawing utils for detecting and drawing landmarks on the image.
Let us look into the parameters for the Holistic Model:

Holistic(
  static_image_mode=False, 
  model_complexity=1, 
  smooth_landmarks=True, 
  min_detection_confidence=0.5, 
  min_tracking_confidence=0.5
)
static_image_mode: It is used to specify whether the input images must be treated as static images or as a video stream. The default value is False.
model_complexity: It is used to specify the complexity of the pose landmark model: 0, 1, or 2. As the model complexity of the model increases the landmark accuracy and latency increase. The default value is 1.
smooth_landmarks: This parameter is used to reduce the jitter in the prediction by filtering pose landmarks across different input images. The default value is True.
min_detection_confidence: It is used to specify the minimum confidence value with which the detection from the person-detection model needs to be considered as successful. Can specify a value in [0.0,1.0]. The default value is 0.5.
min_tracking_confidence: It is used to specify the minimum confidence value with which the detection from the landmark-tracking model must be considered as successful. Can specify a value in [0.0,1.0]. The default value is 0.5.

STEP-3: Detecting Face and Hand landmarks from the image. Holistic model processes the image and produces landmarks for Face, Left Hand, Right Hand and also detects the Pose of the 
Capture the frames continuously from the camera using OpenCV.
Convert the BGR image to an RGB image and make predictions using initialized holistic model.
The predictions made by the holistic model are saved in the results variable from which we can access the landmarks using results.face_landmarks, results.right_hand_landmarks, results.left_hand_landmarks respectively.
Draw the detected landmarks on the image using the draw_landmarks function from drawing utils.
Display the resulting Image.

The holistic model produces 468 Face landmarks, 21 Left-Hand landmarks, and 21 Right-Hand landmarks. The individual landmarks can be accessed by specifying the index of the required landmark. Example: results.left_hand_landmarks.landmark[0]. You can get the index of all the individual landmarks using the below code:
