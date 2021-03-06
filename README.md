# What's Age Got To Do With It?
By: Muriel Kosaka

## Introduction

Autism Spectrum Disorder (ASD) is a neurodevelopmental disorder that affects communication and behavior. Early detection of ASD is beneficial for both the parent and the child. In this final project, I examined a dataset provided on [Kaggle](https://www.kaggle.com/fabdelja/autism-screening-for-toddlers) that included individual characteristics and features to determine ASD traits. These features included the QChat-10 which are 10 questions about the child’s behavior, and then individual characteristics such as sex, ethnicity, whether or not the child was born with Jaundice, if an immediate family member has ASD, and who completed the test on behalf of the child. Scores 4 and above on the QChat-10 indicated that the child had traits of ASD. Using the features provided, I aimed to create a linear regression model to predict age.
If we can predict the age of toddlers with traits of ASD, this can help parents look out for the early signs and have their child tested and receive treatment earlier. See **What's Age Got To Do With It?.pdf** for Google Slides Presentation.

## Process

1) See **1. Regression.ipynb**: Using the dataset, Toddler Autism dataset July 2018.csv from Kaggle, I cleaned the data, conducted necessary EDA and created three multi-linear regression models using feature selection methods: 

    - Using questions A1-A10 from QChat-10 to predict age
        ![alt text](https://github.com/mkosaka1/Module_2_Project/blob/master/Photos/project_regression_png_files/A1_A10_FinalModel.png)
    - Using interactions of questions A1-A10 from QChat-10 to 
        predict age
        ![alt text](https://github.com/mkosaka1/Module_2_Project/blob/master/Photos/project_regression_png_files/Interaction_FinalModel.png)
    - Using individual characteristics to predict age
        ![alt text](https://github.com/mkosaka1/Module_2_Project/blob/master/Photos/project_regression_png_files/Individual_Characteristics_FinalModel.png)
        
2) See **2. Hypothesis_test.ipynb**: Then based off my results from the linear regression models, I conducted three hypothesis tests:

    - Independent samples t-test between Sex on QChat-10 
        scores: results were not significant. 
        ![alt text](https://github.com/mkosaka1/Module_2_Project/blob/master/Photos/project_hypothesis_tests_png_files/sex_qchat_score.png)
    - Independent samples t-test between toddlers who were/were not born with Jaundice on QChat-10 scores: 
        results were not significant.
        ![alt text](https://github.com/mkosaka1/Module_2_Project/blob/master/Photos/project_hypothesis_tests_png_files/Jaundice_Age.png)
    - One way ANOVA between ethnicities on QChat-10 scores: 
        results were significant between White European and 
        Asian.
        ![alt text](https://github.com/mkosaka1/Module_2_Project/blob/master/Photos/project_hypothesis_tests_png_files/one_way_anova.png)


## Libraries

### Data Collection:

- Pandas

### Data Cleaning and Visualization:

- Matplotlib
- Seaborn
- Pandas
- SciPy
- Sklearn
- NumPy
- Statsmodels

## Findings and Limitations

When looking to predict age it is best to use the individual characteristics, although it will over-estimate by 7.17 months. QChat-10 scores best predict age, as QChat-10 scores increase by 1, age goes down by 1.30 months. There is no significant difference in average qchat-10 scores between those who were/were not born with jaundice ( *p*  = 0.72) and between sex ( *p* * = 0.09). White european and asian toddlers had the most significant difference in average qchat-10 scores ( *p*  < 0.05). 

Limitations of our model include who was filling out the survey for the toddlers, there may have been some bias in the responses, e.g. social desirability bias. Another limitation are the responses used for the survey, using a likert scale rather than yes/no responses can better capture the child's behavior.

Future models should include data such as extremely preterm babies, presence of other disorders, and parental information such as age and the presence of obesity and/or diabetes.

