# DeepFect - Defect Detection in Windshields using Deep Learning

##### Industry Partnership Project for 'UNCC ITCS 5152 Computer Vision' (Prof. Stephen Welch).
##### Partnering Companies - Vitro | Microsoft | Mariner

##### We aim to reduce the false positive alerts of defective windshields manufactured by Vitro by applying Computer Vision and Deep Learning techniques.
---

### Project Team 
Adhish Thite | Alzario Rolle | Pratik Kulkarni | Ved Paranjape

### The problem
The existing system at Vitro could not differentiate between the images which contained water on the windshield and the defective windshield images. So, the real problem was to build a system which is robust to false positives like these. 
Formally, the problem was to classify images into the following categories:
0 - Good
1 - Chip Edge (Defective)
2 - Water

### The process
The images that we got from Vitro were really high resolution images and they were distributed into the classes as:
Good - 1
Edge Chip - 4
Water - 6 
Summing the total number of images to 11. As this data wasnt enough to train a model, we divided these high resolution images into smaller segments. So, each images was divided into 64 smaller images. After preprocessing by removing the segmented images, we found out that the dataset was imbalanced. So, we augmented the images using various techniques such as sclaing, flipping, translation, etc. Then, we got a sufficiently good distribution of classes in the dataset after which we began the training procedure. 
As the training dataset contained 701 images in all, we were not sure if we could a deep learning model could be sufficiently trained so we decided to perform two indepenedent experiments.

The CSVM
In this experiment, we used the pre-trained VGG-16 model to create 4096 dimensional embeddings for each of the training images. We then used this data to train an SVM. An SVM works best for large number of features and small training data size. We performed hyper-parameter tuning for the SVM using grid search. 
Results: 
Accuracy - 95.14 %
False Positive Rate - 0.094

The Maverick
The Maverick is a convolution neural network built and trained from scratch to classify the images. The network essentially learns the curves, water droplet formations, chips and calssifies accordingly.
The architecture of model is as follows:
Conv --> Max Pool --> Conv --> Max Pool --> FC1 --> FC2
Results:
Accuracy - 98.05%
False Positive Rate - 0.039




---

