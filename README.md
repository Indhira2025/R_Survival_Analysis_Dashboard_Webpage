

# MSK-CHORD Dashboard: Interactive Exploration of Metastasis and Genomics
#### Dashboard Access

The interactive Shiny dashboard can be deployed locally: \`\`\`R \# Run
locally shiny::runApp("MSK_Chord_dataset\MSK\_Dashboard")

or on a cloud service such as
[**https://indhirav.shinyapps.io/msk_dashboard/**](https://indhirav.shinyapps.io/msk_dashboard/){.uri}.\

Webpage : https://indhira2025.github.io/Survival_Analysis_Dashboard_Webpage/
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
<img width="713" height="444" alt="image" src="https://github.com/user-attachments/assets/8adfeba5-e0d6-4815-a588-ae7354018d86" />
<img width="762" height="443" alt="image" src="https://github.com/user-attachments/assets/7fc97e32-9b1d-46a6-bf8a-89d1dab58451" />

In this study, Random Survival Forest (RSF) proximity clustering identified six distinct genomic patient subtypes, and dimensional visualization confirmed clear separation and structure among these clusters. Kaplan–Meier analysis demonstrated significant differences in metastasis-free survival across the clusters (log-rank p < 0.0001), indicating that these genomic subtypes are not only genetically distinct but also clinically meaningful. Several clusters exhibited unique prognostic patterns, highlighting biologically relevant heterogeneity in metastatic risk. For example, the PIK3CA-enriched cluster (Cluster 4) showed favorable metastasis-free survival, consistent with observations in breast and endometrial cancers8,10, while the TP53-dominant cluster (Cluster 5) reflected a genomic instability phenotype commonly observed across multiple tumor types10. Additionally, enrichment of APC and KRAS mutations in one cluster corresponds to canonical WNT and MAPK pathway activation reported in colorectal tumorigenesis 9-10. Interestingly, a genomically quiet yet clinically aggressive subtype (Cluster 2) was identified, a pattern previously described in prostate and pancreatic cancers11, suggesting that non-mutational mechanisms may drive metastatic progression. Collectively, these results underscore the potential of machine learning–based genomic clustering to stratify patients by risk and inform personalized prognostic assessment. 

## Way forward:
Future work should 
- assess clusters by cancer type, 
- quantify cluster-specific metastasis risk using Cox models, 
- identify key genomic drivers via RSF variable importance,
- validate findings in independent cohorts, 
- investigate mechanisms underlying aggressive subtypes, and 
- integrate clinical data to enhance risk stratification and support precision oncology
- 
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
