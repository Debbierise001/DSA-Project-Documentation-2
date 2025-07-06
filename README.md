# DSA-Project-Documentation-2
Palmora Group HR Analysis

## Project Title: 

### Project Overview
This project analyzes employee data to gain insights into gender distribution, performance ratings, salary structures, bonus allocation, and regional differences. The goal is to uncover trends that can support better HR decision-making

### Tools Used
Power BI
* Data Collection
* Data Cleaning
  - Power Query for Extracting, Transforming and Loading Data (ETL)
  - DAX to create custom columns and measures
  - Roport View for data visualization and analysis


### Data Cleaning & Preparation
- Removed rows with missing salary or department.
- Replaced missing or private gender values with "Unspecified".
- Creating Custom columns to sort Gender and Ratings.
- Created salary band using conditional column logic
- Ensured consistent data types for analysis.

### Data Presentation & Visualizations
1. Gender Distribution: Helps HR monitor inclusion and diversity
  - Clustered bar chart: Gender by Department
  - Pie chart: Overall gender breakdown
  - Card: 
2. Performance Ratings by Gender: Evaluates fairness in scores
  - Clustered column chart: Count of ratings by gender
  - Card: Average rating by gender
  -
3. Salary Structure & Pay Gap: Highlights pay disparities across teams
  - Scatter chart: Salary vs. Gender
  - Bar chart: Average salary by department
  - 

4. Minimum Salary Threshold Analysis: Identifies underpaid regions or roles
  - Column Chart: Salary grouped in ₦10,000 bands
  - Bar Chart: Count of employees earning below ₦90,000

5. Bonus Calculation: Automates bonus logic and performance rewards 
  - Bar chart: Total bonus payout per region
  - Table: Employee-level bonus breakdown
 
### Key DAX Measures
- Gender Count = `COUNT('Employee'[Gender])`
- Gender Percentage = `DIVIDE(CALCULATE(COUNT('Employee'[Gender])), CALCULATE(COUNT('Employee'[Gender]), ALL('Employee'[Gender])))`
- Average Rating by Gender = `AVERAGE('Employee'[Rating])`
- Rating Count by Gender = `COUNT('Employee'[Rating])`
- Average Salary by Gender = `AVERAGE('Employee'[Salary])`
- Salary Count by Department and Region = `COUNT('Employee'[Salary])`
- Employees Below Minimum Salary = `COUNTX(FILTER('Employee', 'Employee'[Salary] < 90000), 'Employee'[Salary])`
- Bonus Amount = `IF(Max('Employee'[Rating]) > 3, MAX('Employee'[Salary]) * 0.1, 0)`
- Total Payment = `MAX('Employee'[Salary]) + [Bonus Amount]`

  
