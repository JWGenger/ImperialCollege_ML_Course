# Model Card for the Portfolio Project

## Model architecture
I used a principal component analysis (PCA) to investigate the "Breast Cancer Wisconsin (Diagnostic) Data Set" provided by UCI Machine Learning on kaggle (https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data?resource=download) and developed two models to predict the breast cancer diagnosis from 30 features of cell nuclei in a fine-needle aspirate obtained from breast cancer patients.
The models that I developed based on a) Support Vector Machines and b) a Random Forrest Classifier. I conducted hyperparameter tuning of four or seven hyperparameters, respectively and used a hyperparameter tuning approach that based on Bayesian Optimization.

## Input
The input for the models are 30 features (decimal numbers) that describe characteristics of cell nuclei obtained via fine-needle aspirates from breast masses from breast cancer patients.

## Output
For each patient sample with 30 features (decimal numbers) that describe characteristics of cell nuclei, 1 patient ID and 1 diagnosis (outcome variable string), the models output a predicted diagnosis for a benign or malignant cancer. No identify or demographic information was detected.

## Performance metrics and performance of the developed models
F1 scores, overall accuracy of the model, precision and recall of the models are used to assess its predictive performance. The performance was evaluated by directly comparing the predicted diagnosis with the actual diagnosis of the patient on a test dataset that comprised randomly selected 20% of the original dataset (80% were used to train the models).
Accuracy of the two models is reported to be about 97%, precision on malignant samples about 98% and recall on malignant samples about 96%.
The precision on benign samples is about 97% and the recall is about 99%. However, detection of malignant samples is more important and the focus of this approach.

## Limitations
The models performance may be degraded by the performance of old image analysis software and the quality of the images obtained by machines from before 1995.




