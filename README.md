# Data Collection and Preprocessing

## 1. Project Overview
This project uses the UCI Online Retail dataset to demonstrate data collection, data cleaning, data type correction, feature engineering, and validation using Python and Pandas.

## 2. Objective
To prepare a raw retail transaction dataset for further analysis by identifying and handling missing values, removing duplicate records, correcting data types, handling invalid prices, and creating useful features.

## 3. Dataset
- **Name:** Online Retail
- **Source:** UCI Machine Learning Repository
- **Original records:** 541,909
- **Original columns:** 8

Dataset source: https://archive.ics.uci.edu/dataset/352/online+retail

## 4. Tools and Technologies
- Python
- Google Colab
- Pandas
- NumPy
- GitHub

## 5. Data Preprocessing
1. Inspected the dataset structure and missing values.
2. Identified and removed 5,268 exact duplicate rows.
3. Converted `CustomerID` to a nullable integer type.
4. Replaced missing product descriptions with `Unknown product`.
5. Removed 2,512 records with zero or negative unit prices.
6. Preserved negative quantities because they may represent returns or cancellations.
7. Created new features for transaction amount, year, month, weekday, cancellation status, and negative-quantity status.
8. Validated the cleaned dataset for duplicates and invalid prices.

## 6. Final Results
- **Final records:** 534,129
- **Final columns:** 14
- **Duplicate rows remaining:** 0
- **Invalid prices remaining:** 0
- **Missing descriptions remaining:** 0
- **Missing CustomerID values:** 132,565

Missing customer IDs were preserved because the actual customer identities cannot be reliably inferred.

## 7. Feature Engineering
- `TransactionAmount`: Quantity multiplied by UnitPrice.
- `Year`: Year extracted from InvoiceDate.
- `Month`: Month extracted from InvoiceDate.
- `DayOfWeek`: Weekday name extracted from InvoiceDate.
- `IsCancellation`: Identifies invoice numbers beginning with `C`.
- `IsReturnQuantity`: Identifies negative quantities.

## 8. Project Files
- `Task1.ipynb`: Python preprocessing notebook.
- `cleaned_online_retail.csv`: Cleaned dataset, if provided separately or hosted elsewhere.
- `README.md`: Project documentation.

## 9. Conclusion
This project demonstrates a practical data preprocessing workflow. The resulting dataset has fewer duplicate and invalid-price records and includes additional features for future retail analysis.

## 10. Notes
Negative quantities were retained to avoid automatically discarding potential returns. The removal of zero or negative prices was performed for this project's positive-price transaction analysis. These decisions should be considered when interpreting results.
