# Start recognizing face

Define a new function called face_detector for real-time face detection and recognition using the trained model. This function detects faces in video frames, draws rectangles around detected faces, and returns the detected face region.

This line converts the input image img from its original color (BGR - Blue, Green, Red) format to grayscale. Grayscale images have only one channel representing pixel intensities, making them suitable for face detection and other image processing tasks.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/b37b86b2-0463-4e57-895b-33fec02d88d8)


This line uses the detectMultiScale method of the face_classifier object (which is presumably a pre-trained face detection classifier provided by OpenCV or another library).
It detects faces in the grayscale image (gray) using a scale factor of 1.3 and a minimum number of neighboring rectangles to consider a region as a face (5). The detectMultiScale function returns a list of rectangles, where each rectangle corresponds to the bounding box of a detected face.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/ca34acb6-cfca-4b03-8a71-59822a2f23f4)

This condition checks if the faces variable is an empty tuple, which would mean that no faces were detected in the image.
If no faces are detected (faces is an empty tuple), the function returns the original image img along with an empty list [] as there are no regions of interest (ROI) or faces to return.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/e98d380d-66cd-4acd-b1e8-5e5ff5de275a)

The code enters this block when faces are detected in the image.
If faces are detected:
-- It iterates through the list of detected faces using a for loop.
For each detected face, it does the following:
-- Draws a rectangle around the detected face on the original image using cv2.rectangle. This helps visualize where the faces are in the image.
-- Defines a region of interest (ROI) by cropping the original image to the bounding box of the detected face using slicing (img[y:y+h, x:x+w]).
-- Resizes the ROI to a fixed size of 200x200 pixels using cv2.resize. This step is often necessary when preparing images for further processing, such as feeding them into a machine learning model for face recognition.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/951a4adf-d8c0-47e2-9821-7de177065f9e)

Real-Time Face Recognition Loop: In a continuous loop, capture video frames from the webcam and perform real-time face recognition using the face_detector function:
-- Read a frame from the webcam.
-- Call face_detector to detect and recognize faces in the frame.
-- If a recognized face is detected:
-- Convert the recognized face to grayscale.
-- Pass the grayscale face to the trained model for prediction.
-- Calculate the confidence level of the prediction.
-- Display appropriate text based on the confidence level.
-- If no recognized face is detected, display a "No face found" message.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/a5e4b7d6-36f1-40e7-9216-18fc5f3725b6)

"ret, frame = cap.read()":
-- cap is likely a video capture object, typically created using OpenCV's VideoCapture class, which is used to read frames from a video source 
-- ret: A Boolean value indicating whether the frame was successfully captured. If the frame capture is successful, ret is set to True; otherwise, it's set to False.
-- frame: The captured frame, which is an image represented as a NumPy array.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/a223b2b9-1458-4958-a165-d1a49f841467)


if not ret:
This line checks whether ret is False, which would indicate that the frame capture failed or that there are no more frames to capture. In such cases, it's typically used to handle the end of the video stream or any errors that might occur during frame capture.
continue:
If ret is False, this continue statement is executed. It essentially skips the rest of the loop iteration and proceeds to the next frame capture, effectively ignoring any processing for this frame.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/bd728b9b-c1a9-4095-b7de-200874dd7bd0)

This line calls the face_detector function and passes the current frame (frame) as an argument.
The face_detector function performs face detection on the frame and returns two values:
image: The modified image with rectangles drawn around detected faces (as explained in the previous response).
face: The last processed face region (ROI) from the frame. This is the region corresponding to the last detected face in the frame.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/062348d8-7c50-4c14-b9b0-41d84c0118c4)

Next, I have enclosed this code in a try-except block, which is used to handle exceptions. It's a way to gracefully handle potential errors or exceptions that might occur during execution.
If an exception occurs within the try block, the code inside the except block is executed.

This line passes the grayscale face region to a prediction model (vimal_model) for recognition or classification.
"results" contains the outcome of the prediction, possibly including the recognized label or class, and some measure of confidence or similarity.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/f794ba0b-99f5-4549-a18d-bd0c6ab7abec)

This conditional statement checks if the second element of the results tuple is less than 500. 

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/fcc55e97-85b3-49e8-b265-25790adafb9b)

This line calculates the confidence percentage based on the second element of the results tuple. It scales the value to a 0-100 range (by dividing by 400) and converts it to an integer.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/6153f7b3-53da-4405-a5a4-71380ce910ef)

This line creates a string display_string that includes the calculated confidence percentage and a message indicating that the system is confident that the recognized face belongs to a user.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/91349673-5246-4099-9206-cdac8e300042)
