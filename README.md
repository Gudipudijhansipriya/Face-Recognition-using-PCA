# Face-Recognition-using-PCA
The Principal Component Analysis ( is one of the most effective image recognition and compression algorithms ever developed [ PCA reduces the huge dimensionality of the data space (observed variables) to the smaller intrinsic dimensionality of feature space (independent variables), which is required to economically characterize the data.

The covariance matrix of a training image set yields these eigenvectors [2],[ The weights are calculated after determining a set of the most relevant eigenfaces. A support vector classifier obtains project input images to principal components and classification. The amount of variance retained is misgiven by the number of principal components we choose. The dataset is obtained from the Github repository Code Heroku and implemented using python3.

# DESCRIPTION:
# Data Collection:
In this step, we obtained our dataset from the Github repository Code Heroku. There are 40 people in the dataset and each person has ten images with different shades. Each image is 64X64 pixels that are equal to 4096 columns. I have taken each image and fl attened it into a matrix format.

The dataset is split into testing and training datasets having both x and y values. Where x represents pixels and y represents the target value(person).

# Apply PCA:
The first thing we apply is a PCA transform to the input dataset.The data is projected to a PCA subspace by extracting the direction having maximum variance from the images. By applying PCA we derive the first few principal components of the dataset where each highlights different objects or body parts like sp ectacles, moustaches and so on from the picture.

# Select number of components:
To know how many components, we need to recognize the image, we will plot a graph and get to know at what level we are getting the accuracy of the image. In the graph we observ e for the first few principal components we observe maximum variance. In the principal components, we can observe some bright spots where it indicates that there is maximum variance at that particular part. At 150, we get more variation getting captured wi th 97% accuracy.

# Project input images to principal components:
We represent the dataset as the weighted sum of the eigenvectors until the number of principal components that the image can recognize the face. The weights will be changed for each image, but the eigenvectors will be the same for the entire dataset. We can generate the eigenvectors at any point in time. We will provide the eigenfaces to our machine learning model. The model will check the similarities with the weights.

# Initialization of classifier and fitting the training data set:
A classifier object for the Support vector classifier is created with a nonlinear kernel and the training data set is fits into it. This is done with the SCV function in sklearn library. The kernel used is rbf with regularisation parameter of 1000 and 0.01 gamma.Then the training data after transforming to pca is fit into it.

# Performing testing and generating classification reports:
PCA is applied on the test set to ensure everything is in PCA space. Then predictions are made by the model for the test set. To analyze the prediction’s accuracy, we obtain the classification report showing a weighted average precision of 0.98 and a recall of 0.93, where precision is how accurate the model is whereas recall is the number of times accuracy is achieved.

# CONCLUSION:
From this study we can determine that a lower dimensional space exists that can more efficiently represent a dataset(closely). PCA finds such low-dimensional projections that maximally preserve variance in the data. The amount of variance retained is given by several principal components we choose. Here, 4096 features were reduced to 150 and the model built gives weighted average precision of of 0.98 and a recall of 0.93. We get 93% accuracy of face recognition.

# REFERENCE:
[1] Erwin et al 2019 J. Phys.: Conf. Ser. 1196 012010 https://iopscience.iop.org/article/10.1088/1742 6596/1196/1/012010/pdf

[2] Liton Chandra Paul Abdulla Al Sumam, Face Recognition Using Principal Component Analysis Method, International Journal of Advanced Research in Computer Engineering Technology ( Volume 1, Issue 9, November 2012. http://ijarcet.org/wp content/uploads/IJARCET VOL 1 ISSUE 9 135 139.pdf

[3] M.A. Turk and A.P. Pentland, “Face Recognition Using Eigenfaces”, IEEE Conf. on Computer Vision and Pattern Recognition, pp. 586 591, 1991.
