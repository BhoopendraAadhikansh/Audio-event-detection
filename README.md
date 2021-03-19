# audio-event-detection
TRAIN MODEL:-
Step 1: Read csv file (labels_train.csv) containing the names of all audio files with their labels.
Step 2: Perform feature extraction of audio files using STFT(short time fourier transform) and considering their absolute values.
Step 3: Resize the audio files and append it in a list. Converting list of absolute values to an array. This array comes out to be x_train.
Step 4: From above csv file, we extract labels and perform One_hot_encoding . Then , one_hot_encoded output comes as y_train.
Step 5: Perform preprocessing of train data (x_train) using keras
Step 6: Build the CNN model using Keras:
1) Import Sequential model from keras
2) Input layer: Number of Input nodes = input shape (shape of x_train)
![image](https://user-images.githubusercontent.com/59888656/111766984-2c210700-88cc-11eb-92ae-d9675acc4dbf.png)
3) Number of hidden layers :
• Convolution 2D layer with 32 nodes having activation ‘relu’(ramp function)
• Convolution 2D layer with 64 nodes having activation ‘relu’
• MaxPooling 2D layer (down-sampling)
• Dropout layer
• Flatten layer
• Dense (Fully-connected) layer with 128 nodes having activation ‘relu’
• Dropout layer
4) Output layer: Dense layer with number of unique classes of labels as number of nodes having activation ‘softmax’
5) Compile the model using categorical cross-entropy loss function
6) Fit the model into the training data (x_train , y_train)
Step 7: Save the model

TASK 1:-
Step 1: Read the test dataset csv file and extract x_test ,y_test.
• For x_test, load .npy files corresponding to a csv file, resize it and convert into an array
• Similarly, for y_test , extract labels
Step 2: Evaluation of model using test dataset:
1) Accuracy of the model
2) Predicted Output by the model
Step 3: Write the evaluation to a new csv file
![image](https://user-images.githubusercontent.com/59888656/111767156-68546780-88cc-11eb-9703-82b892d3194a.png)


TASK 2:-
Step 1: Read the test dataset csv file and split audio files to form an array.
Step 2: Evaluation of model using test dataset:
1) Distance of the model
2) Predicted Output by the model
Step 3: Write the evaluation to a new csv file

![image](https://user-images.githubusercontent.com/59888656/111767224-76a28380-88cc-11eb-83eb-b69c83f5c1cc.png)


