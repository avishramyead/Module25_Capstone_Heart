# Model Card

See the [example Google model cards](https://modelcards.withgoogle.com/model-reports) for inspiration. 

## Model Description

**Input:** Describe the inputs of your model 

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

**Model Architecture:** Describe the model architecture you’ve used

The chosen model for this is the Logistic Regression - which is more appropriate for binary outcomes (than linear regression) since it uses an underlying sigmoid function to model the probabilityv(between 0 and 1).


## Performance

Give a summary graph or metrics of how the model performs. Remember to include how you are measuring the performance and what data you analysed it on. 

The performance of the model based on the chosen hyperparamters :c - L2 regularisation - penalty to loss function, and t - probability of threshold).
The test data (which makes up 20% of the total dataset provides the following metrics.

Confusion Matrix
tn ,fp , fn, tp
450,177, 37, 68

sensitivity:  0.6476
specificity:  0.7177
accuracy :  0.7077



## Limitations

Sensitivity = 0.65
The model correctly detects only ~65% of people who actually have heart disease.
→ This means 35% of actual cases are missed (false negatives), which is risky in healthcare because missing a diagnosis could delay treatment and worsen patient outcomes.

Specificity = 0.72
The model correctly identifies ~72% of healthy individuals.
→ About 28% of healthy people will get a false alarm (false positives), leading to unnecessary stress, tests, and costs.

Linear boundary
Complex relationships between risk factors are not taken into account. 


Correlations
Correlations between the variables has not been included in the model.
Logistic regression assumes predictors are not  correlated . features like blood pressure and BMI can be correlated.



## Trade-offs


. Sensitivity vs. Specificity
if sensitivity incresed (catch more heart disease cases), specificity lowered — more healthy people will be incorrectly classified as sick.

If increase specificity (fewer false alarms), you’ll lower sensitivity — more real cases will be missed.

In heart disease screening, the safer side is usually favoring higher sensitivity to avoid missing dangerous cases, but that means tolerating more false positives.

A slightly lower accuracy with higher sensitivity might save more lives than a model optimized purely for accuracy.

More complex models (e.g., gradient boosting) might improve predictive power but lose transparency — a key requirement in clinical decision-making.

4. Threshold Setting vs. Risk Tolerance
In this model the probability threshhold has been lowered as per the graph shown.
Lowering the threshold improves sensitivity but floods the system with false positives.
Raising the threshold reduces false positives but risks missing real patients.

