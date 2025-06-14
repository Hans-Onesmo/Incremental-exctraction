# ETL Extract Hans Onesmo
This Jupyter notebook implements a robust ETL (Extract, Transform, Load) pipeline for processing school attendance data, with an emphasis on efficient incremental extraction. The system is optimized to manage daily attendance records while reducing redundant data processing.
# Key features:
The pipeline features incremental data loading, processing only new records based on timestamps, and batch processing, extracting data in fixed-size chunks (default: 50 records per run). It includes automatic setup to generate sample data if none exists and implements progress tracking using last_extraction.txt to resume processing from the last extraction point. Additionally, it incorporates robust error handling to gracefully manage missing files and corrupt data.
# Tools:
Python (with Pandas for data manipulation and analysis, and datetime libraries for managing dates, times, and time-based operations) is essential for building ETL (Extract, Transform, Load) workflows. The datetime and timedelta modules play a crucial role in handling temporal data and enabling time-based processing tasks.
# Run codes
Install the required packages using pip install pandas, clone the repository using git clone, launch the Jupyter Notebook, and execute all the cells in sequence.
# Data
The notebook generates synthetic data (school_attendance.csv), simulating daily attendance for 5 schools over a 3-month period, excluding weekends, with realistic daily variations in enrollment and absences.

# School Attendance ETL Pipeline

# Overview
This project implements a complete ETL (Extract, Transform, Load) pipeline for school attendance data. It processes both full datasets and incremental updates, applying data cleaning, enrichment, and structural transformations to prepare the data for analysis.

# Features
Full Data Extraction: Loads complete historical dataset
Incremental Extraction: Efficiently processes only new/updated records
Data Transformations:
  - Cleaning: Handles missing values, removes duplicates
  - Enrichment: Adds calculated fields (attendance rate, weekday, school level)
  - Structural: Standardizes column names and data types

# Transformation Details
Cleaning Transformations
Handles missing values by:
Using median for enrollment numbers
Recalculating present/absent counts when inconsistent
Removes duplicate records for same school/date
Ensures no negative values in numeric fields
Enrichment Transformations
Calculates attendance rate percentage
Adds weekday name (Monday-Sunday)
Categorizes schools by level based on DBN code:
'M': Middle School
'K': Elementary School
'X': High School

# Structural Transformations
Standardizes column names (spaces to underscores)
Converts data types:
School DBN to string
Dates to datetime objects
Reorders columns logically

# Output Files
transformed_full.csv:
Contains all historical data with transformations applied
Columns: School_DBN, School_Level, Date, Weekday, Enrolled, Present, Absent, Attendance_Rate, Released, last_updated

# transformed_incremental.csv:
Contains only new/updated records since last run
Same schema as full transformed file

# Maintenance
last_extraction.txt: Automatically updated after each incremental run
The system maintains data consistency between full and incremental loads
