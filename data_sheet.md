# Datasheet Template

As far as you can, complete the model datasheet. If you have got the data from the internet, you may not have all the information you need, but make sure you include all the information you do have. 

## Motivation
## References: https://www.framinghamheartstudy.org/, https://www.kaggle.com/datasets/dileep070/heart-disease-prediction-using-logistic-regression; https://pmc.ncbi.nlm.nih.gov/articles/PMC4159698/#:~:text=On%20October%2012%2C%201947%2C%20the,site%20in%20the%20following%20month.

World Health Organization has estimated 12 million deaths occur worldwide, every year due to Heart diseases. Half the deaths in the United States and other developed countries are due to cardio vascular diseases. The early prognosis of cardiovascular diseases can aid in making decisions on lifestyle changes in high risk patients and in turn reduce the complications. 
This research intends to pinpoint the most relevant/risk factors of heart disease as well as predict the overall risk using logistic regression

- For what purpose was the dataset created? 
The goal of the dataset is to predict whether the patient has 10-year risk of future coronary heart disease (CHD).The dataset provides the patients’ information. It includes over 4,000 records and 15 attributes.

- Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)? Who funded the creation of the dataset?

The dataset was created by the Framingham HEart Study - which is a joint project of the National Heart, Lung, and Blood Institute (NHLBI) (part of the National Institutes of Health) and Boston University. 
It has been ongoing since 1948 and has involved multiple generations of participants to study cardiovascular disease. The US Public Health Service funds the study in conjunction with HArvard MEdical School.


 
## Composition

- What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)? 
Eachs instance of the dataset is made up of 15 variables. Each attribute is a potential risk factor. There are both demographic, behavioral and medical risk factors.

Demographic:
• Sex: male or female(Nominal)
• Age: Age of the patient;(Continuous - Although the recorded ages have been truncated to whole numbers, the concept of age is continuous)
Behavioral
• Current Smoker: whether or not the patient is a current smoker (Nominal)
• Cigs Per Day: the number of cigarettes that the person smoked on average in one day.(can be considered continuous as one can have any number of cigarettes, even half a cigarette.)
Medical( history)
• BP Meds: whether or not the patient was on blood pressure medication (Nominal)
• Prevalent Stroke: whether or not the patient had previously had a stroke (Nominal)
• Prevalent Hyp: whether or not the patient was hypertensive (Nominal)
• Diabetes: whether or not the patient had diabetes (Nominal)
Medical(current)
• Tot Chol: total cholesterol level (Continuous)
• Sys BP: systolic blood pressure (Continuous)
• Dia BP: diastolic blood pressure (Continuous)
• BMI: Body Mass Index (Continuous)
• Heart Rate: heart rate (Continuous - In medical research, variables such as heart rate though in fact discrete, yet are considered continuous because of large number of possible values.)
• Glucose: glucose level (Continuous)
Predict variable (desired target)
• 10 year risk of coronary heart disease CHD (binary: “1”, means “Yes”, “0” means “No”)


- How many instances of each type are there? 
there are 4000 instances of 15 variables.

- Is there any missing data?
yes some data is missing - as per Jupyter notebook there are 582 rows containing missing data.

- Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by    doctor–patient confidentiality, data that includes the content of individuals’ non-public communications)?
The dataset does not contain any confidential data or those protected by legal or doctor-patient privilege.

## Collection process

- How was the data acquired? 
The Framingham Heart Study acquired data through repeated, detailed medical examinations and lifestyle interviews of participants in Framingham, Massachusetts, beginning in 1948. This data collection included physical examinations, medical history, laboratory tests, and electrocardiograms. Over time, the study expanded to include offspring of the original participants (the Offspring cohort) and then a third generation, with data collected every few years. 

- If the data is a sample of a larger subset, what was the sampling strategy? 
the data is not a sample of a larger dataset

- Over what time frame was the data collected?
The data has been collected over the period of 1948 to 2022

## Preprocessing/cleaning/labelling

- Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)? If so, please provide a description. If not, you may skip the remaining questions in this section. 

Yes,preprocessing of the data was carried out. 
(1) removal of rows containing null variables
(2) removal of variables which were deemed not statistically significant (glucose, total cholesterol)

- Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? 
yes the raw data was saved.
 
## Uses

- What other tasks could the dataset be used for? 
The Framingham Heart Study  has been used for studies on stroke, dementia and cognitive functions, in conjunction with other studies.

- Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a dataset consumer might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other risks or harms (e.g., legal risks, financial harms)? If so, please provide a description. Is there anything a dataset consumer could do to mitigate these risks or harms? 
No

- Are there tasks for which the dataset should not be used? If so, please provide a description.
No


## Distribution

- How has the dataset already been distributed? 
The dataset is distributed on the Kaggle website at https://www.kaggle.com/datasets/dileep070/heart-disease-prediction-using-logistic-regression
- Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)?  
no
## Maintenance

- Who maintains the dataset?
the dataset is maintained by the Framingham Health Study 

