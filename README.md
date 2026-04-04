

# Project Background

Alzheimer’s disease is the most common cause of dementia. While no cure currently exists for later stages, evidence suggests that modifying certain lifestyle and health-related risk factors can help reduce or delay the onset of dementia in some individuals. Early detection of Alzheimer’s Disease (AD) is crucial for timely intervention, as it may help preserve quality of life. However, traditional diagnostic procedures rely heavily on high-cost neuroimaging biomarkers such as those from Magnetic Resonance Imaging (MRI), limiting scalability in routine care. While AI-based techniques can flag individuals at risk for AD through Electronic Health Records (EHR), researchers encounter an information gap due to limited access to neuroimaging data. 

Diagnosing Alzheimer’s disease early is challenging because early brain changes are subtle and may not be obvious clinically. Machine learning (ML) models can support this process by identifying patterns in data that indicate risk before symptoms become significant.

### Scope of This Study

This analysis aims to investigate whether cognitive tests and demographic proxies can achieve diagnostic fidelity comparable to the MRI-based model in detecting high-risk patients before clinical manifestations appear. It also includes exploratory data analysis (EDA), visualisations, and interpretation of factors associated with dementia status.

### Method

This study used data from the Open Access Series of Imaging Studies (OASIS) to examine the diagnostic performance of multiple machine learning algorithms for dementia detection under two predictive settings: a full approach that included demographic, cognitive, and MRI-derived variables, and a cost-effective approach that excluded all neuroimaging measures. Both cross-sectional and longitudinal cohorts were analyzed, with binary classifiers trained to predict dementia status using an 80/20 train–test split. Five classifiers were compared: logistic regression, decision trees (DT), random forests (RF), support vector machines (SVM), and extreme gradient boosting (XGBoost). Model performance was evaluated using accuracy, precision, recall, F1-score, and receiver operating characteristic curve (ROC) analysis. Comparative analyses focused on the impact of removing MRI biomarkers and demographic differences between demented and non-demented groups. 

The original study is available at [here](https://www.frontiersin.org/journals/public-health/articles/10.3389/fpubh.2022.853294/full)

The full implementation and analysis workflow is available [here](../Rmd-file/MLAD.pdf).