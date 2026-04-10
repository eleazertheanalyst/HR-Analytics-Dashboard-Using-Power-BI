
# HR Analytics Dashboard Using Power BI

### Dashboard Link : https://app.powerbi.com/groups/dc3f4dcf-3a16-4f02-8302-60857ec16756/reports/519551e1-cb34-4746-a517-3d7034419cf2/b970eb87132d6650c0dc?experience=power-bi

## Project Overview

This project focuses on identifying and analyzing the key factors driving employee attrition within an organization. The dataset contained inconsistencies and unstructured values, requiring extensive data transformation before meaningful analysis could be performed.

Using Power BI, I designed a comprehensive and interactive dashboard that enables stakeholders to explore attrition patterns across demographics, job roles, compensation levels, and tenure.

The final output provides clear, data-driven insights to support HR teams in improving employee retention and workforce planning.

# Business Objective
The primary objective of this analysis was to:
- Understand the overall attrition rate within the organization
- Identify high-risk employee segments
- Analyze the relationship between attrition and key variables (age, salary, job role, tenure, education)
- Provide actionable recommendations to reduce employee turnover


### Steps followed 
- Step 1 : **Data Loading:** Imported the primary HR dataset (CSV file) along with supporting dimension tables (Education, Job Role, Department) to enrich the analysis and enable relational modeling.
- Step 2 : Reviewed the dataset using column profiling tools to identify inconsistencies, missing values, and formatting issues across categorical and numerical fields.
- Step 3 : **String Sanitization:** Cleaned categorical columns by removing unwanted characters such as double quotation marks (" ") and ensuring uniform text formatting across fields like Gender.
- Step 4 : **Value Standardization:** Cleaned the BusinessTravel column by replacing inconsistent delimiters and correcting CamelCase text (e.g., Non-Travel → Non Travel) to ensure proper grouping in visuals.
- Step 5 : **Numeric Normalization (The “None” Fix)**: Replaced "None" values in numeric columns with 0 and converted the affected fields into Whole Number data types for accurate calculations.
- Step 6 : **Data Type Correction:** Ensured all columns were assigned appropriate data types, including numerical fields (Monthly Income, Years at Company) and categorical fields for consistent analysis.
- Step 7 : **Missing Value Handling:** Assessed null values across the dataset and proceeded with analysis as missing values were minimal and automatically excluded in aggregations.
- Step 8 : **Data Integration & Modeling:** Established relationships between fact and dimension tables (Education, Job Role, Department) to support structured and scalable data modeling.
- Step 9 : **Theme Selection:** In the Report View, under the View tab, a high-contrast dark theme was selected to enhance readability and provide a professional, executive-style presentation.
- Step 10 : **KPI Card Visuals:** Inserted card visuals at the top of the canvas to display key metrics (Total Employees, Attrition, Attrition Rate, Average Salary), ensuring high-level insights are immediately visible.
- Step 11 : **Interactive Slicers:** Added slicers for Department, Education, and Job Role to enable dynamic filtering and allow users to perform focused, segment-level analysis.

- Step 12 : **Custom Visual Implementation:** Integrated appropriate visuals to represent attrition trends across age groups, salary bands, job roles, education fields, and tenure, ensuring clear storytelling.
- Step 13 : **Employee Count Measure:** Developed a DAX measure to calculate the total number of employees in the dataset.
    ```
    Employee_count = COUNT(HR_Data[EmployeeNumber]) 
    ```

- Step 14 : **Attrition Measure:** Created a DAX measure using CALCULATE to compute the total number of employees who have left the organization.
    ```
     Attrition_count = CALCULATE([Employee_count], HR_Data[Attrition]="Yes")
    ```

        
- Step 15 : **Attrition Rate Calculation:** Defined a measure to calculate the percentage of employee turnover relative to total headcount.

    ```
    Attrition_Rate = [Attrition_count] / COUNT(HR_Data[EmployeeCount])
    ```

        
 - Step 16 : **Average Salary Calculation:** Implemented a DAX measure using AVERAGE to compute the mean monthly income across employee segments.
 
    ```
    Avg_Salary = AVERAGE(HR_Data[MonthlyIncome])
    ```

 
 - Step 17 : **Dashboard Layout Design:** Structured the report layout to prioritize KPIs at the top, followed by trend analysis and detailed breakdowns, ensuring logical flow and readability.
 
 - Step 18 : The report was then published to Power BI Service.
<img width="491" height="289" alt="Image" src="https://github.com/user-attachments/assets/79146b28-dd43-4ee6-93a8-9687816341e9" />

# Snapshot of Dashboard (Power BI Service)

<img width="1904" height="930" alt="Image" src="https://github.com/user-attachments/assets/795c35c0-22a0-4d3d-a2e9-2dcb1dac5408" />

 
 # Report Snapshot (Power BI DESKTOP)

 
<img width="1303" height="730" alt="Image" src="https://github.com/user-attachments/assets/c8e23e7b-25c6-4b0a-99d4-257bd1559815" />

# Key Insights & Analytical Findings
### Overall Workforce Metrics
- Total Employees: 1,480
- Total Attrition: 238
- Attrition Rate: 16%

This indicates a moderate turnover level that warrants targeted intervention.

### Demographic Insights
- The 26–35 age group has the highest attrition
- Male employees show higher attrition compared to females

Inference:
Mid-career professionals may be experiencing stagnation, lack of growth opportunities, or external competition.

### Education Field Impact
- Life Sciences (37.39%) and Medical (26.47%) dominate attrition
- Technical degrees show a relatively high attrition rate despite smaller population size

Inference: Specialized roles may face high external demand, burnout or workload imbalance


### Job Role Distribution
- Research Scientists: 100 exits (highest)
- Laboratory Technicians: 58 exits
- Manufacturing Directors: Only 5 exits

Inference: Entry-to-mid-level technical roles are the most vulnerable
Senior roles show strong retention and stability

### Salary vs Attrition
- Highest attrition occurs in the “Up to 5K” salary bracket
- Attrition declines significantly as salary increases
- Almost negligible attrition in 15K+ range

**Inference:** There is a strong inverse relationship between salary and attrition, indicating compensation is a key driver of turnover.

### Tenure Analysis (“Attrition Danger Zones”)
- 1-Year Mark: Significant spike in attrition
- 5-Year Mark: Secondary peak
- 10+ Years: Minimal attrition

**Inference:** Early attrition suggests onboarding or job-fit issues. \
Mid-tenure attrition indicates lack of promotion or career growth

# Business Recommendations

**Based on the analysis:**
- Improve onboarding programs to reduce early attrition
- Introduce clear career progression paths for mid-level employees
- Review compensation structure for lower salary bands
- Focus retention strategies on technical and scientific roles
- Implement targeted engagement initiatives for 26–35 age group

# Technical Skills Demonstrated
- **ETL & Data Cleaning:** Power Query transformations
- **Data Modeling:** Relationships and schema design
- **DAX Calculations:** Measures and calculated columns
- **Data Visualization:** Power BI dashboard design
- **Analytical Thinking:** Translating data into business insights


