# PROJECT TITLE 


## NON-TECHNICAL EXPLANATION OF YOUR PROJECT
100 words to explain what your project is about to a general audience. 
The purpose of the project is to attempt to create a model that predicts the onset of Coronary Heart Disease in 10 years time, based on a patients' Demographic, Behavior, Medical history and Medical- current readings.
It is based on data gathered in the town of Framingham in the USA. 


## DATA
A summary of the data you’re using, remembering to include where you got it and any relevant citations. 

The data was sourced from KAggle at: https://www.kaggle.com/datasets/dileep070/heart-disease-prediction-using-logistic-regression
The dataset was created by the Framingham HEart Study - which is a joint project of the National Heart, Lung, and Blood Institute (NHLBI) (part of the National Institutes of Health) and Boston University. 
It has been ongoing since 1948 and has involved multiple generations of participants to study cardiovascular disease. The US Public Health Service funds the study in conjunction with HArvard MEdical School.
References: https://www.framinghamheartstudy.org/; https://pmc.ncbi.nlm.nih.gov/articles/PMC4159698/#:~:text=On%20October%2012%2C%201947%2C%20the,site%20in%20the%20following%20month.

*Input:** Describe the inputs of your model 

• Sex: male or female(Nominal)
• Age: Age of the patient;(Continuous - Although the recorded ages have been truncated to whole numbers, the concept of age is continuous)
• Current Smoker: whether or not the patient is a current smoker (Nominal)
• Cigs Per Day: the number of cigarettes that the person smoked on average in one day.(can be considered continuous as one can have any number of cigarettes, even half a cigarette.)
• BP Meds: whether or not the patient was on blood pressure medication (Nominal)
• Prevalent Stroke: whether or not the patient had previously had a stroke (Nominal)
• Prevalent Hyp: whether or not the patient was hypertensive (Nominal)
• Diabetes: whether or not the patient had diabetes (Nominal)

• Tot Chol: total cholesterol level (Continuous)
• Sys BP: systolic blood pressure (Continuous)
• Dia BP: diastolic blood pressure (Continuous)
• BMI: Body Mass Index (Continuous)
• Heart Rate: heart rate (Continuous - In medical research, variables such as heart rate though in fact discrete, yet are considered continuous because of large number of possible values.)
• Glucose: glucose level (Continuous)

**Output:** Describe the output(s) of your model
10 year risk of coronary heart disease CHD (binary: “1”, means “Yes”, “0” means “No”)

## MODEL 
A summary of the model you’re using and why you chose it. 
The chosen is the logistic regression: This model is well suited to model binary outcomes, because it uses a sigmoid function to wrap the probability between 0 and 1. 

Here’s why it’s a good fit:

Probability Output: Instead of predicting numbers directly, logistic regression predicts the probability of belonging to one of the two classes.
The logistic (sigmoid) function ensures probabilities are wrapped between 0 and 1, which makes them interpretable.

Interpretable coefficients: Coefficients can be interpreted in terms of odds ratios, which is especially useful in medical contexts.



## HYPERPARAMETER OPTIMSATION
Description of which hyperparameters you have and how you chose to optimise them. 

The 2 hyperparameter that were optimised were:
(1) Regularisation - L2 Penalty -  aka 'c'
a penalty is added to the loss function to decrease the complexity of the model - to stop it from over-fitting. The effect of L2 regularisation is established by changing the values of C between 10exp-2, 10exp-6.
the model is set with different values of C ranging from 10exp-2, 10exp-6 , and then evaluating the respective model accuracy. A graph is then plotted showing the accuracy against different values of C.(See Graph attached: Hyp1_regularisarion_c.jpg)

(2) Probability Threshold (T)
Once the optimal value of C is established, we then choose the probability threshold. This is set at 0.5 by default however, it can be modified to achieve the optimal FalseNegative/FalsePositive Rates.
In order to find the optimal probability threshold, the prediction of dataset is carried out with a range of threshold. The optimal threshold is chosen at the intersection of graphs where we get the most balanced FNRates/FPRate. See Graph:Hyp2_prob_threshold.jpg

## RESULTS
A summary of your results and what you can learn from your model 

The final model produces a confusion matrix as attached: confusion_matrix_heart.jpg

sensitivity:  0.6476
specificity:  0.7177
accuracy :  0.7077
tn, fp, fn, tp
450,177,37, 68

True Negatives (TN) = 450 → Healthy people correctly predicted as healthy
False Positives (FP) = 177 → Healthy people incorrectly predicted as having Coronary HEart Disease(CHD)
False Negatives (FN) = 37 → People with CHD incorrectly predicted as healthy
True Positives (TP) = 68 → People with CHD correctly predicted as having CHD

1. Risk of missing cases (False Negatives)
37/ 105 actual heart disease patient.  35% 
In medical settings, this is a significant risk — undiagnosed patients may not receive needed treatment.

2. Burden from false alarms (False Positives)
177 false alarms out of 627 healthy patients. 28% of healthy people being flagged incorrectly. Causes extra tests, costs, and anxiety, but it’s less severe than missing a sick patient

3. Balance between Sensitivity & Specificity
The model is slightly better at ruling out disease (Specificity: 71.8%) than detecting it (Sensitivity: 64.8%). Probability Threshold can be tuned to shift the balance toward higher sensitivity, even if false positives increase.

4. Clinical meaning
Right now: 2 out of every 3 heart disease patients are caught, but 1 out of 3 are missed.

Trade-off: You could improve patient safety by catching more cases, at the expense of more false alarms.

Accuracy = 70.77% means the model gets about 71 out of 100 predictions correct overall.

Sensitivity(How well does it catch true cases)  = 64.76% → Out of all cases, model correctly identifies about 65%. Therefore 35% of CHD  patients are missed (false negatives) - this is risky in healthcare since missing a disease can be dangerous.

Specificity (How well does it rule out healthy patients)
Specificity = 71.77%. Out of all patients without heart disease, about 72% are correctly identified as healthy. This also means 28% of healthy people are wrongly flagged as having heart disease (false positives), which could cause unnecessary further testing or anxiety.

Trade Offs: The model is slightly better at detecting healthy people (specificity) than detecting sick people (sensitivity).

Improvements: Depending on the clinicians resources, the probability threshold(t) can be tuned to increase sensitivity. Furthermore, correlation coefficients can be added to improve the model.


## (OPTIONAL: CONTACT DETAILS)
If you are planning on making your github repo public you may wish to include some contact information such as a link to your twitter or an email address. 
avishramyead@gmail.com

