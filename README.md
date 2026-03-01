🎓 Student Mental Health & Lifestyle Analytics Dashboard
📌 Project Overview

This project analyzes how lifestyle behaviors influence students’ mental health and academic performance using Power BI.
The aim is to transform raw behavioral data into a decision-support dashboard that helps identify stress drivers and detect students who may require early intervention.

The dashboard explores relationships between:

- Sleep patterns
- Study habits
- Social media usage
- Physical activity
- Counseling participation
- Family support systems
- Academic performance (GPA)
- Self-reported stress levels

---

🎯 Project Objectives

✔ Understand key lifestyle factors affecting student mental health
✔ Identify patterns associated with high stress levels
✔ Segment students into behavioral risk categories
✔ Provide actionable insights for wellbeing and academic planning
✔ Demonstrate real-world data analytics using Power BI and DAX

---

📂 Dataset Description

The dataset contains anonymized student records describing lifestyle, academic, and psychological indicators.

Column| Description
Student ID| Unique identifier for each student
Age| Student age
Gender| Gender category
Study Hours| Weekly academic study time
Sleep Hours| Average sleep per night
Social Media Hours| Daily social media usage
Exercise Hours| Weekly physical activity
Diet Quality| Self-reported nutrition quality
Family Support| Perceived family support level
Counseling Attendance| Whether student attends counseling
GPA| Academic performance score
Stress Level| Self-reported stress score (1–10)

---

🛠 Tools & Technologies Used

- Power BI Desktop — Visualization and dashboard development
- Power Query — Data cleaning and transformation
- DAX (Data Analysis Expressions) — Analytical modeling and KPIs
- Microsoft Excel — Source dataset

---

🔄 Data Preparation Process

1. Imported Excel dataset into Power BI.
2. Cleaned and standardized column names.
3. Corrected data types for numeric and categorical variables.
4. Removed blank or inconsistent records.
5. Built calculated measures and segmentation fields.

---

📊 Key Metrics Created (DAX)

Average Indicators

Avg Stress = AVERAGE(Data[Stress Level])
Avg Sleep = AVERAGE(Data[Sleep Hours])
Avg Study Hours = AVERAGE(Data[Study Hours])
Avg GPA = AVERAGE(Data[GPA])
Total Students = COUNT(Data[Student ID])

---

Stress Category Segmentation

Stress Category =
SWITCH(TRUE(),
Data[Stress Level] <= 3, "Low",
Data[Stress Level] <= 6, "Moderate",
"High"
)

This classification allows easier visualization of student wellbeing distribution.

---

Behavioral Stress Risk Score (Composite Metric)

A calculated indicator combining multiple behavioral risk factors:

Stress Risk Score =
VAR SleepRisk = IF(AVERAGE(Data[Sleep Hours]) < 6, 2, 0)
VAR SocialRisk = IF(AVERAGE(Data[Social Media Hours]) > 4, 2, 0)
VAR ExerciseRisk = IF(AVERAGE(Data[Exercise Hours]) < 2, 2, 0)
RETURN SleepRisk + SocialRisk + ExerciseRisk

---

Risk Classification

Risk Level =
SWITCH(TRUE(),
[Stress Risk Score] <= 1, "Low Risk",
[Stress Risk Score] <= 3, "Moderate Risk",
"High Risk"
)

This helps identify students potentially needing wellbeing support.

---

📈 Dashboard Structure

🔹 Page 1 — Executive Overview

- KPI Cards (Average Stress, Sleep, GPA, Student Count)
- Stress Distribution by Category
- Study Hours vs Stress Visualization

🔹 Page 2 — Lifestyle Drivers

- Sleep vs Stress Scatter Analysis
- Social Media Usage vs Academic Performance
- Exercise vs Stress Relationship
- Key Influencers Visual identifying major stress drivers

🔹 Page 3 — Risk Monitoring

- Risk Level Segmentation Charts
- High-Risk Student Identification Table
- Behavioral indicators for early detection

---

🔍 Key Insights Discovered

📉 Reduced sleep duration is strongly associated with higher stress levels.
📱 Excessive social media usage correlates with declining academic outcomes.
🏃 Students engaging in regular exercise report lower stress indicators.
🎓 Balanced lifestyle habits align with stronger academic performance.
⚠ A defined segment of students falls into a high behavioral risk category.

---

💡 Business Value of This Analysis

This dashboard demonstrates how data analytics can support:

- Student wellbeing programs
- Preventive mental health strategies
- Academic advisory planning
- Counseling resource allocation
- Evidence-based institutional decision-making

---

📁 Repository Structure

student-mental-health-dashboard/
│
├── dataset/
│   └── Student mental health Analysis.xlsx
│
├── dashboard/
│   └── MentalHealthDashboard.pbix
│
├── images/
│   └── dashboard-preview.png
│
└── README.md

---

🚀 How to Use This Project

1️⃣ Download the ".pbix" file.
2️⃣ Open with Power BI Desktop.
3️⃣ Refresh data if prompted.
4️⃣ Use slicers to explore different student segments interactively.

---

📚 Skills Demonstrated

- Data Cleaning & Transformation
- Data Modeling in Power BI
- Advanced DAX Calculations
- Behavioral Data Analysis
- Risk Segmentation Techniques
- Interactive Dashboard Design
- Insight Communication & Storytelling

---

🔮 Future Enhancements

- Predictive analytics for stress forecasting
- Integration with longitudinal student data
- Machine learning classification of risk patterns
- Automated reporting for institutional monitoring

---

👤 Author

Abdul-Razaq Abdul-Qadir Adedeji
Biochemist transitioning into Data Analytics with a focus on applying data-driven solutions to health, education, and organizational wellbeing.

---

⭐ Project Purpose

This project was developed as part of a professional data analytics portfolio to demonstrate the ability to transform raw behavioral datasets into meaningful, decision-oriented insights.
