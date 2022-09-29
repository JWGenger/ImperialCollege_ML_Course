# Non-technical Write-up - Description of the dataset, model and key findings

## The project
The instructions for the portfolio project were to choose a dataset that is related to my field of work and to solve the presented problem with one of the machine learning models I learned about in this programme.
I chose the "Breast Cancer Wisconsin (Diagnostic) Data Set" provided by UCI Machine Learning on kaggle (https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data?resource=download).
The dataset provides 30 measured features that characterise cell nuclei in images of fine needle aspirates (FNA) of breast masses obtained from patients, a sample ID and the diagnosis of the patients as outcome variable.
The task for this dataset is to predict whether the presented cancer is malign or benign based on the features of the nuclei.

## Results
I trained two models: one based on Support Vector Machines, one based on a Random Forrest Classifier. Both models showed the same predictive performance with the same accuracy, precision and recall to identify malignant and benign breast cancers.
The focus of this approach was to reliably predict malignant breast cancer from the provided 30 features of cell nuclei to support breast cancer diagnosis.

Both models developed here had an accuracy of about 97.4% which is the fraction of total samples that were correctly classified. This is already a very good result and means that only 2.6% of patients we incorrectly classified. 
Precision of both models was the same with about 98% for malignant samples. This means that 2% of malignant samples would be incorrectly classified as malignant samples. These patients would be recommended for medical treatment against breast cancer although they don't need it. They are false positives.
However, it still means we would only misclassify 2% of patients that have a good, benign tumor and suggest them for treatment although they don't need treatment. In a clinical setting, it is better to have false positives than false negatives because being false positive usually does not mean that patients will directly receive treatment but be subjected to further diagnoses and closer examination. Therefore, I am confident that these 2% of patients would be correctly classified as benign tumors in the follow-up diagnostics.
The recall describes how many of the positive samples were correctly predicted as positive by the classifier. This means how many malign tumors could we find and on the other hand (1-recall), how many did we miss, eg how many patients that need treatment would not be recommended for treatment? This is also known as sensitivity and true positive rate and is calculated as true poistives divided by the sum of true positives and false negatives. The recall for malign samples is 0.96 in both models. This means that we are correctly classifying 96% of the malign samples but are missing 4% of the malign samples which means that 4% of patients that need treatment wouldn't be recommended for treatment. Nevertheless, correctly identifying 96% of the malign tumors is still a very high and good result.
In conclusion, both models that I developed here are very successful in solving the task to develop a model that predicts malign samples from the 30 features extracted from images of breast masses.



