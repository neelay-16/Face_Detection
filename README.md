# Face_Detection

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

# Training the model

Initialize two empty lists (Training_Data and Labels) to store the training data (grayscale face images) and corresponding labels (indices).

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/dc39bcb7-7789-43af-b69b-3496414a615a)


The for loop iterates over the elements in the onlyfiles collection. It uses the enumerate() function, which is used to iterate over both the elements and their indices in the collection.
i is the index of the current element in the onlyfiles collection, and files is the value (i.e., the filename) of the current element.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/214f0a71-baa3-4ffa-84eb-07edb91775fd)

This line constructs the full path to the current image file by concatenating the data_path (which represents the directory where the image files are located) with the current filename from onlyfiles.
image_path is a string variable that holds the full path to the current image file.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/1f78122f-c262-473a-bdb2-c06f4372edd9)

This line appends the grayscale image (images) to a list called Training_Data. It converts the image to a NumPy array using np.asarray() and specifies the data type as np.uint8, which is an 8-bit unsigned integer data type commonly used for image data.
This list (Training_Data) is typically used to store a collection of images that will be used for training some machine learning model, such as a neural network.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/3a088ac4-cf89-4901-bc77-eaa005884e5d)

This line appends the value of i to a list called Labels. It seems that i corresponds to the index of the current image file in the onlyfiles collection.
This list (Labels) is typically used to store labels or class identifiers associated with the images in Training_Data. In this case, it appears to be used as a way to associate a label or class with each image.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/71042fc7-cccb-4030-b69e-ad1db43063a2)

Convert the Training data and Labels list to a NumPy array for further processing.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/6293d544-4056-4862-8129-ffd43a8a1f27)




