![Screenshot 2025-06-01 163921](https://github.com/user-attachments/assets/b0908f1f-0045-4482-b583-bd89d01711a8)![Screenshot 2025-06-01 163921](https://github.com/user-attachments/assets/3170df2c-2808-4b8a-9828-752b1f121f79)# IBM HR Analytics: Employee Attrition & Performance Analysis

## Introduction

Employee attrition (voluntary or involuntary resignation) affects organizational performance and productivity. This project analyzes IBM HR analytics data to uncover trends, patterns, and factors associated with employee attrition, aiming to support data-driven HR decisions.

---

## Table of Contents

1. [Project Overview](#project-overview)  
2. [Data Source](#data-source)  
3. [Tools and Technique](#tools-and-technique)  
4. [Data Processing and Cleaning](#data-processing-and-cleaning)  
5. [Exploratory Data Analysis](#exploratory-data-analysis)  
6. [Performance Comparison](#performance-comparison)  
7. [Recommendations](#recommendations)  
8. [Limitations](#limitations)

---

## Project Overview

The analysis focused on understanding the key drivers of employee attrition within IBM. We examined how job roles, departments, age, gender, overtime, and marital status affect attrition. The goal was to provide actionable insights for HR teams to reduce voluntary exits.

*Key Questions Addressed:*
- What is the overall attrition rate?
- Which employee attributes are linked to higher attrition?
- How does overtime, age, or marital status affect employee retention?

---

## Data Source

- *Dataset Title*: IBM HR Analytics Employee Attrition & Performance  
- *Source*: [Kaggle Dataset](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)  
- *Total Records*: 1,470  
- *Features*: 35 (including Job Role, Age, Overtime, Marital Status, Gender, etc.)

---

## Tools and Technique

- *Power BI*: For dashboard creation and visual insights  
- *Microsoft Excel*: For data cleaning and transformation  
- *SQL*: For performing queries during analysis

---

## Data Processing and Cleaning

The raw dataset was cleaned in Excel:
- Removed unnecessary columns like EmployeeNumber, Over18, and EmployeeCount
- Verified data types (e.g., converting Attrition to binary)
- Checked for missing values (none found)
- Added derived columns like Age Group (e.g., <30, 30-39, 40+)

---

##  Exploratory Data Analysis

###  Overall Stats:
- *Total Employees*: 1,470  
- *Attrition Count*: 237  
- *Attrition Rate: **16.1%*
  [Screenshot 2025-06-01 163726](https://github.com/user-attachments/assets/a9f5a551-680c-46e4-972e-e2101869370d)


---

### Attrition by Marital Status  
*Finding*: Single employees had the highest attrition rate compared to married and divorced employees.
[Screenshot 2025-06-01 163819](https://github.com/user-attachments/assets/3a4a42a1-42b5-4e2a-adbf-bcfe2634457f)


---

###  Attrition by Overtime  
*Finding: Attrition is significantly higher among employees who worked overtime — **30.53%* vs *10.44%* for those who didn’t.
[Screenshot 2025-06-01 163849](https://github.com/user-attachments/assets/b7277898-c025-41be-abee-57cf67db597f)



---

### Attrition by Age Group  
*Finding: Employees aged **30-39* showed the highest attrition count.
[Uploading Screenshot 2025-06-01 163921.png…]()




---

###  Attrition by Job Role and Department  
*Finding*: Sales Representatives and Laboratory Technicians had the highest attrition. Sales Department saw more exits than R&D or HR.
[Screenshot 2025-06-01 164141](https://github.com/user-attachments/assets/f82d7975-5f66-4905-8c04-e38615f4a7e9)



---

###  SQL-Like Query Examples

Here are some sample queries I used during my data exploration (replicated using Excel filters or SQL tools):

```sql
-- Employees who worked overtime and left
SELECT COUNT(*) 
FROM employee_data
WHERE Overtime = 'Yes' AND Attrition = 'Yes';

-- Attrition rate by Job Role
SELECT JobRole, 
       COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END) * 100.0 / COUNT(*) AS AttritionRate
FROM employee_data
GROUP BY JobRole;

-- Gender-wise attrition
SELECT Gender, 
       COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END) AS AttritionCount,
       COUNT(*) AS Total,
       (COUNT(CASE WHEN Attrition = 'Yes' THEN 1 END)100.0 / COUNT()) AS AttritionRate
FROM employee_data
GROUP BY Gender;
```

---
## Performance Comparison

A comparative breakdown showed:

Females had slightly higher attrition (18.1%) than males (14.6%).

Business travelers who traveled frequently left more often.

Job satisfaction and environment satisfaction showed minor correlation with attrition.

[Screenshot 2025-06-01 164243](https://github.com/user-attachments/assets/cedcc851-8ad7-454a-b952-f486ab505c60)

![Screenshot 2025-06-01 164003](https://github.com/user-attachments/assets/85c25153-3eba-47da-a393-be0dc62863af)



---

## Recommendations

1. Address Overtime Pressure: Implement work-life balance policies and reward fair workloads.


2. Focus on At-Risk Groups: Single, younger employees in sales roles should be targeted with retention strategies.


3. Employee Engagement: Regular surveys on job satisfaction and proactive HR support may improve retention.


4. Mentorship Programs: Create growth pathways especially for entry/mid-level roles with high attrition.




---

 ## Limitations

The data is anonymized and doesn't reflect changes over time.

External factors (e.g., economic issues, personal reasons) are not included.

No real-time performance metrics beyond survey-based scores.

Results may not generalize across other industries or geographies.

---

Author

Esther Anuoluwapo Ishola
Data Analyst | Excel & Power BI Enthusiast
Location: Ibadan, Nigeria
Email: [isholaesther6@gmail.com]
