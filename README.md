# DSA-Project-Documentation-2
Palmora Group HR Analysis

## Project Title: Palmora Group HR Analysis for Gender Distribution, Salary and Performance Insights

### Project Overview
This project analyzes employee data to gain insights into gender distribution, performance ratings, salary structures, bonus allocation, and regional differences. The goal is to uncover trends that can support better HR decision-making

### Data Source 
The datasets used for this project was provided by The Incubator Hub as an Excel files titled "Palmoria Group emp-data.csv" and "Palmoria Group Bonus Rules.xlsv". It consists of Name, Gender, Department, Region, Salary, and Rating.

### Tools Used
Power BI [Download Here]()
- Data Collection
- Data Cleaning
  - Power Query for Extracting, Transforming and Loading Data (ETL)
  - DAX to create custom columns and measures
- Visualization 
  - Roport View for visualization and analysis


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
   - Card: Gender Count
   - Card: Gender Percentage
   - Slicer: Location
    
2. Performance Ratings by Gender: Evaluates fairness in scores
   - Clustered column chart: Count of ratings by gender
   - Card: Average rating by gender
   - Slicer: Gender
    
3. Salary Structure & Pay Gap: Highlights pay disparities across teams
   - Scatter chart: Salary vs. Gender
   - Cluster Bar chart: Average salary by department
   - Card: Average Salary by Gender
   - Card: Salary Count by Department
   - Slicer: Location

4. Minimum Salary Threshold Analysis: Identifies underpaid regions or roles
   - Cluster Column Chart: Salary grouped in ₦10,000 bands
   - Cluster Bar Chart: Count of employees earning below ₦90,000

5. Bonus Calculation: Automates bonus logic and performance rewards 
   - Cluster Bar chart: Total bonus payout per region
   - Table: Employee-level bonus breakdown
   - Card: Total Bonus Paid Out
   - Card: Total Amount to be Paid out
   - Slicers: Rating, Gender and Location
 
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

### Recommendations
- Improve gender balance across departments
- Review salary gaps, especially by gender
- Apply bonuses fairly to high performers
- Minimum pay in low-income regions should be raised.
- Track ratings to guide promotion decisions

### Limitations
- Some ratings were missing or unclear.
- Some employee ratings were missing or labeled "Not Rated".

### References
- Sample dataset from training program
- Analysis done using Power BI

### Project Screenshots
Below are screenshots showing visuals created in Power BI Report View:

![Alt text](https://github.com/Debbierise001/DSA-Project-Documentation-2/blob/main/PowerBI%201_023923.PNG)

![Alt text](https://github.com/Debbierise001/DSA-Project-Documentation-2/blob/main/PowerBI%202_023925.PNG)

![Alt text](https://github.com/Debbierise001/DSA-Project-Documentation-2/blob/main/PowerBI%203_023927.PNG)

![Alt text](https://github.com/Debbierise001/DSA-Project-Documentation-2/blob/main/PowerBI%204_023928.PNG)
