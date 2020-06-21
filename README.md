# MNIST-data-classification
MNIST data classification using ML approach

• Feature Extraction
– We use two methods for feature extraction: Feature extraction using
HOG feature detection and LBPH method.
– Histogram of Oriented Gradients (HOG) feature detection to extract
the feature of MNIST dataset.
– LBPH algorithm is the combination of Local Binary Patterns (LBP)
and Histograms in given radius with number of points used for his-
togram bins.

• Feature Learning We use the logistic regression model to train the ex-
tracted features with the label and predict the output for each test image
features extracted.

• Classification accuracy
– Acuuracy with LBPH feature extraction As mentioned the two
variations resulted in below accuracy : With 64 bins and 16 radius -
54.68% accuracy With 64 bins and 2 radius - 58.63% accuracy
– Acuuracy with HOF feature extraction We experimented with
two different cell size for HOG feature extraction: 7 x 7 and 14 x
14. With the above cell size we got 94.22% accuracy with 7 x 7
cell size and 83.43% accuracy with 14 x 14 cell size. This indicates
the importance of feature extraction. With 7 x 7 cell size we got
72 features for each sample while with 14 x 14 cell size we got 36
features for each sample.
– Impact of features extracted is clearly visible in the accuracy ob-
tained.

MNIST data classification using DL approach

• Conv2D
A filter (3x3) slides over the input image (28x28) with stride=1and com-
putes dot product to give a ‘feature map (26x26)’. (size of input image –
size of filter + 1) = 28 – 3 + 1 = 26
For RGB image, 3 distinct filters are stacked to produce 3 feature maps
(depth=3). In case of MNIST images, depth of feature map is 1 as their
pixel values are grayscale.
For 3 convolutional layers, the output feature map is 22x22.
• MaxPooling
Largest element from the feature map within a window of 2x2 is consid-
ered, thereby resulting in an output image of size 11x11.
This reduces the spatial size of the input and also computations in the
network.
• Flatten
This layer converts the 2D input image (13x13) to a 1-D vector (11x11x24
= 2904)
• Fully Connected (FC)
First FC layer contains 200 neurons with rectifier activation function
(ReLu). This layer takes the inputs from the feature analysis and ap-
plies weights to predict the correct label.
Final FC layer containing 10 neurons with softmax gives the final prob-
abilities for each class label. The neuron with a maximum probability is
the output for the model.

Maximum accuracy obtained with this model is 98.71% with 3 convlutional layers, 0.5 dropout, 200 neurons and 25 epochs.
