# Transaction-Data-Anomaly-Detection

## Overview
This project involves generating synthetic transaction data for the month of March 2024, identifying anomalies in the data, and exporting the results. The data represents different environments and content types, with trade and quote counts for each minute within specific time periods.

## Project Structure
- generate_data_march1_30.ipynb: Script to generate synthetic transaction data for March 1-30, 2024.
- generate_data_march31.ipynb: Script to generate synthetic transaction data for March 31, 2024, with some manually modified trade and quote counts.
- detect_anomalies.py: Script to detect anomalies in the transaction data for March 31, 2024.

Generated CSV files:
* transactions_march.csv: Data for March 1-30, 2024.
* transactions_march31.csv: Data for March 31, 2024.
* anomalies.csv: Full dataset for March 31, 2024, with anomalies marked.
* anomaly_rows.csv: Only the rows from March 31, 2024, that contain anomalies.

Data Generation:

generate_data_march1_30.py
This script generates synthetic data for each minute between 6:30 AM and 1:30 PM from March 1-30, 2024. The data includes:

* timestamp: Unix timestamp for each minute.
* content name: One of onl, fut, otc, wth.
* environment: One of qa, pt, dr, pr.
* lineID: A unique identifier specific to each content name.
* trade count: Random integer between 0 and 50.
* quote count: Random integer between 0 and 50.
  
The trade and quote counts are consistent across different environments for the same timestamp, content name, and lineID.

generate_data_march31.py
This script generates similar synthetic data for March 31, 2024. Additionally, some trade and quote counts are manually modified to introduce anomalies.

Anomaly Detection:

detect_anomalies.py
This script detects anomalies in the data generated for March 31, 2024. It:

Reads transactions_march31.csv.
Groups the data by lineID and checks for discrepancies in trade count and quote count within each group.
Marks rows with anomalies.
Exports the full dataset with anomaly markings to anomalies.csv.
Extracts rows containing anomalies and saves them to anomaly_rows.csv.
Usage
Generate Data for March 1-30, 2024:

bash
Copy code
python generate_data_march1_30.py
Generate Data for March 31, 2024:

bash
Copy code
python generate_data_march31.py
Detect Anomalies in March 31 Data:

bash
Copy code
python detect_anomalies.py
Files
transactions_march.csv: Generated data for March 1-30, 2024.
transactions_march31.csv: Generated data for March 31, 2024.
anomalies.csv: Data for March 31, 2024, with anomalies marked.
anomaly_rows.csv: Rows from March 31, 2024, containing anomalies.
Dependencies
pandas: For data manipulation and analysis.
To install the required packages, use:

bash
Copy code
pip install pandas
Author
[Your Name]

License
This project is licensed under the MIT License - see the LICENSE file for details.
