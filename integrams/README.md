# IntegraMS — Modeling

**Precision Monitoring of Multiple Sclerosis Powered by Multi-Modal Intelligence**
`UC Berkeley MIDS Capstone · Dec 2025` · [Capstone Showcase](https://www.ischool.berkeley.edu/projects/2025/integrams-multimodal-clinical-intelligence-platform-anchored-proteomics-predicting-ms)

> This folder contains the two modeling notebooks I developed as part of the IntegraMS 
> capstone project. My primary contributions were the synthetic data 
> generation pipeline and DSS trajectory extrapolation.

---

## Contents

| File | Description |
|----------|-------------|
| `synthetic-data-generation.ipynb` | HMA Synthesizer pipeline to expand 17 real MS patient records into 1,020 synthetic records |
| `extrapolations.ipynb` | Weibull survival model to extrapolate DSS disability scores from Year 3 to Year 6 |
| `integrams-presentation.pdf` | Capstone showcase presentation slides |

---

## Synthetic Data Generation Pipeline

To enable robust model training while preserving patient privacy and biological patterns,
I built a synthetic data generation pipeline using the SDV (Synthetic Data Vault) HMA
(Hierarchical Modeling Algorithm) Synthesizer to expand a seed cohort of 17 real MS patients.

### Why HMA Synthesizer?

I selected the HMA Synthesizer for its specific advantages in medical data:

- **Hierarchical Structure:** Maintains the complex `Patient` → `Visit` relationships
- **Multi-Table Support:** Preserves dependencies across multi-modal data tables
- **Constraint Enforcement:** Ensures generated data remains clinically valid
- **Privacy:** Generates entirely new patient records rather than anonymizing existing ones

### Data Flow & Quality Control

I designed the pipeline to transform a small seed dataset into a large-scale, validated 
training corpus.

**1. Generation Phase**
- Input: 17 real patient profiles (seed data)
- Process: The HMA model learned distributions and correlations across patient-level and visit-level tables
- Output: 1,020 synthetic records generated

**2. Validation Phase**
- Quality Score: 89.8% (assessed via SDV evaluation metrics)
- Filtering: Low-quality records removed (91% pass rate)
- Final Count: 930 high-quality records

**Post-Processing — Ensuring Biological Plausibility and Data Integrity**

I applied a multi-layer post-processing pipeline to ensure the synthetic data was 
clinically valid and structurally consistent:

- **Temporal Constraints:** Enforced chronological logic across all time-based fields 
  (e.g., diagnosis year ≥ birth year, disease onset before diagnosis, chronological 
  visit ordering, years post-diagnosis fixed at 3)
- **Multi-Table Structure:** Validated 2 visits × 200 peptides per patient; resampled 
  binding signals from real data distributions; ensured patient-level attributes were 
  consistent across all 400 rows per patient
- **Clinical Constraints:** Enforced race encoding consistency, DSS milestone logic, 
  and preservation of disease timeline features across timepoints
- **Cross-Table Validation:** Verified patient demographics matched across all tables 
  and temporal logic held for all 1,020 synthetic patients — achieving **100% 
  consistency post-processing**

**3. Dataset Split**

| Set | Count | Percentage |
|-----|-------|------------|
| Training | 744 | 80% |
| Validation | 186 | 20% |

**Key Impact:** This pipeline enabled robust model training that would have been statistically 
impossible with the original n=17 cohort, while successfully preserving biological signals 
and clinical trajectories.

---

## DSS Trajectory Extrapolation

I developed this module to extrapolate Disability Status Scale (DSS) scores from Year 3 
to Year 6 post-diagnosis. Understanding this progression is vital for identifying 
intervention windows before severe disability occurs.

### Modeling Approaches

I evaluated two complementary strategies to model disability progression:

**1. Survival-Based Model — Weibull_min Distribution (Best Performer)**
- Treats disability progression as a time-to-event process
- Captures non-linear dynamics (acceleration/deceleration)
- Handles censored data naturally
- Provides probabilistic confidence intervals

**2. Ensemble Curve Fitting**

I also developed an ensemble approach averaging three mathematical models to create a 
robust baseline:
- **Exponential:** Assumes constant proportional growth
- **Logistic:** Models growth with saturation limits
- **Power Law:** Models decelerating progression

### Key Results & Clinical Interpretation

The Weibull survival model proved to be the most clinically realistic method for the 
3–6 year window.

**Optimal Parameters**

| Parameter | Value |
|-----------|-------|
| Shape (k) | `1.1214` |
| Scale (λ) | `0.4425` |
| Location | `0.0000` (fixed) |
| Baseline DSS | `2.0` |

**Interpretation**
- **Progression Dynamics (k > 1):** A shape parameter of 1.12 indicates a slightly 
  accelerating hazard, meaning the speed of disability progression increases modestly 
  over time during this transitional phase
- **Timing (λ = 0.44):** Suggests a median time to the next DSS level of approximately 
  1.6 years

**Clinical Example**

| | |
|-|-|
| **Scenario** | An MS patient presents with a DSS of 2.0 at Year 3 |
| **Prediction** | The model forecasts a DSS of 3.3 by Year 6 |
| **Insight** | This indicates a slow progression, suggesting a valuable window for therapeutic intervention before the patient reaches severe disability (DSS 6+) |

---

## Team & Full Project

IntegraMS was built as a team capstone project. The complete codebase spans three private 
repositories covering modeling, front-end, and back-end development. This folder reflects 
my individual contributions to the modeling pipeline.
