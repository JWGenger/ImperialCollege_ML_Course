# Prediction of malignant breast cancer from cell nucleus features from fine-needle aspirates from breast masses

## Non-technical explanation of my project and Results
The instructions for the portfolio project were to choose a dataset that is related to my field of work and to solve the presented problem with one of the machine learning models I learned about in this programme.
I chose the "Breast Cancer Wisconsin (Diagnostic) Data Set" provided by UCI Machine Learning on kaggle (https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data?resource=download).
The dataset provides 30 measured features that characterise cell nuclei in images of fine needle aspirates (FNA) of breast masses obtained from patients, a sample ID and the diagnosis of the patients as outcome variable.
The task for this dataset is to predict whether the presented cancer is malign or benign based on the features of the nuclei.

I trained two models: one based on Support Vector Machines, one based on a Random Forrest Classifier. Both models showed the same predictive performance with the same accuracy, precision and recall to identify malignant and benign breast cancers.
The focus of this approach was to reliably predict malignant breast cancer from the provided 30 features of cell nuclei to support breast cancer diagnosis.

Both models developed here had an accuracy of about 97.4% which is the fraction of total samples that were correctly classified. This is already a very good result and means that only 2.6% of patients we incorrectly classified. 
Precision of both models was the same with about 98% for malignant samples. This means that 2% of malignant samples would be incorrectly classified as malignant samples. These patients would be recommended for medical treatment against breast cancer although they don't need it. They are false positives.
However, it still means we would only misclassify 2% of patients that have a good, benign tumor and suggest them for treatment although they don't need treatment. In a clinical setting, it is better to have false positives than false negatives because being false positive usually does not mean that patients will directly receive treatment but be subjected to further diagnoses and closer examination. Therefore, I am confident that these 2% of patients would be correctly classified as benign tumors in the follow-up diagnostics.
The recall describes how many of the positive samples were correctly predicted as positive by the classifier. This means how many malign tumors could we find and on the other hand (1-recall), how many did we miss, eg how many patients that need treatment would not be recommended for treatment? This is also known as sensitivity and true positive rate and is calculated as true poistives divided by the sum of true positives and false negatives. The recall for malign samples is 0.96 in both models. This means that we are correctly classifying 96% of the malign samples but are missing 4% of the malign samples which means that 4% of patients that need treatment wouldn't be recommended for treatment. Nevertheless, correctly identifying 96% of the malign tumors is still a very high and good result.
In conclusion, both models that I developed here are very successful in solving the task to develop a model that predicts malign samples from the 30 features extracted from images of breast masses.

## Data 
The instructions for the portfolio project were to choose a dataset that is related to my field of work and to solve the presented problem with one of the machine learning models I learned about in this programme. 
I chose the "Breast Cancer Wisconsin (Diagnostic) Data Set" provided by UCI Machine Learning on kaggle (https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data?resource=download). 
The dataset provides 30 measured features that characterise cell nuclei in images of fine needle aspirates (FNA) of breast masses obtained from patients, a sample ID and the diagnosis of the patients as outcome variable.
The task for this dataset is to predict whether the presented cancer is malign or benign based on the features of the nuclei.The purpose of the dataset is not known and it is not given who funded the creation of the dataset on behalf of which entity. However, the dataset was used in several publications to train different kinds of machine learning models to diagnose breast cancer from fine-needle aspirates.
(see: W.N. Street, W.H. Wolberg and O.L. Mangasarian. Nuclear feature extraction for breast tumor diagnosis. IS&T/SPIE 1993 International Symposium on Electronic Imaging: Science and Technology, volume 1905, pages 861-870, San Jose, CA, 1993.,
O.L. Mangasarian, W.N. Street and W.H. Wolberg. Breast cancer diagnosis and prognosis via linear programming. Operations Research, 43(4), pages 570-577, July-August 1995.,
W.H. Wolberg, W.N. Street, and O.L. Mangasarian. Machine learning techniques to diagnose breast cancer from fine-needle aspirates. Cancer Letters 77 (1994) 163-171.) and others: https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29). Therefore, it meets the need to refine measures in cancer diagnosis to predict disease and patient outcomes with higher accuracy.

The dataset is publicly available as general training dataset for educational purposes, e.g. in machine learning education. It can be accessed for example on kaggle: https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data/metadata?resource=download or via the UCI Machine Learning Repository: https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29 .

## Model and hyperparameter optimisation
I performed first a PCA analysis to get an idea of the distribution of the dataset and most important drivers of variance and to check whether I could identify features that drive difference between the two classes 'benign' and 'malign'. Then, I trained two models: one based on Support Vector Machines, one based on a Random Forrest Classifier. 

The presented problem is a classification problem and the advantage of an SVM approach is that it is very useful for binary classification problems where we need to find a decision boundary between two classes in high dimensions. The SVM function sklearn is also supported by additional techniques like the integrated kernel trick (eg application of mathematical transformations on the input data or introduction of axiliary variables to turn non-linear relationships between input and output into a linear relationship). I applied an SVM approach and tuned four hyperparameters (C, gamma, degree and kernel) using bayesian optimisation as it is part of the sci-kit optimization package skopt.

I chose to tune the four selected hyperparameters for the following reasons:
- Kernel: Kernels are the mathematical functions used in SVM approaches that take the input data and transform it into the required form, e.g. here provide different ways of defining a decision boundary. I chose the kernel options linear, poly and rbf which will create a linear or polynomial decision boundary or one based on a radial basis function (RBF).
- C: This is the hyperparameter that controls the allowed error in defining the decision boundary. Low values for C allow low errors and large Cs allow large errors or misclassification, respectively.
- Gamma: Gamma is a hyperparameter used for the polynomial and RBF kernel and is not used for the linear kernel. It defines the curvature in the decision boundary.
- Degree: This is the hyperparameter that defines the degree of the polynomial function used as kernel to define a decision boundary and is ignored in all other kernels.

In the second approach, I wanted to use a Random Forrest Classifier with Bayesian Optimization hyperparameter tuning for the 7 hyperparameters n_estimators, max_features, max_depth, min_samples_split, criterion, min_samples_leaf and bootstrap. Although we could extract the feature importance from the SVM approach before because we used a linear kernel, one drawback of SVMs is usually their low interpretability which is better with the RFC approach. In the following, I explored whether I could get a better classifier with the RFC approach. The distadvantage of an RFC model is that it is slower than an SVM model because it generates a lot of different trees.

I tuned the following hyperparameters:
- n_estimators: the number of trees in the forrest
- max_features: the maximum number of features considered for splitting a node
- max_depth: the maximum number of levels in each decision tree
- min_samples_split: the minimum number of data points that will be placed in a node before it will be split
- criterion: the function we use to measure the quality of the split, e.g. the information yield
- min_samples_leaf: the minimum number of data points allowed in a lead node
- bootstrap = method for sampling data points

## Results 

Taken together, I trained two models: one based on Support Vector Machines, one based on a Random Forrest Classifier. Both models showed the same predictive performance with the same accuracy and F1 and performed far better than a naive classifier that would classify all samples as malign samples. The naive classifier had an accuracy of 41.2% which means that the misclassification rate would be 58.8%. This would lead to 58.8% of patients not receiving the treatment they would need (or would receive treatment although they don't need it). Being treated for breast cancer although they wouldn't need this treatment would mean surgical interventions and strong medical treatment regimes although not necessary and thereby it would lead to a drastic decrease in life quality.

On the other hand, both models developed here had an accuracy of about 97.4% which is the fraction of total samples that were correctly classified. This is already a very good result. We will look more specifically at different parameters of the predictive performance in the following.

According to the classification report given above, precision of both models was the same with about 0.98 for malign samples (1) and 0.97 for benign samples (0). Precision is the fraction of correct predictions in the positive class (true positives among true and false positives). This means that 2% of malign samples would be incorrectly classified as malign samples. These patients would be recommended for medical treatment against breast cancer although they don't need it. They are false positives.

However, it still means we would only misclassify 2% of patients that have a good, benign tumor and treat them although they don't need treatment. In a clinical setting, it is better to have false positives than false negatives because being false positive usually does not mean that patients will directly receive treatment but be subjected to further diagnoses and closer examination. Therefore, I am confident that these 2% of patients would be correctly classified as benign tumors in the follow-up diagnostics.

The recall describes how many of the positive samples were correctly predicted as positive by the classifier. This means how many malign tumors could we find and on the other hand (1-recall), how many did we miss, eg how many patients that need treatment would not be recommended for treatment? This is also known as sensitivity and true positive rate and is calculated as true poistives divided by the sum of true positives and false negatives. The recall for malign samples is 0.96 in both models. This means that we are correctly classifying 96% of the malign samples but are missing 4% of the malign samples which means that 4% of patients that need treatment wouldn't be recommended for treatment. Nevertheless, correctly identifying 96% of the malign tumors is still a very high and good result.

In conclusion, both models that I developed here are very successful in solving the task to develop a model that predicts malign samples from the 30 features extracted from images of breast masses.
