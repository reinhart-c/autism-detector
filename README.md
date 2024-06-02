# Autism Detector


# Skills and Tools
- Python
- NumPy
- Pandas
- Scikit-learn (sklearn)
- Nilearn
- Nibabel


# Problem
Autism spectrum disorder (ASD) is a developmental disorder caused by differences in the brain and it causes difficulties in communication, social interaction, and monotonous behaviors. Even though some symptoms are typically identifiable between the ages of one and two, many children do not receive a medical diagnosis of ASD until they are significantly older. The problems from ASD are irreversible if it is not identified and treated at an early age. WHO states that one in 160 children have ASD and they frequently present with other disorder like anxiety, depression, and attention deficit hyperactivity disorder (ADHD).

These days, ASD is usually diagnosed using standardized instruments like the Autism Diagnostic Observation Scale and the Autism Diagnostic Interview-Revised scale. But this method takes a lot of time, and is subjective. Furthermore, because the scales are not totally objective, inaccurate outcomes may occur. Numerous studies have applied traditional machine learning methods such as SVM, logistic regression, random forest, and KNN. Some also applied deep learning like CNN and DNN for the classification of ASD. 


# Solution
In our study, we focus on increasing the accuracy of four commonly used methods, which are support vector machine, random forest, k-nearest neighbor, and logistic regression. Our aim is to improve the accuracy of these methods in detecting autism from fMRI data. With more precise and reliable detection methods, we can provide better support and intervention strategies for individuals with autism. 


# Method
In the process of analyzing brain connectome data, the initial step involves collecting data. We fetched the data using fetch_abide_pcp function from Nilearn. This dataset was preprocessed by Preprocessed Connectomes Project (PCP) using Configurable Pipeline for the Analysis of Connectomes (CPAC) pipeline. After fetching the dataset, we apply the BASC multiscale atlas to each image, then we extract the time series. After that we resize the number of features so that all images have the same dimension. Afterwards, we use those time series to make a correlation matrix, which we use to select the features based on the feature’s correlation to the target class. After getting those features, we used standard scaler from Sklearn to scale those features, and reduce the dimension using PCA. Lastly, we split those data into train, validation, and test.

The models are then trained using the train data, and a cross-validation is performed using the validation data and grid search cross-validation. By doing this, we are able to determine the model's optimal parameter, which we then use to test the model with test data. Finally, we use a confusion matrix and classification report to conduct an evaluation.
