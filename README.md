# H1N1-Vaccines
Kendall McNeil, October 2023
![image](https://github.com/kmcneil901/H1N1-Vaccines/assets/139075900/a3915cb7-ffa5-4cab-af72-502a1ef23ac4)

# 1. Introduction
1. DESCRIPTION: Beginning in the spring of 2009, the H1N1 influenza virus, commonly referred to as "swine flu," swept across the globe. In fact, at my own high school, we had the first case of swine flu in the entire state of Texas and were shut down for over a month. It is estimated that in the first year, swine flu was responsible for 363,000 deaths worldwide.
2. OBJECTIVE: The objective of this project is to identify individuals who will not receive a swine flu vaccine. Predicting individuals who will not receive the vaccine will help to inform the CDC’s marketing strategies. To do this, I have analyzed over 26,000 data points collected via phone call through the National 2009 H1N1 Flu Survey. This survey was administered by the National Center for Health Statistics in collaboration with the CDC.
3. DEFINING KEY TERMS: Throughout this notebook, when the term “unvaccinated” is used, it refers specifically to the annual swine flu vaccinestill recommended today by the CDC.
4. METHODOLOGY: Logistic Regression
5. TARGET: h1n1_vaccine
  - 1 represents no vaccine
  - 0 represents vaccine
6. PERFORMANCE METRICS: Performance will be evaluated according to the area under the receiver operating characteristic curve (ROC) along with the accuracy, recall, precision, and f1 scores. A higher value indicates stronger performance.
7. OUTLINE:
- This GitHub Repository contains the main H1N1 Vaccine ipynb, which includes all the model creation and data exploration.
- This GitHub Repository also contains a data folder, which includes all the relevant data files.
- There is also a Tableau Dashboard that displays visualizations of the prediction data: https://public.tableau.com/app/profile/kendall.mcneil/vizzes
- Lastly, there is a PDF of the final non-technical presentation: 

# 2. Description of the Data:
*From the DrivenData Website: https://www.drivendata.org/competitions/66/flu-shot-learning/page/211/
*36 Columns Total
*For all binary variables: 0 = No; 1 = Yes.

1. respondent_id: unique and random identifier
2. h1n1_concern - Level of concern about the H1N1 flu. 0 = Not at all concerned; 1 = Not very concerned; 2 = Somewhat concerned; 3 = Very concerned
3. h1n1_knowledge - Level of knowledge about H1N1 flu. 0 = No knowledge; 1 = A little knowledge; 2 = A lot of knowledge
4. behavioral_antiviral_meds - Has taken antiviral medications. (binary)
5. behavioral_avoidance - Has avoided close contact with others with flu-like symptoms. (binary)
6. behavioral_face_mask - Has bought a face mask. (binary)
7. behavioral_wash_hands - Has frequently washed hands or used hand sanitizer. (binary)
8. behavioral_large_gatherings - Has reduced time at large gatherings. (binary)
9. behavioral_outside_home - Has reduced contact with people outside of own household. (binary)
10. behavioral_touch_face - Has avoided touching eyes, nose, or mouth. (binary)
11. doctor_recc_h1n1 - H1N1 flu vaccine was recommended by doctor. (binary)
12. doctor_recc_seasonal - Seasonal flu vaccine was recommended by doctor. (binary)
13. chronic_med_condition - Has any of the following chronic medical conditions: asthma or an other lung condition, diabetes, a heart condition, a kidney condition, sickle cell anemia or other anemia, a neurological or neuromuscular condition, a liver condition, or a weakened immune system caused by a chronic illness or by medicines taken for a chronic illness. (binary)
14. child_under_6_months - Has regular close contact with a child under the age of six months. (binary)
15. health_worker - Is a healthcare worker. (binary)
16. health_insurance - Has health insurance. (binary)
17. opinion_h1n1_vacc_effective - Respondent's opinion about H1N1 vaccine effectiveness. 1 = Not at all effective; 2 = Not very effective; 3 = Don't know; 4 = Somewhat effective; 5 = Very effective.
18. opinion_h1n1_risk - Respondent's opinion about risk of getting sick with H1N1 flu without vaccine. 1 = Very Low; 2 = Somewhat low; 3 = Don't know; 4 = Somewhat high; 5 = Very high.
19. opinion_h1n1_sick_from_vacc - Respondent's worry of getting sick from taking H1N1 vaccine. 1 = Not at all worried; 2 = Not very worried; 3 = Don't know; 4 = Somewhat worried; 5 = Very worried.
20. opinion_seas_vacc_effective - Respondent's opinion about seasonal flu vaccine effectiveness. 1 = Not at all effective; 2 = Not very effective; 3 = Don't know; 4 = Somewhat effective; 5 = Very effective.
21. opinion_seas_risk - Respondent's opinion about risk of getting sick with seasonal flu without vaccine. 1 = Very Low; 2 = Somewhat low; 3 = Don't know; 4 = Somewhat high; 5 = Very high.
22. opinion_seas_sick_from_vacc - Respondent's worry of getting sick from taking seasonal flu vaccine. 1 = Not at all worried; 2 = Not very worried; 3 = Don't know; 4 = Somewhat worried; 5 = Very worried.
23. age_group - Age group of respondent.
24. education - Self-reported education level.
25. race - Race of respondent.
26. sex - Sex of respondent.
27. income_poverty - Household annual income of respondent with respect to 2008 Census poverty thresholds.
28. marital_status - Marital status of respondent.
29. rent_or_own - Housing situation of respondent.
30. employment_status - Employment status of respondent.
31. hhs_geo_region - Respondent's residence using a 10-region geographic classification defined by the U.S. Dept. of Health and Human Services. Values are represented as short random character strings.
32. census_msa - Respondent's residence within metropolitan statistical areas (MSA) as defined by the U.S. Census.
33. household_adults - Number of other adults in household, top-coded to 3.
34. household_children - Number of children in household, top-coded to 3.
35. employment_industry - Type of industry respondent is employed in. Values are represented as short random character strings.
36. employment_occupation - Type of occupation of respondent. Values are represented as short random character strings.

# 3. Model Performance

The final model was a logistic regression model with gridsearched parameters. 

1. Accuracy: 83.99%.
2. Recall: 95.11%.
3. Precision: 86.04%.
4. F1-Score: 90.35%.
5. ROC AUC Score: 68.905%.
   
![image](https://github.com/kmcneil901/H1N1-Vaccines/assets/139075900/d15fb01a-027f-4f38-9de7-c77d674df2bc)
![image](https://github.com/kmcneil901/H1N1-Vaccines/assets/139075900/ae41d4cd-e0d7-438a-8164-0e65ccdb71e2)

MODEL INTERPRETATION: While the final model’s overall accuracy score was 84%, the recall rate was 95%. This tells us that of individuals who will not receive the vaccine, the model will accurately predict 95% of them. This is good news for us because, for this business question, we are mostly concerned with identifying unvaccinated individuals. It won’t hurt to market to an individual who will indeed get the vaccine. We would rather err on the side of identifying a larger volume of unvaccinated individuals. Let’s take a sneak peak at what this machine learning model tells us.

# 4. Model Predictions
Using the model, we generated predictions. The predictions revealed the following trends in the data.
Note that these visualizations are from the Tableau Dashboard linked above. 

Income:

<img width="285" alt="image" src="https://github.com/kmcneil901/H1N1-Vaccines/assets/139075900/00fd7cea-3e8d-4143-8cb8-038ce3566cee">

Employment Status:

<img width="273" alt="image" src="https://github.com/kmcneil901/H1N1-Vaccines/assets/139075900/f850472d-4e26-41b8-bf99-6ed11165c1d3">

Education: 

<img width="419" alt="image" src="https://github.com/kmcneil901/H1N1-Vaccines/assets/139075900/1a335dc9-63bd-4355-9648-c702b71a496a">

Sex & Age: 

<img width="449" alt="image" src="https://github.com/kmcneil901/H1N1-Vaccines/assets/139075900/c4a4e9ef-926a-4da3-966d-4217bb39c6b3">

Doctor Recommendation: 

<img width="323" alt="image" src="https://github.com/kmcneil901/H1N1-Vaccines/assets/139075900/21aa5d4e-3a09-4f7e-8ca1-a61d443f6ff5">

Race:
<img width="790" alt="image" src="https://github.com/kmcneil901/H1N1-Vaccines/assets/139075900/9fbdf7cc-7c0e-4dbd-8354-5957c0e6c912">

Rent/Own: 
<img width="771" alt="image" src="https://github.com/kmcneil901/H1N1-Vaccines/assets/139075900/fb9564ac-6128-4b6c-a8ee-e0ab87e37764">

Presence of a Child:
<img width="776" alt="image" src="https://github.com/kmcneil901/H1N1-Vaccines/assets/139075900/ee31711c-42e5-4303-ba4f-3ad85a12a617">



