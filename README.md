# Python Data Analysis Capstone

A Python-based data analysis project focused on data creation, cleaning, transformation, dataset merging, business-rule implementation, aggregation, and CSV reporting using pandas and NumPy.

## Project Overview

This capstone demonstrates an end-to-end data preparation and analysis workflow using three related datasets:

- Employee data
- Seniority data
- Project data

The datasets are created as pandas DataFrames, exported to CSV files, transformed through multiple business rules, merged using employee IDs, and used to produce consolidated reporting outputs.

## Tools & Technologies

- Python
- pandas
- NumPy
- Jupyter Notebook
- CSV

## Dataset Structure

### Employee Dataset
Contains:

- Employee ID
- Name
- Gender
- City
- Age

### Seniority Dataset
Contains:

- Employee ID
- Designation Level

### Project Dataset
Contains:

- Employee ID
- Project
- Cost
- Status

Project statuses include:

- Finished
- Ongoing
- Failed

## Analysis Workflow

### 1. DataFrame Creation & CSV Export

Created Employee, Seniority, and Project DataFrames using pandas and exported them as CSV files.

### 2. Missing Value Handling

Identified missing project cost values and replaced them using a running average calculated from previously available cost values.

### 3. Name Transformation

Split the employee `Name` column into:

- First Name
- Last Name

The original `Name` column was then removed.

### 4. Dataset Merging

Merged the Employee and Seniority datasets using `ID`, followed by merging the Project dataset using the same employee ID.

This produced a consolidated dataset containing employee, seniority, and project information.

### 5. Bonus Calculation

Applied a 5% bonus to projects with a `Finished` status.

Projects with other statuses received a bonus value of zero.

### 6. Employee Demotion Rule

Employees associated with failed projects had their designation level reduced by 1.

Records with designation levels above 4 were excluded from the resulting dataset.

### 7. Gender-Based Titles

Added titles to employee first names based on gender:

- `Mr.` for male employees
- `Mrs.` for female employees

The Gender column was then removed.

### 8. Age-Based Promotion

Employees older than 29 years were promoted by reducing their designation level by 1.

### 9. Total Project Cost

Calculated the total project cost for each employee using `groupby()` and aggregation.

A separate reporting DataFrame was created containing:

- Employee ID
- First Name
- Total Cost

This output was exported as `TotalProjCost.csv`.

### 10. City-Based Filtering

Filtered the consolidated dataset to identify employee records where the city name contains the letter `o`, using a case-insensitive condition.

## Generated CSV Files

The notebook generates the following CSV files during execution:

```text
employee.csv
seniority.csv
project.csv
final.csv
TotalProjCost.csv
