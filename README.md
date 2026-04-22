
# Webpage for this project 
 https://indhira2025.github.io/R_Survival_Analysis_Dashboard_Webpage/

# Genomic Clustering and Survival Analysis in Cancer: A Data-Driven Approach to Identifying Metastatic Risk Subtypes

## Abstract

Background: Metastasis remains the leading cause of cancer mortality, yet outcomes vary widely even within cancer type. Traditional subtyping often fails to capture non-linear interactions between multi-omic features and longitudinal survival. Here, we present a framework that uses a supervised survival model to learn a patient distance metric, then clusters on that representation to identify metastatic-risk subtypes.

**Outcome Variable:**\
Time to metastasis — interval from study entry (baseline) to firstdocumented metastatic event.
## Methods
We fit a random survival forest (RSF) to predict metastasis-free survival using MSK-CHORD, a large clinico-genomic dataset with longitudinal outcomes across five cancer types (n = 25040). Predictors included gene-level mutations, tumor mutational burden, copy number alteration burden, and cancer type. We derived out-of-bag (OOB) proximities from the RSF as a survival-informed distance between patients, then clustered them with partitioning around medoids (PAM). The optimal cluster number (K=5) was selected via silhouette analysis and validated by bootstrapping (mean Jaccard index = 0.918). Cluster-level survival differences were assessed with Kaplan-Meier curves and quantified with Cox regression, and variable importance (VIMP) was used to identify predictive genomic features.

## Dataset

**MSK-CHORD**\
Targeted sequencing of 25,040 tumors from 24,950 patients and their
matched normals via MSK-IMPACT, along with clinical annotations, some
derived from natural language processing (NLP).\
[Dataset link on
cBioPortal](https://www.cbioportal.org/study/summary?id=msk_chord_2024)


## Results
<img width="1556" height="832" alt="image" src="https://github.com/user-attachments/assets/63c8ec02-e6ed-41db-b2a9-2c69f6a072f7" />
<img width="656" height="652" alt="image" src="https://github.com/user-attachments/assets/97c04167-0c8e-41b1-bc1f-5be48fe551ab" />
<img width="647" height="649" alt="image" src="https://github.com/user-attachments/assets/ac9417a1-46bf-4fc5-b2f9-1fe257c454f7" />
<img width="906" height="651" alt="image" src="https://github.com/user-attachments/assets/750cc05c-5d47-4894-92ae-e0511e67c6be" />



RSF Model Evaluation : C-index: 0.77;  BrierScore:  0.152(Vs 0.218) \
Identified 5  Clusters (K=5)\
● Distinct genomic profiles\
● Silhouette-based validation \
● High stability (Mean Jaccard Index = 0.918) and  interpretability\
Clustering on RSF-derived distances resolved five subtypes with significantly different metastasis-free survival (p < 0.0001). Cluster membership was a strong independent predictor of outcome in Cox regression: Cluster 2, enriched for breast cancer, had the poorest prognosis (HR = 2.22 vs reference Cluster 1) compared to other clusters . VIMP analysis highlighted TP53, GATA3, and ERBB2 as key drivers, providing biological interpretability for the cancer subtypes.\
Two clusters had immediate clinical implications:\
-Cluster 2 (Rapid-Progressors): An "ultra-high-risk" phenotype with a 75% risk of spread within 500 days, driven by TP53, ERBB2, and high CNA burden. These findings support aggressive, early intervention.\
-Cluster 4 (The Stable Group): Patients with excellent long-term survival despite "aggressive" cancer types. This reveals a clear opportunity to de-escalate treatment and avoid unnecessary toxicity.

But an interesting and important question was : "How does Cluster 1 — the group with mutations in practically every gene have the best metastasis free survival probability?"

Logic suggests that more mutations = "stronger" cancer. However, the data (and literature from Goodman et al.) tells a different story. This "hyper-mutated" state often results in two
phenomena:\
Immune Visibility: High mutation counts make the tumor"louder," creating more neoantigens that allow the immune systemto recognize and attack the cancer more effectively.\
GenomicInstability: Sometimes, a cancer becomes so unstable that it loses its"fitness." The cells are so dysfunctional that they struggle to survive the complex journey required to spread to other organs.

This finding highlights why we cannot rely on a single metric. Context is everything.
 
## The Impact
Two patients with the same diagnosis can have completely different genomic stories. This approach helps us catch high-risk cases earlier while sparing stable patients from overtreatment.


## Conclusion 
Clustering on RSF-derived proximities reveals risk groups that are informed by metastasis onset. This pipeline offers a general framework for precision oncology and for identifying high-risk patients who may benefit from intensified therapy.


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
