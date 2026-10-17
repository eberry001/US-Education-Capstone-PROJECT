# Data Dictionary & Documentation: American Educational System Dataset

## 1. Overview & Dataset Context

This dataset presents a comprehensive, statistically representative sample of **5,000 educational institutions** across the United States. Designed to model the structural, demographic, financial, and academic dynamics of the American educational ecosystem, the dataset spans K-12 public, charter, and private schools as well as 2-year community colleges and 4-year higher education institutions across all 50 states and the District of Columbia.

- **File Name:** [`us_education_system_dataset.csv`](file:///Users/peterokwukogu/Downloads/Antigravity/us_education_system_dataset.csv)
- **Primary Unit of Analysis:** Individual Educational Institution (School / College)
- **Total Records:** 5,000 rows (excluding header)
- **Total Columns:** 35 variables
- **Standard Alignment:** Aligned with U.S. Department of Education and National Center for Education Statistics (NCES) reporting conventions (e.g., Common Core of Data / IPEDS frameworks).

---

## 2. Key Educational System Dimensions

1. **Governance & School Level:** Reflects the American division between public school districts, public charter schools (independent public entities), private non-profit/religious institutions, and postsecondary colleges.
2. **Socioeconomic Status (SES):** Utilizes Free/Reduced-Price Lunch (FRL) eligibility—the standard US metric for economic disadvantage—and Title I federal funding status under the Elementary and Secondary Education Act (ESEA).
3. **Geographic Locales:** Categorized according to NCES urbanicity classifications (City, Suburban, Town, Rural).
4. **Demographic Composition:** Detailed student racial and ethnic distributions matching federal race/ethnicity reporting, along with Special Education (IEP) and English Language Learner (ELL) rates.
5. **Funding Mechanics:** Captures per-pupil spending alongside federal, state, and local funding revenue shares, illustrating US property-tax-dependent education finance.
6. **Academic Performance & Progression:** Standardized test proficiency (Math and Reading), composite SAT/ACT scores, 4-year high school graduation rates, AP/IB participation, and postsecondary college enrollment.

---

## 3. Data Dictionary

| # | Column Name | Data Type | Value Range / Categories | Detailed Description & Educational Significance |
|---|---|---|---|---|
| 1 | `institution_id` | String | `US-EDU-10001` – `US-EDU-15000` | Unique institutional record identifier (analogous to NCES School/NCES District ID). |
| 2 | `institution_name` | String | Text | Full legal or operational name of the educational institution. |
| 3 | `state_code` | String | 2-Letter US Abbreviation (`CA`, `TX`, `NY`, etc.) | Two-letter state postal abbreviation covering all 50 US states plus DC. |
| 4 | `state_name` | String | Full State Name | Complete state name where the institution is located. |
| 5 | `county` | String | Text (e.g., `Los Angeles County`) | County or county-equivalent local administrative region. |
| 6 | `nces_locale` | String | `City - Large`, `City - Midsize`, `Suburban - Large`, `Suburban - Midsize`, `Town - Fringe`, `Town - Distant`, `Rural - Fringe`, `Rural - Remote` | Official NCES urbanicity code based on population density and proximity to urban clusters. |
| 7 | `level` | String | `Elementary School`, `Middle School`, `High School`, `K-12 Combined`, `2-Year College`, `4-Year University` | Educational tier/grade span served by the institution. |
| 8 | `control` | String | `Public`, `Public Charter`, `Private Non-Profit`, `Private Religious`, `Private For-Profit` | Institutional governance structure and funding mechanism. |
| 9 | `title_i_status` | String | `Title I Schoolwide`, `Title I Targeted`, `Not Title I Eligible`, `Not Applicable` | Federal Title I eligibility under ESEA for schools with high concentrations of low-income students. |
| 10 | `total_enrollment` | Integer | 80 – 52,000 | Total count of full-time and part-time enrolled students. |
| 11 | `number_of_teachers` | Integer | 1 – 3,000 | Total full-time equivalent (FTE) instructional teaching staff. |
| 12 | `student_teacher_ratio` | Float | 6.0 – 30.0 | Ratio of enrolled students to full-time equivalent instructional staff (`total_enrollment / number_of_teachers`). |
| 13 | `percent_free_reduced_lunch` | Float | 0.0% – 98.0% | Percentage of students eligible for Free or Reduced-Price Lunch under the National School Lunch Program (key SES proxy). |
| 14 | `racial_white_pct` | Float | 0.0% – 100.0% | Percentage of enrolled students identifying as Non-Hispanic White. |
| 15 | `racial_black_pct` | Float | 0.0% – 100.0% | Percentage of enrolled students identifying as Black or African American. |
| 16 | `racial_hispanic_pct` | Float | 0.0% – 100.0% | Percentage of enrolled students identifying as Hispanic or Latino of any race. |
| 17 | `racial_asian_pct` | Float | 0.0% – 100.0% | Percentage of enrolled students identifying as Asian, Native Hawaiian, or Pacific Islander. |
| 18 | `racial_native_pct` | Float | 0.0% – 100.0% | Percentage of enrolled students identifying as American Indian or Alaska Native. |
| 19 | `racial_two_or_more_pct` | Float | 0.0% – 100.0% | Percentage of enrolled students identifying with two or more racial categories. |
| 20 | `special_education_pct` | Float | 4.0% – 25.0% | Percentage of students receiving special education services under an Individualized Education Program (IEP / IDEA). |
| 21 | `english_learner_pct` | Float | 0.0% – 45.0% | Percentage of students classified as English Language Learners (ELL) requiring language support services. |
| 22 | `per_pupil_expenditure_usd` | Integer | \$7,500 – \$65,000 | Annual institutional expenditure or operating budget allocated per student in USD. |
| 23 | `federal_funding_pct` | Float | 0.0% – 40.0% | Percentage of institutional budget derived from US federal government grants (e.g., Title I, IDEA, Pell). |
| 24 | `state_funding_pct` | Float | 0.0% – 70.0% | Percentage of institutional budget derived from state government appropriations and aid formulas. |
| 25 | `local_funding_pct` | Float | 0.0% – 98.0% | Percentage of budget from local sources (local property taxes for public schools; tuition/endowments for private schools). |
| 26 | `math_proficiency_pct` | Float | 12.0% – 96.0% | Percentage of students scoring at or above state/national proficiency standards in standardized math assessments. |
| 27 | `reading_proficiency_pct` | Float | 15.0% – 98.0% | Percentage of students scoring at or above state/national proficiency standards in standardized reading/ELA assessments. |
| 28 | `graduation_rate_pct` | Float | 55.0% – 99.5% | Adjusted 4-year cohort high school graduation rate (or 6-year postsecondary graduation rate). |
| 29 | `chronic_absenteeism_pct` | Float | 4.0% – 58.0% | Percentage of students missing 10% or more of school days during the academic year. |
| 30 | `avg_sat_score` | Integer / Blank | 720 – 1560 (or empty for primary) | Average composite SAT score (Math + Evidence-Based Reading & Writing, 400–1600 scale). Blank for primary/middle tiers. |
| 31 | `avg_act_score` | Float / Blank | 12.0 – 35.0 (or empty for primary) | Average composite ACT score (1–36 scale). Blank for primary/middle tiers. |
| 32 | `ap_ib_participation_pct` | Float / Blank | 2.0% – 75.0% (or empty for primary) | Percentage of high school juniors and seniors enrolled in at least one Advanced Placement (AP) or International Baccalaureate (IB) course. |
| 33 | `postsecondary_enrollment_pct` | Float / Blank | 25.0% – 95.0% (or empty for primary) | Percentage of high school graduates who enroll in a 2-year or 4-year postsecondary institution within 12 months of graduation. |
| 34 | `stem_certified_flag` | String | `Yes`, `No` | Indicates whether the institution offers a state- or nationally-certified STEM magnet curriculum or specialized track. |
| 35 | `broadband_access_pct` | Float | 50.0% – 99.0% | Estimated percentage of student households with reliable high-speed home broadband internet access. |

---

## 4. Institutional & Geographic Distribution in the Dataset

### Breakdown by School Level
- **Elementary School:** ~2,200 institutions (44%)
- **High School:** ~1,250 institutions (25%)
- **Middle School:** ~1,000 institutions (20%)
- **4-Year University:** ~200 institutions (4%)
- **K-12 Combined:** ~200 institutions (4%)
- **2-Year Community College:** ~150 institutions (3%)

### Governance / Control Types
- **Public (Traditional District):** ~3,600 institutions (72%)
- **Public Charter:** ~600 institutions (12%)
- **Private Non-Profit:** ~400 institutions (8%)
- **Private Religious:** ~300 institutions (6%)
- **Private For-Profit:** ~100 institutions (2%)

---

## 5. Potential Analytical Use Cases

1. **Educational Equity & Resource Allocation Analysis:**
   - Investigate how per-pupil expenditure (`per_pupil_expenditure_usd`) and funding sources (`local_funding_pct` vs `federal_funding_pct`) vary across low-SES (`percent_free_reduced_lunch`) and high-SES schools.
2. **Predictive Modeling for Graduation Rates & Achievement:**
   - Build machine learning models to predict `graduation_rate_pct` or `math_proficiency_pct` using student-teacher ratios, chronic absenteeism, and funding levels.
3. **Digital Divide & Achievement Gap Studies:**
   - Analyze the correlation between `broadband_access_pct`, `chronic_absenteeism_pct`, and standardized testing outcomes (`avg_sat_score`, `math_proficiency_pct`).
4. **Charter vs Traditional Public School Performance Comparisons:**
   - Compare academic proficiency and demographic segregation metrics between traditional public schools and charter schools controlling for locale and SES.

---

## 6. Accessing the Files

Both files are saved in the project workspace:
- **CSV Dataset:** [`us_education_system_dataset.csv`](file:///Users/peterokwukogu/Downloads/Antigravity/us_education_system_dataset.csv)
- **Data Dictionary:** [`us_education_system_data_dictionary.md`](file:///Users/peterokwukogu/Downloads/Antigravity/us_education_system_data_dictionary.md)
