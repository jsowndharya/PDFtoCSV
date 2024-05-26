This script reads a specific page from a PDF file and converts the second table on that page into a CSV file. It uses the tabula library in Python to handle the PDF parsing and conversion.

Prerequisites
Make sure you have tabula-py installed. You can install it using pip:

sh
Copy code
pip install tabula-py
Usage
Modify Paths: Ensure the paths to the input PDF file and the output CSV file are correctly specified in the script.

Run the Script: Execute the script to convert the second table on page 2 of the specified PDF file to a CSV file.

python
Copy code
import tabula

# Specify the path to your PDF and the desired output path for the CSV
pdf_path = r'C:/Users/sownd/Desktop/Python/ast_sci_data_tables_sample.pdf'
csv_output_path = r'C:/Users/sownd/Desktop/Python/table1.csv'

# Read the specified page from the PDF
dfs = tabula.read_pdf(pdf_path, pages=2, multiple_tables=True)

# Check if multiple tables were read
if dfs and len(dfs) > 1:
    # Convert the second table into a CSV file
    dfs[1].to_csv(csv_output_path, index=False)
else:
    print("The specified page does not contain multiple tables or an error occurred.")
Example
Given a PDF file located at C:/Users/sownd/Desktop/Python/ast_sci_data_tables_sample.pdf, this script will extract the second table found on page 2 and save it as a CSV file at C:/Users/sownd/Desktop/Python/table1.csv.

Notes
The script assumes the PDF contains multiple tables on the specified page.
Modify the pages parameter if you need to read a different page.
Ensure the paths to the PDF and CSV files are valid and accessible.

