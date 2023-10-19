Face Detection using OpenCV
==========================

This script demonstrates how to detect faces in real-time using OpenCV's Haar cascade classifier. It uses the default Haar cascade model for frontal face detection, which is stored in the file `haarcascade_frontalface_default.xml`.

### Usage

1. Install the required packages by running the following command:
```
pip install opencv-python
```
2. Run the script using the following command:
```
python Cv2-FaceDetect.py
```
3. The script will start capturing video from the default camera (camera index 0) and detect faces in real-time.
4. Press the 'ESC' key (key code 27) to exit the script.

### Code Explanation

The script imports the `cv2` module from the OpenCV library. It then loads the Haar cascade model for frontal face detection using the `cv2.CascadeClassifier` class.

The `detect()` function is defined to perform the face detection. It captures video from the default camera using the `cv2.VideoCapture` class and enters a loop to process each frame.

Within the loop, the function does the following:

1. Reads a frame from the camera using the `cv2.VideoCapture.read()` method.
2. Converts the frame to grayscale using the `cv2.cvtColor()` function.
3. Detects faces in the grayscale image using the `cv2.CascadeClassifier.detectMultiScale()` method. The faces are detected at multiple scales (1.1, 4) to capture faces of different sizes.
4. Draws rectangles around the detected faces using the `cv2.rectangle()` function. The rectangles are drawn on the original color image (`img`).
5. Displays the image with the detected faces using the `cv2.imshow()` function.
6. Waits for 30 milliseconds for a key press using the `cv2.waitKey()` function. If the 'ESC' key is pressed (key code 27), the loop is exited.

The script then releases the camera resource using the `cv2.VideoCapture.release()` method and exits.

### Notes

* The script assumes that the camera is connected and functioning properly.
* The script uses the default Haar cascade model for frontal face detection. If you want to use a different model, you can load it using the `cv2.CascadeClassifier` class and pass the model file path as an argument.
* The script detects faces in real-time, but the detection accuracy may vary depending on the lighting conditions, face orientation, and other factors.
* You can modify the script to detect faces in a different resolution or frame rate by adjusting the `cv2.VideoCapture` parameters.
