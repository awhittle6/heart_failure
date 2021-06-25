# Motivation
Heart complications is the leading factor of death in the United Status. In this project we are intrested in analyzing how the following factors: <br>
1. age: Age <br />
1. anaemia: Decrease of red blood cells or hemoglobin (boolean) <br />
1. creatinine_phosphokinase: Level of the CPK enzyme in the blood (mcg/L) <br />
1. diabetes: If the patient has diabetes (boolean) <br />
1. ejection_fraction: Percentage of blood leaving the heart at each contraction (percentage) <br />
1. high_blood_pressure: If the patient has hypertension (boolean) <br />
1. platelets: Platelets in the blood (kiloplatelets/mL) <br />
1. serum_creatinine: Level of serum creatinine in the blood (mg/dL) <br />
1. serum_sodium: Level of serum sodium in the blood (mEq/L) <br />
1. sex: Woman or man (binary) <br />
1. smoking: If the patient smokes or not (boolean)<br />
1. time: Follow-up period (days) <br />
1. DEATH_EVENT: If the patient deceased <br />


# Data Preprocessing 
The data set obtained for this analysis was provided on kaggle and can be viewed [here](https://www.kaggle.com/andrewmvd/heart-failure-clinical-data).
Before establishing any correlations and while this data we will first look at the PDFs (Probability Density Function) of each feature. <br>
<img src="https://i.imgur.com/IT3shfM.png" width="500" height="550"> <br>
Heatmap of features to class: <br>
<img src ="https://user-images.githubusercontent.com/50965707/123425484-35d39e00-d590-11eb-9544-3202c2956f9e.png" width="750" height="500"><br>

As we can see, most of the features have skewed PDFs and this we will pass normalization to pycaret to change the values of numeric columns in the dataset to a common scale, without distorting differences in the ranges of values.
