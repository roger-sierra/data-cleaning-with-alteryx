# World Layoffs Data Cleaning Workflow

## Overview

This project involves cleaning and processing a dataset containing global layoffs information. The data comes from a CSV file named `world_layoffs.csv`. The goal of this workflow is to prepare the data for further analysis by handling duplicates, null values, formatting issues, and other inconsistencies.

## Workflow Description

The workflow performs the following key steps:

1. **Input Data:**
   - The workflow begins by reading the `world_layoffs.csv` file containing the raw data.
   - **Tool Used:** *Input Data Tool*

2. **Remove Duplicates:**
   - Duplicates in the dataset are identified and removed to ensure unique records.
   - **Tool Used:** *Unique Tool*

3. **Replace "NULL" Strings:**
   - Strings labeled as "NULL" are replaced with actual null values to standardize missing data representation.
   - **Tool Used:** *Multi-Field Formula Tool*

4. **Remove Leading and Trailing Whitespace:**
   - Leading and trailing whitespace characters in text fields are removed to ensure consistency across entries.
   - **Tool Used:** *Data Cleansing Tool*

5. **Remove Trailing Punctuation:**
   - The workflow removes trailing punctuation from the "Country" column to ensure uniform formatting.
   - **Tool Used:** *Data Cleansing Tool*
  
6. **Remove Duplicate "Crypto" Industries:**
   - Entries labeled as "Crypto", "CryptoCurrency", "Crypto Currency", etc. in the "Industry" column are consolidated into one "Crypto" industry.
   - **Tool Used:** *Formula Tool*

7. **Convert Date Format:**
   - The "Date" column is converted to a datetime format, and the original column is replaced with the newly formatted version.
   - **Tool Used:** *DateTime Tool/Select Tool*

8. **Convert Blanks to Nulls in "Industry" Column:**
   - Any blanks in the "Industry" column are converted to null values, ensuring consistent handling of missing data.
   - **Tool Used:** *Formula Tool*

9. **Replace Null Values in "Industry" Column:**
   - Null values in the "Industry" column are replaced with corresponding values from other rows where possible, filling in gaps in the data.
   - **Tool Used:** *Multi-Row Formula Tool*

10. **Filter on Null Values:**
    - The workflow filters records where the "Total Laid Off" and "% Laid Off" columns contain null values, preparing the dataset for final output.
    - **Tool Used:** *Filter Tool*

11. **Output Data:**
    - The cleaned data is outputted as `layoffs_finalized`, ready for analysis.
    - **Tool Used:** *Output Data Tool*

## Workflow Image

Below is a visual representation of the data cleaning and processing workflow:

![image](https://github.com/user-attachments/assets/a036dd76-eef4-4799-9894-c9da8f56a82c)

## How to Run the Workflow

1. **Requirements:**
   - Alteryx Designer (version 2020.1 or higher)
   
2. **Steps to Run:**
   - Clone this repository to your local machine.
   - Open the `workflow.yxmd` file in Alteryx Designer.
   - Ensure the `world_layoffs.csv` file is placed in the correct directory as specified in the input tool configuration.
   - Run the workflow to process the data.

3. **Output:**
   - The final cleaned dataset will be outputted as `layoffs_finalized`.csv.
