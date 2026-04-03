# Data Science Portfolio

Master of Information and Data Science (MIDS) · UC Berkeley School of Information · Graduated December 2025

**ML Engineer / Data Scientist** with hands-on experience in predictive modeling, EDA,
feature engineering, model evaluation, and ML deployment. This portfolio showcases projects
spanning healthcare AI, NLP, computer vision, and distributed ML.

---

## Skills & Tools

**Languages:** Python, SQL

**ML & AI:** Deep Learning · NLP · Predictive Modeling · Statistical Analysis · Classification · Clustering · Survival Modeling · Synthetic Data Generation

**Frameworks & Libraries:** PyTorch · TensorFlow · Scikit-learn · HuggingFace Transformers · FastAPI · NumPy · Pandas · Matplotlib · Seaborn · SciPy

**Platforms & Tools:** Databricks · Azure Kubernetes Service (AKS) · Docker · Redis · Grafana · Tableau

---

## Projects

| Project | Area | Key Tools | Date |
|--------|------|-----------|------|
| [IntegraMS](./integrams/) | Healthcare AI · Survival Modeling · Synthetic Data | Python, HMA Synthesizer, SMOTE, Weibull | Dec 2025 |
| [Airline Delay Prediction](./airline-delay-prediction/) | Classification · Distributed ML | XGBoost, Databricks, Scikit-learn | May 2025 |
| [ML API Deployment](./ml-api-deployment/) | MLOps · NLP | FastAPI, Docker, AKS, DistilBERT, Redis | Dec 2024 |
| [LEARN-ECE](./learn-ece/) | NLP · Event Causality | PyTorch, Transformers, MAVEN-ERE | Dec 2024 |
| [Social Media & Mental Health](./social-media-mental-health/) | Data Visualization · EDA | Tableau, Python | Aug 2024 |
| [ACME Gourmet Meals Takeoff](./acme-gourmet-meals/) | Graph Analytics · Urban Planning | Python, NetworkX, Harmonic Centrality | May 2024 |
| [Pawpularity](./pawpularity/) | Computer Vision · Regression | ResNet, PyTorch | May 2024 |
| [EV Pricing in Germany](./ev-pricing-germany/) | Regression · Statistical Modeling | Python, Statsmodels | Dec 2023 |
| [Wildlife Corridors 📄](./wildlife-corridors/Wildlife Corridors.pdf) | Research Design · Environmental Data Science | Mixed Methods, Linear Regression, ANOVA | Dec 2023 |

---

## IntegraMS
**Precision Monitoring of Multiple Sclerosis Powered by Multi-Modal Intelligence**
`UC Berkeley MIDS Capstone · Dec 2025` · [Capstone Showcase](https://www.ischool.berkeley.edu/projects/2025/integrams-multimodal-clinical-intelligence-platform-anchored-proteomics-predicting-ms)

- Led EDA on 500 MS patient records; identified 17 patients with sufficient longitudinal data for predictive modeling
- Built a synthetic data pipeline using HMA Synthesizer, expanding 17 patients to 1,020 synthetic records (89.8% quality score — a 60× expansion)
- Applied SMOTE for demographic balancing and Weibull survival modeling to forecast disability progression 3–6 years post-diagnosis
- Presented findings to clinical partners, faculty, and industry professionals at UC Berkeley MIDS Capstone Showcase

---

## Airline Delay Prediction
**A Machine Learning Approach to Minimizing Airline Losses & Improving Customer Satisfaction**
`UC Berkeley · May 2025`

- Performed EDA and imputation on a multi-year flight dataset
- Fine-tuned Logistic Regression and Random Forest classifiers with hyperparameter optimization
- Collaborated on Databricks for distributed processing; team's final XGBoost model achieved **85.3% F1-score**

---

## ML API Deployment
**Full End-to-End Machine Learning API**
`UC Berkeley · Dec 2024`

- Developed a REST API serving a DistilBERT sentiment analysis model using FastAPI, Docker, and Poetry
- Implemented Redis caching and Pydantic validation; deployed to Azure Kubernetes Service (AKS)
- Validated scalability via k6 load testing across 14,000+ requests; achieved **median response time of 113 ms**
- Monitored system performance with Grafana dashboards

---

## LEARN-ECE
**Leveraging Attention for Robust Neural Event Causality Extraction**
`UC Berkeley · Dec 2024`

- Developed event stream preprocessing pipeline for MAVEN-ERE dataset (2,913 documents, 570 event types)
- Trained and compared PAIN and TES models for next-event prediction; TES achieved log-likelihood of **-0.909** vs. PAIN's -1.0063

---

## Social Media & Mental Health
`UC Berkeley · Aug 2024`

- Analyzed demographic patterns across 1,248 social media users; identified correlations between age, gender, and emotional well-being
- Built interactive Tableau dashboards with demographic filtering; participated in usability testing for technical and non-technical audiences

---

## ACME Gourmet Meals Takeoff
**Data-Driven Expansion Strategy Using BART Transit Network Analysis**
`UC Berkeley · May 2024`

- Applied Harmonic Centrality to BART transit data to identify high-traffic network hubs
  as optimal candidates for meal pickup locations and faster local delivery
- Collaborated with a team using complementary graph algorithms (Louvain Modularity,
  PageRank, Minimum Spanning Tree, Geodesic Fencing) to deliver a comprehensive
  expansion strategy for Acme Gourmet Meals

---

## Pawpularity
**Predicting Engagement with a Pet's Profile Based on Profile Picture**
`UC Berkeley · May 2024`

- EDA on 9,912 pet images; removed 27 duplicate images with inconsistent labels
- Fine-tuned a ResNet model with hyperparameter experimentation; achieved test **RMSE of 20.39**
- All work aligned with the NeurIPS Responsible AI Checklist for data quality, transparency, and reproducibility

---

## EV Pricing in Germany
**Assessing the Impact of Energy Efficiency on Electric Vehicle Pricing**
`UC Berkeley · Dec 2023`

- Modeled energy efficiency vs. EV pricing across 308 vehicle models using multiple linear regression (**R² = 0.764**)
- Addressed multicollinearity, omitted variable bias, and reverse causality through hypothesis testing and assumption validation

---

## Wildlife Corridors 
**Is the U.S. Government Spending its $350 Million in Wildlife Corridor Funding Wisely?**
`UC Berkeley · Dec 2023` · [Full Report](./wildlife-corridors/Wildlife Corridors.pdf)

- Designed a mixed-methods research study to analyze how corridor length and width impact species crossing rates across 1,200+ corridors in the U.S., Canada, Brazil, and the Netherlands
- Proposed separate linear regression models for predator and prey species; incorporated ANOVA to examine how species variation impacts crossing rates
- Developed a data collection framework combining public databases, surveys, and camera trap monitoring across a 3-year study timeline
- Addressed real-world research challenges including confounding environmental variables, geographic bias, and regulatory compliance (IACUC, state video laws)

*Research design project — no code. Full report available via the link above.*

---

*Connect with me on [LinkedIn](https://www.linkedin.com/in/maria-jose-healey/)*
