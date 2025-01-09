# Finance Tracker Project

## Overview

The **Finance Tracker** project is a Python-based application designed to help individuals manage and track their financial activities. It enables users to input, store, and analyze their expenses and income, providing insights into their spending patterns and savings.

---

## Key Features

- **Data Entry**: Allows users to input financial transactions.
- **Data Storage**: Saves financial records in a structured CSV format.
- **Analysis and Visualization**: Provides insights into income, expenses, and trends.
- **User-Friendly Design**: Clean and modular code structure for ease of use and extension.

---

## Project Files

### 1. `data_entry.py`
This module is responsible for handling user inputs and storing financial transactions in the CSV file.

#### Key Components:
- **Transaction Input**:
  - Prompts the user for details such as date, category, amount, and description.
- **CSV Writing**:
  - Appends transaction data to `finance_data.csv`.

#### Example Code:
```python
import csv

def add_transaction(date, category, amount, description):
    with open('finance_data.csv', mode='a', newline='') as file:
        writer = csv.writer(file)
        writer.writerow([date, category, amount, description])
```

### 2. `finance_data.csv`
This file serves as the database for storing financial records. Each row contains:
- **Date**: When the transaction occurred.
- **Category**: Type of transaction (e.g., Food, Salary, Entertainment).
- **Amount**: The monetary value of the transaction.
- **Description**: Additional details about the transaction.

### 3. `main.py`
This script integrates the functionality of data entry and provides options for analyzing financial data.

#### Key Components:
- **Menu Options**:
  - Add a new transaction.
  - View financial summaries.
- **Data Analysis**:
  - Reads data from `finance_data.csv`.
  - Computes total income, expenses, and savings.
- **Visualization**:
  - Generates bar charts and pie charts for category-wise analysis using Matplotlib.

#### Example Code:
```python
import pandas as pd
import matplotlib.pyplot as plt

def analyze_data():
    data = pd.read_csv('finance_data.csv')
    summary = data.groupby('Category')['Amount'].sum()
    summary.plot(kind='pie', autopct='%1.1f%%')
    plt.title('Category-wise Expense Distribution')
    plt.show()
```

---

## How to Run the Project

### Step 1: Install Dependencies
Ensure you have Python installed. Then, install required libraries:
```bash
pip install pandas matplotlib
```

### Step 2: Input Transactions
Run the `data_entry.py` script to input transactions:
```bash
python data_entry.py
```

### Step 3: Analyze Data
Run the `main.py` script to view analysis and visualizations:
```bash
python main.py
```

---

## Future Enhancements

- **User Authentication**: Add login/logout functionality.
- **Enhanced Visualization**: Include more interactive charts using Plotly or Dash.
- **Budgeting Features**: Allow users to set and track budgets.
- **Cloud Integration**: Store data securely on the cloud for cross-device access.

---

## Conclusion
The **Finance Tracker** project is a simple yet powerful tool for personal financial management. With its modular design and focus on user-friendly features, it provides valuable insights into spending habits and savings potential. Whether you're managing personal finances or planning budgets, this project is a great starting point.

---

**Happy Tracking!**

