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

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/b9444f7c-ed32-4521-8f6b-744f9ab734af)


Initialize the LBPH (Local Binary Pattern Histogram) Face Recognizer model.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/b14455a5-2f90-479a-9c4d-ac03767257d1)


Train the LBPH Face Recognizer model using the training data (Training_Data) and labels (Labels) collected earlier.

![image](https://github.com/neelay-16/Face_Detection/assets/135517502/2bea6fdd-21ab-475e-9adf-150269e89870)
