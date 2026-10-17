# US Education & Global Development Analytics
### Data Science & ML Workflow Capstone Project

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=for-the-badge&logo=scipy&logoColor=white)](https://scipy.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![AltSchool Africa](https://img.shields.io/badge/AltSchool_Africa-Baraka_2026-blueviolet?style=for-the-badge)](https://altschoolafrica.com/)

---

## ⚠️ Academic Disclaimer

> **IMPORTANT NOTICE:**  
> This dataset (`us_education_system_dataset.csv`) is **fully synthetic** and was generated strictly for **educational and analytical purposes** as part of the AltSchool Africa Data Science curriculum. While its structural design, variables, and distributions mirror real-world conventions from the U.S. Department of Education and National Center for Education Statistics (NCES Common Core of Data / IPEDS), all institutional records, metrics, and identifiers are simulated. This project does not reflect live institutional evaluations and should not be used as official government statistics.

---

## 📌 Executive Summary

Acting in the capacity of **Lead Data Scientist at an International Educational Policy Advisory Firm**, this capstone project investigates resource allocation mechanics, structural equity, and student performance metrics across **5,000 U.S. educational institutions**. 

Using the scientific Python stack (**NumPy**, **Pandas**, and **SciPy**), raw heterogeneous educational records were analyzed to evaluate systemic funding equity, data integrity, demographic indicators, and academic outcomes. The central directive of this study is to deliver an empirical briefing for the **Minister of Education** to guide national subsidy distribution and educational policy interventions.

### Key Takeaways:
1. **Funding Consistency & Computation:** Zero funding balance anomalies exist across all 5,000 institutions (`federal_funding_pct + state_funding_pct + local_funding_pct = 100%`). NumPy vectorized operations performed **~1,616x to 1,711x faster** than iterative loop-based logic.
2. **Socioeconomic Correlation with Graduation:** Student poverty concentration (Free/Reduced Lunch eligibility) exhibits a statistically significant moderate negative correlation with graduation rates ($r = -0.4153$, $p < 0.0001$). Conversely, household broadband internet access exhibits a statistically significant moderate positive correlation ($r = 0.3217$, $p < 0.0001$).
3. **Public vs. Private Completion Gap:** Private institutions achieve a statistically significantly higher mean graduation rate (**87.52%**) compared to Public institutions (**84.38%**), confirmed via independent two-sample t-test ($t = -14.2788$, $p < 0.0001$).
4. **Staffing Equity Across Locales:** One-Way ANOVA across Urban, Suburban, Town, and Rural locales revealed no statistically significant variation in student-teacher ratios ($F = 0.2463$, $p = 0.8640$), demonstrating geographical parity in instructional staffing.
5. **System-Wide Math Proficiency:** Bootstrap resampling (10,000 iterations) established a 95% confidence interval of **[59.55%, 60.46%]** around the sample mean math proficiency of **60.01%**, indicating high estimation stability.

---

## 📁 Repository Structure

```plaintext
US-edu-DATA-cap/
├── US_Education Capstone Project.ipynb      # Main Jupyter notebook containing all 7 analytical modules
├── us_education_system_dataset.csv          # Primary dataset (5,000 institutional records, 35 variables)
├── us_education_system_data_dictionary.md   # Official data dictionary & variable schema documentation
└── README.md                                # Comprehensive repository overview and project documentation
```

---

## 📊 Dataset Overview

The dataset provides a comprehensive representation of **5,000 educational institutions** spanning K-12 primary and secondary schools through 2-year community colleges and 4-year higher education universities across all 50 U.S. states and the District of Columbia.

- **Primary Unit of Analysis:** Individual Educational Institution (School / College)
- **Total Records:** 5,000 rows (excluding header)
- **Total Columns:** 35 variables
- **Standard Alignment:** Aligned with U.S. Department of Education and National Center for Education Statistics (NCES) Common Core of Data (CCD) and IPEDS reporting frameworks.

### Institutional Distribution

#### By Educational Level
| Institution Level | Record Count | Approximate Share |
|---|:---:|:---:|
| Elementary School | 2,225 | 44.5% (~2,200) |
| High School | 1,209 | 24.2% (~1,250) |
| Middle School | 996 | 19.9% (~1,000) |
| K-12 Combined | 212 | 4.2% (~200) |
| 4-Year University | 204 | 4.1% (~200) |
| 2-Year College | 154 | 3.1% (~150) |
| **Total** | **5,000** | **100.0%** |

#### By Governance / Control
| Control Type | Record Count / Representation | Share |
|---|:---:|:---:|
| Public (Traditional District) | ~3,600 | 72% |
| Public Charter | ~600 | 12% |
| Private Non-Profit | ~400 | 8% |
| Private Religious | ~300 | 6% |
| Private For-Profit | ~100 | 2% |

#### By NCES Locale
Institutions cover 8 detailed NCES urbanicity classifications:
`City - Large`, `City - Midsize`, `Suburban - Large`, `Suburban - Midsize`, `Town - Fringe`, `Town - Distant`, `Rural - Fringe`, and `Rural - Remote`. Consolidated in the study into four broad groups: **Suburban** (2,139), **Urban** (1,631), **Town** (642), and **Rural** (588).

---

## 🔬 Methodology & Project Modules

The capstone project was executed across seven rigorous modules in [`US_Education Capstone Project.ipynb`](file:///US_Education%20Capstone%20Project.ipynb):

### Module 1: Data Ethics & Privacy
- **Privacy Debt & Linkage Risk:** Analyzed how long-term retention of granular educational records poses re-identification hazards (e.g., student trajectory tracking across decades through quasi-identifiers like locale, demographics, and test scores cross-referenced with public databases).
- **Mock Security Protocol:**
  - *Storage Framework:* Segregated cloud repository certified under **ISO 27001** standards.
  - *Access Control:* Zero-Trust architecture utilizing **Role-Based Access Control (RBAC)** with mandatory multi-factor authentication (MFA).
  - *Encryption Standards:* **AES-256** encryption at rest and **TLS 1.3** cryptographic protocols in transit.
  - *Deletion Protocol:* Permanent cryptographic sanitization conforming to **NIST SP 800-88** guidelines.

### Module 2: High-Performance Numerical Analysis (NumPy)
- **Vectorized Funding Audit:** Evaluated institutional revenue shares (`federal_funding_pct + state_funding_pct + local_funding_pct`) using array broadcasting and boolean masking.
- **Funding Gap Detection:** Identified **0 schools** with funding gaps outside the tolerance threshold (99% – 101%), verifying dataset internal consistency.
- **Benchmarking Report:** Vectorized summation executed in **0.0006s – 0.0008s** compared to **1.0427s – 1.4463s** for iterative loops, yielding a **~1,616x to 1,711x computational acceleration**.

### Module 3: Advanced Data Wrangling & Aggregation (Pandas)
- **Hierarchical Grouping:** Multi-level segmentation by `nces_locale` and `control` (evaluating distribution skew across large suburban public clusters vs. sparse rural private cohorts).
- **Academic Aggregation:** Generated grouped statistical summaries (`mean`, `median`, `std`, `count`) for `avg_sat_score`.
- **Memory Optimization:** Converted object columns (`nces_locale` and `control`) to categorical dtypes (`category`) to optimize memory footprint and grouping throughput.

### Module 4: Quality Diagnostics & Group-Based Imputation
- **Null Value Diagnosis:** Missing values were detected in exactly 4 columns:
  - `avg_sat_score`: 3,375 nulls
  - `avg_act_score`: 3,375 nulls
  - `ap_ib_participation_pct`: 3,579 nulls
  - `postsecondary_enrollment_pct`: 3,579 nulls
- **Structural Missingness Crosstabs:** Cross-tabulation against `level` revealed missingness is **100% structurally determined**:
  - Elementary Schools (2,225) and Middle Schools (996) have 0 SAT/ACT/AP/IB/Postsecondary values.
  - 2-Year Colleges (154) do not report standard high school SAT/ACT or 4-year postsecondary transitions.
  - 4-Year Universities (204) report enrolled freshman SAT/ACT metrics but not high school AP/IB or secondary postsecondary transitions.
- **Ethical Imputation Decision:** Rather than mechanically imputing medians with `.transform()` (which would invent misleading scores for elementary institutions where metrics do not apply), structural nulls were intentionally preserved to uphold data integrity.

### Module 5: Outlier Surgery (Detect, Erase, Heal)
- **Target Variable:** `per_pupil_expenditure_usd`.
- **Step 1 (Detect):** Evaluated Interquartile Range fences ($Q1 - 1.5 \times IQR$, $Q3 + 1.5 \times IQR$) separately within each localized `nces_locale` $\times$ `control` cluster. Identified **128 institutional spending outliers**.
- **Step 2 (Erase):** Applied boolean masking via `.loc` to convert flagged spending outliers to `np.nan` within a clean series (`per_pupil_expenditure_cleaned`), isolating 128 missing values.
- **Step 3 (Heal):** Replaced the 128 `NaN` entries with localized group medians using `.transform('median')` and fancy indexing, returning remaining nulls to **0**.

### Module 6: Inferential Statistics & Hypothesis Testing (SciPy)
- **Independent Two-Sample T-Test:** Compared graduation rates between Public (`Public`, `Public Charter`) and Private (`Private Non-Profit`, `Private Religious`, `Private For-Profit`) institutions (`stats.ttest_ind`).
- **One-Way ANOVA:** Assessed variation in student-teacher ratios across 4 consolidated locale categories (`Urban`, `Suburban`, `Town`, `Rural`) (`stats.f_oneway`).
- **Non-Parametric Bootstrap Resampling:** Executed 10,000 resampling iterations (with replacement, seed = 42) to calculate the 95% percentile confidence interval of mean `math_proficiency_pct`.

### Module 7: Executive Communication
- **Pearson Bivariate Correlation:** Analyzed linear relationships between graduation rate and socioeconomic predictors (`percent_free_reduced_lunch` and `broadband_access_pct`).
- **Policy Briefing Translation:** Transformed empirical findings and p-values into concrete operational directives for government education administrators.

---

## 📈 Key Statistical Findings

| Research Question | Analytical Test | Key Metrics & Statistics | Result / Interpretation |
|---|---|---|---|
| **Revenue Stream Consistency** | Vectorized Boolean Masking | $\Sigma(\text{Federal} + \text{State} + \text{Local}) \in [99, 101]$ | **0 anomalies detected** across 5,000 institutions. Data is 100% consistent. |
| **Computational Vectorization Speed** | Execution Timing Benchmark | Loop: 1.0427s – 1.4463s<br>Vectorized: 0.0006s – 0.0008s | **~1,616x faster** execution leveraging NumPy array operations. |
| **Public vs. Private Graduation Rate** | Independent Two-Sample T-Test | Public Mean: **84.38%**<br>Private Mean: **87.52%**<br>$t = -14.2788$, $p = 0.0000$ | **Reject $H_0$ ($p < 0.0001$).** Statistically significant difference; private schools graduate at higher rates (+3.14%). |
| **Staffing Equity Across Locales** | One-Way ANOVA | $F = 0.2463$, $p = 0.8640$ | **Fail to Reject $H_0$.** No statistically significant difference in student-teacher ratio across Urban, Suburban, Town, and Rural locales. |
| **National Math Proficiency Estimate** | Bootstrap Resampling (10,000 iterations) | Sample Mean: **60.01%**<br>95% CI: **[59.55%, 60.46%]** | Narrow 0.91% interval confirms high precision and stability of system-wide math proficiency. |
| **Student Poverty vs. Graduation** | Pearson Correlation ($r$) | $r = -0.4153$, $p = 0.0000$ | **Statistically significant moderate negative relationship ($p < 0.0001$).** Higher poverty concentration is associated with lower graduation rates. |
| **Digital Divide vs. Graduation** | Pearson Correlation ($r$) | $r = 0.3217$, $p = 0.0000$ | **Statistically significant moderate positive relationship ($p < 0.0001$).** Higher broadband access is associated with higher graduation rates. |

---

## 🏛️ Policy Briefing: Action Plan for the Minister of Education

1. **Private vs. Public Graduation Disparity ($p < 0.0001$):**
   - **Finding:** Private institutions exhibit an average graduation rate of 87.52% compared to 84.38% in public schools.
   - **Action Plan:** Commission a focused task force to investigate private school operational practices—specifically instructional support structures, selective intake impacts, and cohort monitoring—to identify models adaptable into public systems.
2. **Poverty Concentration & Free/Reduced Lunch ($p < 0.0001$):**
   - **Finding:** A moderate negative correlation ($r = -0.4153$) confirms that economic disadvantage remains a persistent barrier to high school completion.
   - **Action Plan:** Target weighted compensatory funding formulas, specialized tutoring, academic counseling, and integrated nutritional assistance directly to schools exhibiting high Free/Reduced Lunch eligibility rates.
3. **Broadband Infrastructure & The "Homework Gap" ($p < 0.0001$):**
   - **Finding:** A moderate positive correlation ($r = 0.3217$) links home internet access with academic progression and completion.
   - **Action Plan:** Deploy municipal digital infrastructure subsidies and subsidized broadband access in underserved zones where high poverty overlaps with connectivity deficits.
4. **Instructional Staffing Across Locales ($p = 0.8640$):**
   - **Finding:** Student-teacher ratios do not meaningfully differ by urbanicity ($F = 0.2463$).
   - **Action Plan:** Avoid macro-level geographic reallocation of teacher quotas between urban and rural zones; prioritize school-level staffing audits for specific institutional outliers instead.

---

## 🛠️ Tech Stack & Libraries

- **Language:** Python 3
- **Numerical Processing:** [NumPy](https://numpy.org/) (`ndarray`, broadcasting, boolean masking, random choice resampling, percentile calculations)
- **Data Wrangling & Analysis:** [Pandas](https://pandas.pydata.org/) (`DataFrame`, hierarchical `groupby`, `.agg()`, `.crosstab()`, `category` dtypes, `.loc` indexing, `.transform()`)
- **Statistical Testing:** [SciPy](https://scipy.org/) (`scipy.stats.ttest_ind`, `scipy.stats.f_oneway`, `scipy.stats.pearsonr`)
- **Interactive Development:** [Jupyter Notebook](https://jupyter.org/)
- **Performance Profiling:** Python `time` module

---

## 🚀 How to Run the Project

Follow these steps to reproduce the analysis locally:

### 1. Clone the Repository
```bash
git clone https://github.com/<your-username>/<your-repo-name>.git
cd <your-repo-name>
```

### 2. Set Up a Virtual Environment (Optional but Recommended)
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS / Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install pandas numpy scipy jupyter
```

### 4. Launch Jupyter Notebook
```bash
jupyter notebook
```

### 5. Execute Analysis
Open [`US_Education Capstone Project.ipynb`](file:///US_Education%20Capstone%20Project.ipynb) in Jupyter and run all cells sequentially (`Cell` -> `Run All`).

---

## 👤 Author Information

- **Name:** Eberechi Bessie Donalds
- **Program:** Data Science
- **Cohort:** Baraka 2026
- **Institution:** [AltSchool Africa](https://altschoolafrica.com/)
- **Examination Date:** September 25, 2026
