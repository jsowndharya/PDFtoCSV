# PDF to CSV Conversion Script

This script uses the tabula-py library to extract tables from a specified page of a PDF file and convert them into a CSV file.

# Prerequisites
Ensure you have tabula-py installed. You can install it using pip:

# pip install tabula-py

Usage
Specify Paths:

pdf_path: Path to your PDF file.
csv_output_path: Desired output path for the CSV file.

# Script Explanation:

The script reads tables from page 2 of the specified PDF file.
If multiple tables are present, it converts the second table into a CSV file.
# Code Example

import tabula

# Specify the path to your PDF and the desired output path for the CSV
pdf_path = r'C:/Users/sownd/Desktop/Python/ast_sci_data_tables_sample.pdf'
csv_output_path = r'C:/Users/sownd/Desktop/Python/table1.csv'

# Read the specified page from the PDF
dfs = tabula.read_pdf(pdf_path, pages=2, multiple_tables=True)

# Notes
Make sure the PDF file path and CSV output path are correct and accessible.
This script assumes there are multiple tables on the specified PDF page. If not, it will notify you of the issue.
