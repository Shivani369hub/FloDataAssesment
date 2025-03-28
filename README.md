# Sales Orders Processing System

## Overview
This project is designed to process sales orders, clean and store the data in an SQLite database, enrich orders with location data using IP addresses, and generate sales reports.

## Features
- Cleans and loads sales order data from CSV files.
- Stores data in an SQLite database.
- Fetches location details using IP addresses from an external API.
- Caches IP-based location data to optimize performance.
- Generates quarterly sales reports in Excel format.

## Installation
### Step 1: Create a Virtual Environment
Run the following command to create a virtual environment:
```bash
python -m venv venv
```

Activate the virtual environment:
- **Windows**
  ```bash
  venv\Scripts\activate
  ```

### Step 2: Install Required Packages
Install the necessary dependencies using:
```bash
pip install -r requirements.txt
```

## Usage
### 1. Running the Main File
To process the sales orders and generate reports, open the Jupyter Notebook (`main.ipynb`) in VS Code and run all the cells sequentially.

This will:
- Generate the enriched orders file (`enriched_orders.csv`).
- Create a state-wise quarterly sales report in Excel format.

### 2. Generating State Sales Reports
When generating a state sales report, ensure the parameters are correctly set.

#### Example:
To generate a report for Illinois (IL) in 2024 and save it as `IL_state_sales_report_2024.xlsx`, use:
```python
main.generate_sales_report(conn, 'IL', 2024, 'IL_state_sales_report_2024.xlsx')
```

## File Descriptions
- `main.py` - Contains all core functions for processing sales orders.
- `orders_file.csv` - Sample input file containing sales order data.
- `ip_addresses_test.csv` - Sample input file containing IP addresses for orders.
- `requirements.txt` - Lists all required Python packages.
- `sales_orders.db` - SQLite database storing order and IP-related data.
- `IL_state_sales_report_2024.xlsx` - Generated quarterly sales report.

## Dependencies
The project requires the following Python libraries:
```
pandas
sqlite3
requests
openpyxl
numpy
```
Ensure all dependencies are installed using `requirements.txt` before running the scripts.

## Notes
- Make sure your CSV files have proper column names as expected by the scripts.
- Ensure an active internet connection for fetching IP location data.
- The database file `sales_orders.db` will be created in the project directory if it does not exist.

## License
This project is licensed under the MIT License.

## Author
Shivani

