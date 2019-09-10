# Medication Dosage and Frequency Predictions

### This notebook is a complete walkthrough of the data preprocessing, analysis, and machine learning model design used for the medication titration tool as part of my internship at Veta Health during Summer 2019. This is not the final version since I have saved the final version only for Veta Health. However, this notebook does demonstrate the general work. Also, please note that none of the data that is used in this notebook has been provided. That data can only be accessed by permission of MIT Lab for Computational Physiology. In order to access for the data, you need to [request access].(https://eicu-crd.mit.edu/gettingstarted/access/). Additionally, the method of implementation is not shown in this notebook since that is solely meant for Veta Health. 

####  This notebook shows the lowest performance achieved all iterations. However, it is meant to demonstrate how drug dosafe and frequency can be predicted using clinical features. 


### Problem: 

Doctors regularly prescribe their patients medication even after they have left the hospital. The prescribing of those medications and the recommended frequencies is often based on factors such as pre-existing conditions, patient weight and height, age, and lab tests. However, it is often difficult to accuractly prescribe a dosage and frequency of a medication for any patient. It is therefore of interest to design a machine learning based model to predict ideal medication dosages and frequencies. 

### Challenges: 

Clinical/patient data is often very difficult to come by. Due to the high level of security required to protect patient information and the risk associated with the identification of patients using their clinical information, most patient data found within EHRs is not publicly available. Additionally, most patient data is very sparse and often incomplete. There also exists the challenges associated with medical termonologies used to define various features of clinical data. The terminologies used are not always consistent. The incompleteness and sparsity of clinical data makes it extremely difficult to produce statistical models that can acccuractely make any predictions of any kind at all, let alone the prediction of ideal medication and dosage for a patient. 

### Solutions: 

Fortunately, there are some sources of clinical data available. The most well-known and widely used ones are the [MIMIC III critical care database](https://mimic.physionet.org) and the [eICU Collaborative Research Database](https://eicu-crd.mit.edu) curated by the Lab for Computational Physiology (LCP) at MIT. These two databases contains over 100 GB of patient data and is generously provided for free upon request. This data has been retrieved and used for the final modeling in this project. Prior to the availability of this data, other datasets were also used to make predictive models. Please refer to the the "Project Iterations" folder for those respective notebooks. You will find that those first iterations with those datasets were fairly unsucessful.

Even though there is significant data available through the LCP, it is not always complete data. However, it does provide easy ways to combine tables in its relational database to get tables in which one can find data for individual de-identified patients such as which medications they take, their vitals, and some of the tests that were administered to them. After preprocessing the data, transforming it, it was successfully used to build a predictive model for drug dosage and frequency prediction. Although it doesn't provide consistent results from medication to medication, it is generally successful for multiple medications and is a great starting point upon which a preliminary medication titration product can be designed and deployed for use. 

### Dependacies:

All code found in this notebook has already been run. I have provided outputs of the results as I go through each bit of code. However, in order to rerun it and actually use it for more medication datasets, you will need the following on your machine, either locally or in a virtual environment. 

> Python 3.6

> Pandas

> Numpy

> Scikit-learn

> XGBoost (not Python wrapper version, actual XGBoost package)

> Tensorflow (2.0 is fine), Keras

> Matplotlib
