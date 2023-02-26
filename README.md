Aditya Khera ak4604.

2.  
What is one-hot encoding? Why is this important and how do you implement it in keras?
Setting each label to a unique binary input, this way A is [00000X1], B is [00000X10], and so on for the entire alphabet. This implementation allows us to represent categorical variables as binary arrays or vectors, making guessing and the usage of probabilities even possible. 
 
What is dropout and how does it help overfitting?
Dropout is a layer in our Keras sequential model used to help regularize the data and prevent overfitting. By knocking out a random 10% of the data and then boosting the values fo the ones that remains, we can use random selection and deletion to ensure our data does not have too many features and does not overrepresent majority data. 
 
Why is the softmax function necessary in the output layer?
It is necessary as the final layer to our model. This is because it transfers all these large and potentially confusing real score values and turns them into values between 0 and 1. This narrower range allows the model to make more precise estimations/predicitons. 
 
This is a more practical calculation.
  
Input image dimensions = 100x100x1 
Convolution layer with filters=16 and kernel size=(5,5)
(W_in−F+2P)/S+1 according to towardsdatascience.com


W = 100x100x1
F = 5x5
S = 1
K = 16


(100-5+2*1)/1+1 = 98 
depth out = out_channels = 16

conv output would be (98, 16)


MaxPooling layer with pool size = (2,2) What are the dimensions of the outputs of the convolution and max pooling layers?

Pooling layer input: W = 100, kernel size = 2, stride = 2.
Output size is W/F or 100/2 = 50
So we have a (50, 50) output form the pooling later


3.
Design choices and architecture are written below. Let me preface by saying I was not able to complete this assignment out of confusion. I had gone to a couple of office hours, watched at least 5 hours of youtube tutorials and still couldn’t figure it out. What I’ve submitted is pretty much what I’ve been able to understand. I can successfully split the training set into an 80-20 train and validation mix. I have also built a sequential model that has a logical architecture and process the go about predicting signals with. That being said, I’m hoping for partial credit and don’t know much more that I can do. 

The design choices were based off of the texts attached in the document. Working with Ujjwal Karn’s guide to CNNs, I built the model with layers in the following order: Conv, Drop, Pool, Conv, Drop, Pool , Flatten, Dense.
This in theory, mimics the paper Karn provided and will be low cost in terms of computation complexity. I think this would be a perfect balance, where the model builds, trains, and tests in a quick manner without trading off too much accuracy. 

The data is split in 80% train and 20% validation for the model, something I learned from the 5-fold training process covered in class. 
