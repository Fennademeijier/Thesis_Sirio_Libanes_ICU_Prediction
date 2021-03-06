# Thesis_Sirio_Libanes_ICU_Prediction
Thesis Code for predicting ICU admission 

For my Bachelor Thesis I took on the challenge of creating a model that can predict ICU admission of hospitalized COVID-19 patients. My model is built with data, and inspired by the Kaggle page 'COVID-19 - Clinical Data to assess diagnosis - Sírio-Libanês data for AI and Analytics by Data Intelligence Team'. The dataset and the tasks prescribed can be found on https://www.kaggle.com/S%C3%ADrio-Libanes/covid19 . 

I aim to build a random forest model that uses patient data to effectively predict whether or not the patient will need ICU admission during their hospital stay. Of all data, the MEDIAN extension for laboratory values and vital signs is used as to reduce the data dimensionality. Furthermore, constant features and features that show high multicollinearity are discarded. Patients that are not ICU admitted in any of the time windows are labelled negative and their 0-2h data is used. Lagged time-window data is used for patients that are ICU admitted, and this data is labelled positive. For example; if a patient is ICU admitted in the 4-6h time-window, their 2-4h data is used with a positive label in modeling. Patients that are ICU admitted in the 0-2h time-window are discarded. 

The 1.0 notebook that is uploaded fills missing data using foreward and backward fill. The 2.0 notebook uses multiple imputation to fill patient's missing data.

Judging by the evaluation criteria, forward and backward fill proves to be superior over iteratively imputing missing data. The final model has a PR AUC score of 0.84 and a recall score of 75.5%, and SHAP analysis identifies respiratory rate, age percentile, PCR, diastolic blood pressure, lymphocyte count, missingness,  urea, creatinine and lactate dehydrogenase as the top predictors of ICU  admission. In clinical settings, this model could be utilized as a prioritization tool,  which in turn aids resource allocation and ultimately reduces mortality and length of ICU stay. This study underscores the added value of the appliance of machine learning models in the COVID-19 pandemic. In the future, more research is warranted to to more accurately identify local and globalpredictors of ICU admission,  given the dynamical nature of the SARS-CoV-2 virus.


