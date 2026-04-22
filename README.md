
# Webpage for this project 
 https://indhira2025.github.io/R_Survival_Analysis_Dashboard_Webpage/

# Genomic Clustering and Survival Analysis in Cancer: A Data-Driven Approach to Identifying Metastatic Risk Subtypes

## Abstract

Background: Metastasis remains the leading cause of cancer mortality, yet outcomes vary widely even within cancer type. Traditional subtyping often fails to capture non-linear interactions between multi-omic features and longitudinal survival. Here, we present a framework that uses a supervised survival model to learn a patient distance metric, then clusters on that representation to identify metastatic-risk subtypes.

**Outcome Variable:**\
Time to metastasis — interval from study entry (baseline) to first
documented metastatic event.
Methods: We fit a random survival forest (RSF) to predict metastasis-free survival using MSK-CHORD, a large clinico-genomic dataset with longitudinal outcomes across five cancer types (n = 25040). Predictors included gene-level mutations, tumor mutational burden, copy number alteration burden, and cancer type. We derived out-of-bag (OOB) proximities from the RSF as a survival-informed distance between patients, then clustered them with partitioning around medoids (PAM). The optimal cluster number (K=5) was selected via silhouette analysis and validated by bootstrapping (mean Jaccard index = 0.918). Cluster-level survival differences were assessed with Kaplan-Meier curves and quantified with Cox regression, and variable importance (VIMP) was used to identify predictive genomic features.

## Dataset

**MSK-CHORD**\
Targeted sequencing of 25,040 tumors from 24,950 patients and their
matched normals via MSK-IMPACT, along with clinical annotations, some
derived from natural language processing (NLP).\
[Dataset link on
cBioPortal](https://www.cbioportal.org/study/summary?id=msk_chord_2024)


## Results
<img width="706" height="392" alt="image" src="https://github.com/user-attachments/assets/f19c7c0b-a32b-4463-b9cb-da7aac10637e" />
<img width="1345" height="637" alt="image" src="https://github.com/user-attachments/assets/664fc7e0-8653-4097-983f-0d7dd6e0a49d" />
<img width="1873" height="801" alt="image" src="https://github.com/user-attachments/assets/4ce8b8b3-f3e9-4b11-bbd6-86915f4c03b6" />
<img width="760" height="625" alt="image" src="https://github.com/user-attachments/assets/3d1a6c39-188e-4ad4-858f-6b0fe2821c5b" />


Results: The RSF model achieved a C-index of 0.77. Clustering on RSF-derived distances resolved five subtypes with significantly different metastasis-free survival (p < 0.0001). Cluster membership was a strong independent predictor of outcome in Cox regression: Cluster 2, enriched for breast cancer, had the poorest prognosis (HR = 2.22 vs reference Cluster 1) compared to other clusters . VIMP analysis highlighted TP53, GATA3, and ERBB2 as key drivers, providing biological interpretability for the cancer subtypes.


Conclusion: Clustering on RSF-derived proximities reveals risk groups that are informed by metastasis onset. This pipeline offers a general framework for precision oncology and for identifying high-risk patients who may benefit from intensified therapy.


## MSK-CHORD Dashboard

While the MSK-CHORD cohort is accessible through cBioPortal, this Shiny dashboard provides enhanced exploratory analysis:

Where cBioPortal provides high-level cohort summaries, this dashboard
emphasizes interactive sub-cohort analysis, network-level fusion
insight, scalability, and improved clinical interpretability, making it
well-suited for exploratory and translational research use cases.

#### Dashboard Access

The interactive Shiny dashboard can be deployed locally: \`\`\`R \# Run
locally shiny::runApp("MSK_Chord_dataset\MSK\_Dashboard")

or on a cloud service such as
[**https://indhirav.shinyapps.io/msk_dashboard/**](https://indhirav.shinyapps.io/msk_dashboard/){.uri}.\


Authors: 
Indhira Vadivel, MS Health Data Science,  University of Michigan
Dr. Erin Craig , Associate Professor,  University of Michigan
