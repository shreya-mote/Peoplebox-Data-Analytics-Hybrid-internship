# Peoplebox-Data-Analytics-Hybrid-internship
#Historical Data Transformation Objective: Transform current employee data from a columnar format into a historical, row-based versioning format suitable for database storage using Python. 
Approach and Assumptions:

Reading the Data: The code starts by reading the input CSV file named "input (3).csv" using pandas' read_csv function.

Sorting Data: The data is sorted based on the 'Employee Code' and 'Date of Joining' to ensure a chronological order for each employee's records.

Effective Date and End Date: The 'Effective Date' is determined as the 'Date of Joining' for each employee's next record. If it is the last record, the current date is considered. The 'End Date' is set to one day before the 'Effective Date' of the next record or '2100-01-01' for the last record.

Last Compensation: The 'Last Compensation' column is created by shifting the 'Compensation' column by one row for each employee.

Choosing Compensation: Among the 'Compensation', 'Compensation 1', and 'Compensation 2' columns, the latest value is chosen for the 'Compensation' column.

Tenure in Org: This column is calculated as the difference between the 'Effective Date' and the 'Date of Joining', converted to years.

Variable Pay: A new column named 'Variable Pay' is created with initial values set to None (NaN).

Last Pay Raise Date: This column is created by shifting the 'Compensation 1 date' column by one row for each employee.

Performance Rating: The maximum value between 'Review 1' and 'Review 2' is chosen for each employee as their 'Performance Rating'.

Engagement Score: The maximum value between 'Engagement 1' and 'Engagement 2' is chosen for each employee as their 'Engagement Score'.

Selecting Output Columns: Only the desired columns for the output are selected.

Saving the Transformed Data: The transformed data is saved to a new CSV file named "output.csv" in the specified directory.

Assumptions:

The input CSV file is correctly formatted and contains the expected columns.
The 'Date of Joining', 'Compensation date', 'Compensation 1 date', 'Compensation 2 date', 'Review 1 date', 'Review 2 date', 'Engagement 1 date', and 'Engagement 2 date' columns are in a consistent date format.
The missing values in the 'Variable Pay' column are acceptable and can be handled downstream.
The input data contains records for multiple employees, and the transformations are applied on a per-employee basis.
