# Face_Detection

# Collecting training data

Import Libraries: Import the necessary libraries for the project, including OpenCV (cv2) for computer vision tasks and NumPy (numpy) for numerical operations.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/a5c033e4-9929-4d13-959e-0c93bdc905bd)

Load Pre-trained Classifier: Load a pre-trained face detection classifier using the cv2.CascadeClassifier class. This classifier is used to detect faces in images.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/5ae81b56-d7ba-42c8-9f3f-9cbc06db8e1c)


Define face_extractor Function: Define a function called face_extractor that takes an image as input and returns cropped faces if detected. It converts the image to grayscale and uses the face detection classifier to locate faces.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/ebaaeeaf-2c09-4815-8376-cdd7953c75bf)

(x, y, w, h) is the loop variable. In the context of face detection, these values typically represent the coordinates and dimensions of a rectangle that outlines a detected face. Here's what each component of the tuple typically represents:
x: The x-coordinate of the top-left corner of the detected face.
y: The y-coordinate of the top-left corner of the detected face.
w: The width of the detected face (horizontal dimension).
h: The height of the detected face (vertical dimension).
faces is a collection (e.g., a list or array) 
So, this line of code initializes a loop that iterates through each detected face, and for each iteration, it assigns the values of x, y, w, and h from the current tuple in faces to these variables.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/8256c3a3-f1cd-4370-b214-d94526bae44d)


cropped_face is a variable that will store the cropped portion of the original image containing a detected face.
img is the original image (or a reference to it) that is being processed.
--img[y:y+h, x:x+w] is Python's array slicing notation used to extract a subregion of the image specified by the coordinates and dimensions of the detected face:
--img[y:y+h] extracts the portion of the image from the y-th row to the (y+h)-th row, representing the height of the face.
-- , separates the rows from the columns.
-- img[y:y+h, x:x+w] further restricts the subregion to span from the x-th column to the (x+w)-th column, representing the width of the face.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/ee088c3d-5454-48e9-ac65-5f6d37d49bbd)

Initialize Count: Initialize a variable called count to keep track of the number of face samples collected.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/b7147bf4-3ffe-4742-a0fa-3d8830d14f94)

Read a frame from the webcam.
Call the face_extractor function to attempt to detect and extract a face from the frame.
If a face is successfully extracted:
--Increment the count variable.
--Resize the extracted face to a fixed size (e.g., 200x200 pixels).
--Convert the face to grayscale.
--Save the grayscale face as an image with a unique name.
--Display the extracted face with a count label on top of it.
If no face is detected in the frame, print "Face not found."
Check if the 'Enter' key is pressed or if 100 samples have been collected. If so, exit the loop.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/ca68dca8-d7c8-4709-ad84-e92a9a67136d)














