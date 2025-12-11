

# Project Background

Alzheimer’s disease is the most common cause of dementia. While no cure currently exists for later stages, evidence suggests that modifying certain lifestyle and health-related risk factors can help reduce or delay the onset of dementia in some individuals. Therefore, early intervention is valuable in primary healthcare. An early-stage prediction model can help professionals recognis individuals at risk, allowing them to access appropriate treatments, make lifestyle changes, and slow disease progression through timely intervention.

Diagnosing Alzheimer’s disease early is challenging because early brain changes are subtle and may not be obvious clinically. Machine learning (ML) models can support this process by identifying patterns in data that indicate risk before symptoms become significant.

### Scope of This Study

This study focuses on the first two stages of the Well Pathway for Dementia by developing and evaluating five machine learning classification models to determine which achieves the highest accuracy in predicting dementia status (demented vs. nondemented) based on clinical and demographic metrics. It also includes exploratory data analysis (EDA), visualisations, and interpretation of factors associated with dementia status.

The original study is available at [here](https://www.frontiersin.org/journals/public-health/articles/10.3389/fpubh.2022.853294/full).


# Dataset Overview & Structure

Cross-sectional MRI database contains 436 records, and its structure is shown below. These features represent known biomarkers associated with Alzheimer’s pathology.

<div align="center">
  <img src="./Figure/datastructure.jpg" width="500">
</div>


Before beginning the analysis, several preliminary checks were performed to ensure data accuracy, including handling missing values, reviewing attribute definitions, and generating descriptive statistical summaries. 

A detailed summary of these diagnostics can be found [here](./Report-pdf/Dataset.pdf).

The dataset used for this project is the Cross-sectional MRI Data in Nondemented and Demented Older Adults, available at [here](https://www.kaggle.com/datasets/jboysen/mri-and-alzheimers).


# Executive Summary

### Model Performance Overview: 

* The models' performance was evaluated using Accuracy, Precision, and Recall, as shown in the table below.

<div align="center">
  <img src="./Figure/modelresult.jpg" width="500">
</div>


* The **XGBoost model** is the strongest and most clinically reliable candidate for early-stage Alzheimer's disease prediction. 

This model achieved a competitive overall Accuracy of $89.36\%$, a peak score shared with the Decision Tree (DT) model. The decisive advantage is XGBoost's superior Recall of $0.88$, which is vital because it minimizes False Negatives (the critical error of missing a diagnosis). While DT maintains slightly higher Precision ($0.87$), XGBoost delivers a strong and reliable Precision of $0.82$. This exceptional Recall score makes minimizing False Negatives the deciding factor for safety and reliability in early-stage Alzheimer's disease detection, ensuring that patients and their caregivers can proceed immediately with crucial early intervention or treatment planning.

Detailed findings and insights (Visualizations & Confusion Matrices) can be found [here](./Report-pdf/ModelPerformance.pdf).


# Insights Deep Dive

### Exploratory Data Analysis Summary:

* Females are more represented in the dataset, with similar proportions across dementia status.
  
* Nondemented patients show higher whole-brain volume (nWBV), stronger MMSE performance, and greater education levels (Educ) relative to demented patients.
  
* A noticeably larger proportion of individuals with dementia fall within the 75–80 age range compared to the nondemented group.

A full set of detailed visualizations and findings for dementia-related variables is available at [here](./Report-pdf/EDA.pdf).


### Modeling Pipeline Summary:

* **Preprocessing:** Non-predictive identifiers (ID, Hand, Visits, Delay) and the outcome-defining variable CDR were removed to avoid information leakage and overfitting.

* **Imputation:** Rows with missing CDR were removed, which also eliminated missing Educ and MMSE, and the remaining 19 SES values were imputed using KNN ($k=5$).

* **Train–Test Split:** An 80/20 train–test split was used, and all classification models were trained with 10-fold cross-validation. 
  
* **Modeling:** Five classification models were evaluated: Decision Tree (DT), Random Forest (RF), Support Vector Machine (SVM), XGBoost, and Logistic Regression (baseline).

* **Feature Importance:** The top three predictors identified by both Random Forest and XGBoost models are MMSE, nWBV, and Age.

A complete description of the methods and model implementation, including R code, is provided [here](./Report-pdf/Method.pdf).


# Future Improvements:

The EDA section can be further strengthened by incorporating findings from additional studies on Alzheimer’s disease, including research on pathology, risk factors, and the relationship between aging and cognitive decline. As future work, integrating evidence from the scientific literature would allow for more rigorous interpretation of exploratory patterns and more evidence-based conclusions.

MMSE, nWBV, and Age are all clinically relevant attributes for detecting Alzheimer’s disease. Additional studies could expand on these findings by identifying more features that could further improve early detection and intervention strategies.

This study used the same dataset as the original paper but applied a slightly different approach to handling missing values, which may explain minor differences in model performance. XGBoost still demonstrated strong and stable predictive behavior across evaluation metrics, indicating that it remains a promising model for further refinement. Further tuning of the model may improve Recall and Accuracy, as well as contributing to more reliable early detection of dementia.

### Limitations

A limitation of this study is that dementia status was defined solely from CDR rather than a full clinical diagnostic protocol, and observations with missing CDR values were excluded because a valid outcome label could not be assigned. In addition, the dataset is relatively small, so the resulting model estimates and accuracy metrics should be interpreted with caution. Future studies could benefit from larger datasets with more comprehensive diagnostic information to enhance model reliability.

# References

Full references are listed at the end of the Exploratory Data Analysis PDF.

