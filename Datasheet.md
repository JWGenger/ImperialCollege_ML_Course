# Datasheet for the Porfolio Project

The instructions for the portfolio project were to choose a dataset that is related to my field of work and to solve the presented problem with one of the machine learning models I learned about in this programme. 
I chose the "Breast Cancer Wisconsin (Diagnostic) Data Set" provided by UCI Machine Learning on kaggle (https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data?resource=download). 
The dataset provides 30 measured features that characterise cell nuclei in images of fine needle aspirates (FNA) of breast masses obtained from patients, a sample ID and the diagnosis of the patients as outcome variable.
The task for this dataset is to predict whether the presented cancer is malign or benign based on the features of the nuclei.

## Motivation
### Purpose and Source of the dataset
The original source of the dataset are:

1. Dr. William H. Wolberg, General Surgery Dept.
University of Wisconsin, Clinical Sciences Center
Madison, WI 53792
wolberg '@' eagle.surgery.wisc.edu

2. W. Nick Street, Computer Sciences Dept.
University of Wisconsin, 1210 West Dayton St., Madison, WI 53706
street '@' cs.wisc.edu 608-262-6619

3. Olvi L. Mangasarian, Computer Sciences Dept.
University of Wisconsin, 1210 West Dayton St., Madison, WI 53706
olvi '@' cs.wisc.edu


The purpose of the dataset is not known. However, the dataset was used in several publications to train different kinds of machine learning models to diagnose breast cancer from fine-needle aspirates.
(see: W.N. Street, W.H. Wolberg and O.L. Mangasarian. Nuclear feature extraction for breast tumor diagnosis. IS&T/SPIE 1993 International Symposium on Electronic Imaging: Science and Technology, volume 1905, pages 861-870, San Jose, CA, 1993.,
O.L. Mangasarian, W.N. Street and W.H. Wolberg. Breast cancer diagnosis and prognosis via linear programming. Operations Research, 43(4), pages 570-577, July-August 1995.,
W.H. Wolberg, W.N. Street, and O.L. Mangasarian. Machine learning techniques to diagnose breast cancer from fine-needle aspirates. Cancer Letters 77 (1994) 163-171.) and others: https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29). Therefore, it meets the need to refine measures in cancer diagnosis to predict disease and patient outcomes with higher accuracy.

The dataset is publicly available as general training dataset for educational purposes, e.g. in machine learning education. It can be accessed for example on kaggle: https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data/metadata?resource=download or via the UCI Machine Learning Repository: https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29 .

## Composition
### General description of the dataset
The dataset comprises one data table file with 32 columns of features that were computed from digitized images of fine-needle aspirates of breast masses from breast cancer patients.
These features describe characteristics of the cell nuclei that are present in the images. 30 columns are features of the cell nuclei in decimal numbers,
one column is an ID of the corresponding patient, one column is a string that represents the diagnosis of this patient (M for malign, B for benign breast cancer).
Cell nucleus features comprise data like mean radius, mean texture, mean perimeter, etc. of the cell nuclei in the images. In general, means for ten real-valued features were computed like
radius, texture, perimeter, area, smoothness, compactness, concavity, concave points, symmetry and fractal dimension. Moreover, other columns contain the standard errors and mean of the three largest values of these features.
All features were recorded for four significant digits and there are no missing values for records in the data table. The dataset was created from fine-needle aspirates from 357 patients diagnosed with benign tumors and 212 patients diagnosed with malignant tumors (total: 569).
The features are not raw data but the product of an image analysis. The data are labelled with an anonymized patient ID. No relationships between instances are indicated, no data splits are given or recommended. It is a self-contained dataset.

The dataset does not contain any confidential data of patients and it is not even possible to clearly identify a subpopulation like women which would be a good guess for such a dataset. However, breast cancer is possible in men as well but gender is not indicated.
It is also not possible to identify single individuals and does not contain further health data or identification for the patients from which the samples were taken.

## Collection process
It is not clear how and by whome the dataset was created, which institution conducted the sample collection and which institution conducted the image analysis. The dataset was donated by Nick Street on 01.11.1995. It is not known whether an ethical review process was conducted when the data was created but it can be assumed that it meets the academic standards of the medical scientific community
as it is provided by academic staff of the University of Wisconsin. Further information about the process how consent was obtained from patients that provided samples is not available.

## Preprocessing/cleaning/labelling
The dataset was prepared as a training dataset for educational purposes in the machine learning field. It is unknown how the dataset was modified from the original dataset for this purpose. The raw dataset is not provided.

## Uses
The dataset is in general used as training dataset for educational purposes in the machine learning field as a Multivariate dataset with real attributes to solve classification problems.
Further information about the use of this dataset are not given.

## Distribution
The dataset is publicly available via kaggle (https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data?resource=download&select=data.csv) where it was provided by UCI Machine Learning which is also the official owner of this dataset on kaggle. It can also be retrieved from the UCI Machine Learning repository (https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29). 
The license of the dataset is CC BY-NC-SA 4.0 and it can be freely used by the public. There are no further terms of use given.

## Maintenance
There is no information given on whether or how the dataset will be maintained or updated.













