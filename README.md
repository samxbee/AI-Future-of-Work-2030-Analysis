#  AI & The Future of Work (2030): The "High-Touch" Shield

###  Project Context
*This project is the first entry in my data analytics portfolio, completed as a capstone case study for the **Google Data Analytics Professional Certificate**.*

###  Executive Summary
**Does being a "Generalist" protect you from AI? The data suggests: No.**

This project analyzes a dataset of 3,000 job roles to predict automation trends by the year 2030. While common career advice suggests that "stacking more skills" (Versatility) reduces risk, my analysis found **no significant correlation** between skill quantity and job safety.

**The Reality:** The data isolates **Formal Education** and **"High-Touch" Capability** (Emotional Intelligence) as the strongest predictors of resilience against automation.

####  Key Findings at a Glance
| Metric | Finding |
| :--- | :--- |
| **Correlation (Skills vs. Safety)** | `~0.02` (Negligible) |
| **High Risk Group** | **~85%** avg. automation probability for Manual/Routine roles. |
| **Low Risk Group** | **<10%** avg. automation probability for PhD/High-Touch roles. |
| **Safest Cluster** | "High-Touch" Service (Nursing, Teaching) regardless of degree. |

---

###  Key Visualizations

![Automation Risk by Role and Education](automation_risk_by_role_education.png)
*Figure 1: Automation risk patterns across role clusters reveal education's protective effect varies by job type. High-Touch roles (Nursing, Teaching) show consistently low risk regardless of degree, while Cognitive roles benefit significantly from advanced education.*

###  The Analyst's Journey: From Data to Wisdom
*This project evolved from a simple visualization exercise into a deep-dive investigation of data integrity and feature engineering.*

#### 1. The Challenge
I started by asking: *"Which jobs are safe?"* The raw data offered a binary view: High Risk vs. Low Risk. However, this conflated very different roles grouping "Customer Support" (Desk) with "Factory Workers" (Manual) simply because both had high automation probabilities.

#### 2. The Discovery (Data Integrity)
During the cleaning process, I identified significant **redundancy in job listings**, requiring a rigorous de-duplication process to ensure my risk averages weren't skewed by repeated low-quality data points.

#### 3. The Solution (Feature Engineering)
To find the *nuance* in the data, I engineered my own classification feature, **`Role_Cluster`**, using **Regex logic** to segment the workforce into three distinct categories:
* ** Manual Labor:** (e.g., Drivers, Mechanics, Technicians)
* ** Cognitive Desk:** (e.g., Analysts, Customer Support, Software Engineers)
* ** High-Touch Service:** (e.g., Nurses, Teachers, Doctors)

---

###  Methodology & Technical Approach
**Tools:** Google Sheets (Advanced Formulas, Pivot Tables, Visualization)

#### Key Techniques:
* **Regex Classification (Feature Engineering):**
    Created a custom formula to taxonomize job titles based on keywords, correcting for "False Positives" (e.g., distinguishing *Customer Support* from *Manual Labor*).
    ```excel
    =IF(REGEXMATCH(A2, "(?i)Construction|Technician|Driver|Mechanic|..."), "Manual_Labor",
     IF(REGEXMATCH(A2, "(?i)Nurse|Teacher|Doctor|Therapist..."), "High_Touch_Service", "Cognitive_Desk"))
    ```
* **Correlation Analysis (`=CORREL`):**
    Tested the hypothesis: *"Does Skill Versatility correlate with lower Automation Risk?"*
* **Pivot Table Segmentation:**
    Analyzed the intersection of `Education_Level` and `Role_Cluster` to visualize the "Staircase of Safety."

---

###  Key Data Insights

#### 1. The "Generalist" Myth
There is **no statistical evidence** in this model that simply acquiring "more skills" reduces automation risk. A Retail Worker with 7 distinct skills had a nearly identical risk profile (90%+) as one with 3 skills. **Depth (Specialization) appears to outweigh Breadth.**

#### 2. The "Staircase" of Education
* **Manual Labor:** High risk regardless of education. A High School diploma here carries **~85% automation probability**.
* **Cognitive Roles:** Education acts as a shield. Automation risk drops precipitously from **up to 80%desk jobs.

#### 3. The "High-Touch" Safe Haven
My custom segmentation revealed that **"High-Touch" roles** (Nursing, Teaching) are the most resilient category. Unlike Cognitive roles (which need PhDs to be safe) or Manual roles (which are rarely safe), High-Touch roles showed **low automation risk** across all education levels.

---

###  Limitations & Assumptions
* **Synthetic Data:** This analysis uses a synthetic dataset designed for educational purposes. Real-world automation rates will be influenced by local regulations and technology costs.
* **Simplification:** The "Manual vs. Cognitive" split is based on job title keywords and may not capture the full complexity of hybrid roles.
* **Scenario-Based:** Risk probabilities are scenario predictions, not deterministic outcomes.

---

###  Files in This Repository
* **[AI_Impact_Jobs_2030_Analysis.xlsx](./AI_Impact_Jobs_2030_Analysis.xlsx)**: The complete workbook containing:
    * `Raw_Data` (Original source)
    * `Working_Data` (Cleaned with Regex Logic & Versatility Scores)
    * `Analysis` (Pivot Tables & Dashboards)

---

*Author: Sam B. Suaaidi*


*Connect with me on LinkedIn: https://www.linkedin.com/in/samxbe/*
