# DSA-Project-Documentation-2
Palmora Group HR Analysis

## Project Title: Palmora Group HR Analysis for Gender Distribution, Salary, and Performance Insights

### Project Overview
This project analyzes employee data to gain insights into gender distribution, performance ratings, salary structures, bonus allocation, and regional differences. The goal is to uncover trends that can support better HR decision-making.

### Data Source 
The datasets used for this project was provided by The Incubator Hub as Excel files titled "Palmoria Group emp-data.csv" and "Palmoria Group Bonus Rules.xlsx", which consist of Name, Gender, Department, Region, Salary, and Rating.

### Tools Used
Power BI [Download Here](https://github.com/Debbierise001/DSA-Project-Documentation-2/raw/main/Palmora%20Group%20HR%20Analysis.pbix)
- Data Collection
- Data Cleaning
  - Power Query for Extracting, Transforming, and Loading Data (ETL)
  - DAX to create custom columns and measures
- Visualization 
  - Report View for visualization and analysis
  - Model View to connect and disconnect relationships between the tables


### Data Cleaning & Preparation
- Removed rows with missing salary and department.
- Replaced null and empty gender rows with "Unspecified".
- Created conditional columns to sort Gender and Ratings as values.
- Created Salary Band using conditional column logic
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
    
3. Salary Structure & Pay Gap: Highlights pay gaps across teams
   - Scatter chart: Salary vs. Gender
   - Cluster Bar chart: Average salary by department
   - Card: Average Salary by Gender
   - Card: Salary Count by Department
   - Slicer: Location

4. Minimum Salary Threshold Analysis: Identifies underpaid regions or roles
   - Cluster Column Chart: Salary grouped in $10,000 bands
   - Cluster Bar Chart: Count of employees earning below $90,000

5. Bonus Calculation: Automates bonus logic and performance rewards 
   - Cluster Bar chart: Total bonus payout per region
   - Table: Employee-level bonus breakdown
   - Card: Total Bonus Paid Out
   - Card: Total Amount to be Paid out
   - Slicers: Rating, Gender, and Location
 
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
- Improve gender balance across departments.
- Review salary gaps, especially by gender.
- Apply bonuses fairly to high performers.
- Minimum pay in low-income regions should be raised.
- Track ratings to guide promotion decisions.

### Limitations
- Some employee ratings were missing or labeled "Not Rated".

### References
- Sample dataset from the training program
- Analysis done using Power BI

### Project Screenshots
Below are screenshots showing visuals created in Power BI Report View:

![PowerBI 1](https://github.com/Debbierise001/DSA-Project-Documentation-2/raw/main/PowerBI%201.PNG)

![PowerBI 2](https://github.com/Debbierise001/DSA-Project-Documentation-2/raw/main/PowerBI%202.PNG)

![PowerBI 3](https://github.com/Debbierise001/DSA-Project-Documentation-2/raw/main/PowerBI%203.PNG)

![PowerBI 4](https://github.com/Debbierise001/DSA-Project-Documentation-2/raw/main/PowerBI%204.PNG)
