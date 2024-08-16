# ACME_Capstone-Project

The project is focused on building upon the completed exploratory data analysis (EDA) of road traffic accidents in Great Britain for the year 2020. The data source, data dictionary, data cleaning, preprocessing, and EDA steps can be found at the repository: https://github.com/ekeng3/ACME-software-Lab

This repository contains a Jupyter notebook focused on analyzing road traffic accidents, with the following main objectives:

1. **Use Apriori algorithm to uncover relationships between variables influencing accidents**
2. **Identify accidents in some regions**
3. **Use outlier detection methods to identify unusual entries in the dataset**
4. **Develop a classification model to accurately predict fatal injuries sustained in road traffic accidents, to inform and improve road safety measures**

The key components of the notebook are:

1. **Data Preprocessing**:
   - The notebook loads the LSOA (Lower-layer Super Output Area) region data and merges it with the main accident data.
   - It handles missing values and creates a new column `general_region` to extract the general region name from the LSOA code.

2. **Apriori Algorithm**:
   - The notebook applies the Apriori algorithm to the preprocessed data to identify frequent item sets and association rules.
   - It analyzes the generated rules, focusing on those with high lift, which indicate a strong association between the antecedents and consequents.

3. **Spatial Analysis**:
   - The notebook filters the data for specific regions (Kingston upon Hull, Darlington, and East Riding of Yorkshire).
   - It applies K-Means clustering to the latitude and longitude of the accidents and visualizes the clusters on a map.

4. **Predictive Modeling**:
   - The notebook includes the implementation of a classification model to predict accident severity. However, the models struggle with the minority classes suggesting that the models are biased towards the majority class. Further work will be done to address this issue.

The main libraries used in the notebook are:

- `pandas`: For data manipulation and preprocessing
- `folium`: For creating interactive maps
- `mlxtend`: For applying the Apriori algorithm
- `sklearn`: For the K-Means clustering

The notebook provides a detailed analysis of the association rules generated by the Apriori algorithm, interpreting the significance of the rules in terms of support, confidence, and lift. Some key findings include:

1. **Rule 54**: There is a strong relationship between certain weather conditions (raining without high winds) and wet/damp road surface conditions, with a high confidence and lift.
2. **Rule 99**: A speed limit of 60 is strongly associated with rural areas, with high confidence and lift.
3. **Rule 100**: If the junction detail is of type 0 (not at or within 20 meters of a junction), the junction control is almost certainly of type 1 (authorized person).
4. **Rule 108**: There is a moderate association between junction control type 4 (give way or uncontrolled) and junction detail type 3 (T or staggered junction).

The notebook also includes a spatial analysis, where it clusters the accidents in the selected regions and visualizes the clusters on a map.

Conclusion

This analysis highlights key insights into road traffic accidents in Great Britain for 2020. By leveraging EDA, clustering, association rules, and predictive modeling, we’ve uncovered patterns that can inform safety measures and policy decisions. The combination of geographical and statistical analysis provides a comprehensive view of accident severity and its influencing factors.

Further work will focus on refining the predictive model and applying the insights gained to design interventions that reduce accident severity and frequency. Specifically, Considering the evaluation of the models, we notice that the models struggle significantly with classes 1 and 2, as reflected in their poor precision, recall, and F1 scores for these classes. This suggests that the models are heavily biased towards class 3, which has the majority of the instances.
Since the models are biased towards the majority class (class 3) and perform poorly in minority classes (classes 1 and 2), as the next step I would particularly focus  on handling the class imbalance. To achieve this, I will be using the Synthetic Minority Over-sampling Technique (SMOTE) to generate synthetic samples or simple random oversampling.
