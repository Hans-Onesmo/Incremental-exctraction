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
