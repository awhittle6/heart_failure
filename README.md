# Motivation
Heart disease is the leading factor of death in the United Status. In this project we are intrested in analyzing how the following factors: <br>
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
<img src="https://i.imgur.com/IT3shfM.png" width="650" height="500"> <br><br>
Let's look at a heatmap of features to class using the seaborn library: <br><br>
<img src ="https://user-images.githubusercontent.com/50965707/123425484-35d39e00-d590-11eb-9544-3202c2956f9e.png" width="650" height="500"><br><br>

As we can see, most of the features have skewed PDFs and this we will pass normalization to pycaret to change the values of numeric columns in the dataset to a common scale, without distorting differences in the ranges of values. For this particular example we will scale our feautues using the MinMax scaler since multiple features have some intense outliers with a non-normal distribution.<br>
<img src = "https://miro.medium.com/max/780/1*kxS78PFEiDXq0slix6a5xA.png">

# Results and Conclusion
To compare all imported models I took utilization of [pycaret's compare model](https://pycaret.org/compare-models/) and sorted the models by their [f1 score](https://en.wikipedia.org/wiki/F-score).
<br>These are the results of each model's score:<br>
<img src = "https://user-images.githubusercontent.com/50965707/123449095-58be7c00-d5a9-11eb-8f2f-88dc49bf477c.png" width = "650" height="500"><br>
As indicated, the Random Forrest Classifier had the highest F1 score , and thus, has the highest average recall and accuracy score. For further optimization we tune it's hyperparameters giving us an overall F1 score of 0.7353.
<br> To visualize how each of the features impacts the prediction of heart failure, we will visualize a few examples with the LIME library.
<br><img src = "https://user-images.githubusercontent.com/50965707/123450816-1c8c1b00-d5ab-11eb-9091-58647001575e.png"><br><img src= "https://user-images.githubusercontent.com/50965707/123451225-86a4c000-d5ab-11eb-9791-f4abd369f040.png">
<br> Here we can see the magnitude and direction that each feature has on the probability of someone having heart failure. 
<br>
# References
<br>
Davide Chicco, Giuseppe Jurman: Machine learning can predict survival of patients with heart failure from serum creatinine and ejection fraction alone. BMC Medical Informatics and Decision Making 20, 16 (2020).<br><br>
Harris, C. R., Millman, K. J., van der Walt, S. J., Gommers, R., Virtanen, P., Cournapeau, D., … Oliphant, T. E. (2020). Array programming with NumPy. Nature, 585, 357–362. https://doi.org/10.1038/s41586-020-2649-2<br><br>
McKinney, W., & others. (2010). Data structures for statistical computing in python. In Proceedings of the 9th Python in Science Conference (Vol. 445, pp. 51–56).<br><br>
Pycaret<br><br>
Seaborn<br><br>
Lime<br><br>


