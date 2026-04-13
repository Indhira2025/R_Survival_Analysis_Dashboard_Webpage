

# MSK-CHORD Dashboard: Interactive Exploration of Metastasis and Genomics
#### Dashboard Access

The interactive Shiny dashboard can be deployed locally: \`\`\`R \# Run
locally shiny::runApp("MSK_Chord_dataset\MSK\_Dashboard")

or on a cloud service such as
[**https://indhirav.shinyapps.io/msk_dashboard/**](https://indhirav.shinyapps.io/msk_dashboard/){.uri}.\

Webpage : https://indhira2025.github.io/R_Survival_Analysis_Dashboard_Webpage/
## Abstract

Problem : Metastasis is the leading cause of cancer mortality in solid
tumors, with widely variable timing and risk among patients (Filipp et
al., 2017). High-dimensional genomic data, including somatic mutations
and copy number alterations, offer insights into tumor heterogeneity and
progression (Schramm et al., 2025; Zheng & Frost, 2020). Yet, accurately
predicting time to metastasis from such complex data remains challenging
(Mobadersany et al., 2018). \## Methodlogy This project investigates
genomic determinants of metastatic progression using the MSK-CHORD
(Nature 2024) cohort of 25,040 tumors profiled with MSK-IMPACT. The
primary objective is to model **time to metastasis** by integrating
high-dimensional somatic mutation and copy number alteration data with
survival analysis.

A two-stage framework combines Random Survival Forest–based phenotype
discovery with penalized Cox regression to quantify metastasis risk. In
parallel, an interactive Shiny dashboard enables dynamic exploration of
genomic alterations, copy number frequencies, metastatic site
distributions, fusion networks, tumor mutation burden, and survival
outcomes across cancer types.

Together, this work bridges machine learning, survival modeling, and
interactive visualization to support precision oncology and
translational research.

## Dataset

**MSK-CHORD**\
Targeted sequencing of 25,040 tumors from 24,950 patients and their
matched normals via MSK-IMPACT, along with clinical annotations, some
derived from natural language processing (NLP).\
[Dataset link on
cBioPortal](https://www.cbioportal.org/study/summary?id=msk_chord_2024)

**Outcome Variable:**\
Time to metastasis — interval from study entry (baseline) to first
documented metastatic event.

## Results
<img width="706" height="392" alt="image" src="https://github.com/user-attachments/assets/f19c7c0b-a32b-4463-b9cb-da7aac10637e" />
<img width="1345" height="637" alt="image" src="https://github.com/user-attachments/assets/664fc7e0-8653-4097-983f-0d7dd6e0a49d" />
<img width="1873" height="801" alt="image" src="https://github.com/user-attachments/assets/4ce8b8b3-f3e9-4b11-bbd6-86915f4c03b6" />
<img width="760" height="625" alt="image" src="https://github.com/user-attachments/assets/3d1a6c39-188e-4ad4-858f-6b0fe2821c5b" />



## Results
In this study, Random Survival Forest (RSF) proximity clustering identified five distinct genomic patient subtypes, and dimensional visualization confirmed clear separation and structure among these clusters. Kaplan–Meier analysis demonstrated significant differences in metastasis-free survival across the clusters (log-rank p < 0.0001), indicating that these genomic subtypes are not only genetically distinct but also clinically meaningful. Several clusters exhibited unique prognostic patterns, highlighting biologically relevant heterogeneity in metastatic risk. Cluster stability analysis using 100 bootstrap iterations confirmed that K=5 provided a highly stable solution (Mean Jaccard Index = 0.918), whereas higher cluster counts (e.g., K=6 or 10) resulted in a significant reduction in stability and the emergence of poorly defined subgroup
### Cluster Enrichment
To determine the biological composition of the identified subgroups, I analyzed the association between molecular clusters and primary cancer types using Pearson residuals. The analysis revealed highly significant tissue-specific enrichment ().

Cluster 2 and Cluster 5 demonstrated the strongest tissue specificity, being almost exclusively over-represented in Breast Cancer and Prostate Cancer, respectively. Cluster 3 was significantly enriched for Non-Small Cell Lung Cancer, while Colorectal Cancer cases were primarily distributed between Clusters 1 and 4. These results indicate that while some genomic features are shared across tissues, the clustering remains strongly influenced by the primary site of the tumor."
Connecting to Survival:
survival plot:
lowest-surviving group (Cluster 2) is the Breast Cancer enriched group.
highest-surviving group (Cluster 1) is enriched for Colorectal Cancer.
This adds a massive layer of clinical insight: it suggests that the "Breast Cancer" signature in dataset is significantly more aggressive than the "Colorectal" signature in Cluster 1.

## In Progress work:

- assess clusters by cancer type, 
- quantify cluster-specific metastasis risk using Cox models, 
- identify key genomic drivers via RSF variable importance,
- validate findings in independent cohorts, 
- investigate mechanisms underlying aggressive subtypes, and 
- integrate clinical data to enhance risk stratification and support precision oncology
  
## MSK-CHORD Dashboard

While the MSK-CHORD cohort is accessible through cBioPortal, this Shiny
dashboard provides enhanced exploratory analysis:

-   Dynamic cancer-type filtering with real-time updates across all
    plots.
-   Interactive CNA frequency visualization, showing precise hoverable
    amplification/deletion percentages.
-   Metastatic site summaries from clinical annotations.
-   Fusion chord diagram visualization, enabling intuitive exploration
    of recurrent gene fusion partners and network relationships (not
    available in the standard portal view).
-   Unified interface combining genomics, clinical variables, and
    survival analysis in one workflow.

Where cBioPortal provides high-level cohort summaries, this dashboard
emphasizes interactive sub-cohort analysis, network-level fusion
insight, scalability, and improved clinical interpretability, making it
well-suited for exploratory and translational research use cases.

#### Dashboard Access

The interactive Shiny dashboard can be deployed locally: \`\`\`R \# Run
locally shiny::runApp("MSK_Chord_dataset\MSK\_Dashboard")

or on a cloud service such as
[**https://indhirav.shinyapps.io/msk_dashboard/**](https://indhirav.shinyapps.io/msk_dashboard/){.uri}.\
