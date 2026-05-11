# 🚀 2024 Tech Career Strategic Intelligence Dashboard

### *Navigating the Global Data Job Market with Evidence-Based Insights*

![Tech Job Market Insight 2024 - Dashboard](/images/Tech_Dashboard_1.png)

## 📋 Project Overview

The **2024 Tech Career Strategic Intelligence Dashboard** is a comprehensive analytical tool designed to solve the uncertainty inherent in modern job searching. By processing a global dataset of job postings from the full year of 2024, this project provides a macro and micro view of the tech industry.

It moves beyond simple job counts to analyze the intersection of **Geography, Compensation, Skill Demand, and Academic Barriers**, offering a multidimensional roadmap for anyone looking to enter or advance in the data field.

---

## 🎯 Strategic Foundation

Every visual in this dashboard was built to answer a specific set of foundational questions:

### 1. What problem are we trying to solve?

Job seekers are often overwhelmed by "skill fatigue"—the feeling that they must learn everything at once. This dashboard solves this by:

* **Quantifying Skill ROI:** Showing exactly which skills correlate with higher salaries.
* **Reducing Search Friction:** Identifying which companies and regions are most active in hiring for specific roles.
* **Validating Career Paths:** Showing the actual necessity of a degree vs. skills-first hiring to set realistic expectations for applicants.

### 2. Who are you designing this for?

* **Aspiring Data Professionals:** To guide their learning roadmap based on market value.
* **Senior Analysts & Engineers:** To benchmark their current salary against global market rates.
* **HR & Recruitment Strategists:** To understand competitor benefits (Remote work, Insurance) and salary offerings.

---

## 📊 Feature Breakdown

### 🛠️ Data Engineering & Modeling

* **Unpivoting Skill Sets:** Leveraged Power Query to transform nested JSON-like skill lists into a flat, relational structure, enabling the analysis of over 100+ unique technologies.
* **Boolean Normalization:** Created DAX calculated columns to turn technical True/False values into human-readable labels like **"Remote Opportunity"** and **"Skills-Based Hiring."**
* **Time-Series Integration:** Built a dedicated Calendar Table to allow the **Timeline Slicer** to filter data across months and quarters of 2024.

### 📈 Visual Insights

* **The ROI Scatter Plot:** The centerpiece of the dashboard. It categorizes skills into four quadrants: *High Demand/Standard Pay*, *High Demand/High Pay (Power Skills)*, *Niche/High Pay*, and *Foundational*.
* **Global Salary Hotspots:** A dynamic map visual using **Median Yearly Salary** as bubble size, allowing users to find locations that offer the best financial returns.
* **Degree Accessibility Metric:** A donut chart that highlights the percentage of the market that does not explicitly require a degree, emphasizing the growth of competency-based hiring.

---

## 🧪 Deep Dive Study: 2024 Data Analyst Market Trends

Using the interactive filters of the dashboard, we performed a targeted study on the **Data Analyst** job title to understand the specific roadmap for entry-to-mid-level professionals.

![Tech Job Market Insights 2024 - Data Analyst](/images/Tech_Dashboard_2.png)

### 1. The Skill-Salary Paradox

For Data Analysts, the scatter plot reveals a clear distinction between **Foundational** and **Premium** skills:

* **High Volume (The "Baseline"):** SQL and Excel remain the most frequently mentioned skills. While essential for getting an interview, they sit at a lower median salary point, indicating they are "entry stakes."
* **High Value (The "Negotiation Lever"):** Proficiency in **Python**, **Tableau**, and **Power BI** shifts the data points higher on the Y-axis. Analysts mastering these visualization and automation tools see a median salary increase of approximately **15-20%** compared to those with only spreadsheet skills.

![Tech Job Market Insights 2024 - Skills](/images/Tech_Dashboard_3.png)

### 2. Educational Accessibility

The study shows that the Data Analyst role is one of the most accessible in the tech sector:

* **Skills-First Trend:** Over **35%** of Data Analyst postings in 2024 do not explicitly require a degree in the job description.
* **Strategy:** This suggests that a strong portfolio (like this dashboard) and verified technical certifications are highly effective for this specific career path.

![Tech Job Market Insights 2024 - Data Analyst](/images/Tech_Dashboard_2.png)

### 3. Remote Work & Geography

* **Flexibility:** The **Remote Work %** for Data Analysts stayed consistent at roughly **30%** throughout 2024, showing that while many companies are returning to offices, the analytical nature of the work maintains high remote viability.
* **Hotspots:** The map indicates that while major tech hubs (SF, NYC, London) offer the highest raw salaries, secondary hubs are emerging with highly competitive median pay when adjusted for cost of living.

![Tech Job Market Insights 2024 - Time filtering ](/images/Tech_Dashboard_4.png)

### 4. Strategic Recommendations for Candidates

Based on the dashboard insights, a Data Analyst in 2024 should:

1. **Prioritize SQL & Power BI/Tableau:** These are the "Golden Trio" for maximum visibility.
2. **Highlight Remote-Ready Skills:** Focus on cloud-based collaboration tools mentioned in the `job_via` and `job_skills` data.ss
3. **Build a Portfolio:** Since a degree is often not mentioned, a tangible project demonstrating data storytelling (like this Power BI report) acts as the primary validator for recruiters.

---

## 💡 Technical Deep Dive (DAX)

To provide dynamic and accurate filtering, the following measures were implemented:

```dax
// Measure: Calculate the percentage of "Skills-First" jobs
% No Degree Required = 
VAR TotalJobs = COUNTROWS('job_postings')
VAR NoDegreeJobs = CALCULATE(COUNTROWS('job_postings'), 'job_postings'[job_no_degree_mention] = TRUE)
RETURN
DIVIDE(NoDegreeJobs, TotalJobs, 0)

// Measure: Dynamic Remote Work Ratio
Remote % = 
DIVIDE(
    CALCULATE(COUNTROWS('job_postings'), 'job_postings'[job_work_from_home] = TRUE),
    COUNTROWS('job_postings'), 
    0
)

```

---

## 🏁 Conclusion

The 2024 data reveals a tech market in transition. While foundational skills like **SQL** and **Excel** remain non-negotiable for entry, the "Salary Ceiling" is consistently broken by those mastering **Cloud (AWS/Azure)** and **Big Data (Spark/Python)**.

Furthermore, the dashboard proves that the "Degree Barrier" is softening, with a significant percentage of high-paying roles focusing on verifiable technical skills. By utilizing this dashboard, a job seeker can transition from a "spray and pray" application strategy to a **Targeted Career Strike**, focusing only on the roles, locations, and skills that align with their personal and financial goals.

---

**Developed by:** Hadeer Al-Tabaa

**Tools:** Power BI, Power Query, DAX

**Data Scope:** January - December 2024

**Contact:** [Hadeer Altabaa LinkedIn Profile Link](https://www.linkedin.com/in/hadeeraltabaajuniorwebdeveloper/)

---

*Disclaimer: This dashboard is based on available 2024 job posting data and is intended for informational and career-planning purposes.*
