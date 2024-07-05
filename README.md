# Utilities

This repository contains a collection of useful scripts and functions for general utility purposes. The codes included offer various functionalities such as data cleaning, integration with Google Sheets, and more.

## Features
- **Integration with Google Sheets**: Easily upload and share files on Google Drive.
- **Data Cleaning**: Functions to clean and preprocess your data.

## Functions and Classes

### `def extrair_valores(registro, chave):`
Extract values from a record based on a key.

### `def encrypt_column(*columns) -> str:`
Encrypts specified columns.

### `def get_year_month(df, ref_date):`
Extracts year and month from a dataframe based on a reference date.

### `def clean_symbols_column(column_name):`
Cleans symbols from a specified column.

### `def fill_blank_column(col_name, value_to_fill):`
Fills blank values in a specified column with a given value.

### `class Sender:`
Handles file upload and sharing on Google Drive.

#### Methods:
- `__init__(self)`: Initializes the Sender class and sets up the Google Drive service.
- `set_drive_service(self)`: Configures the Google Drive service with credentials.
- `send_file(self, drive_folder_id, filepath)`: Uploads a file to a specified Google Drive folder and returns the file ID.
- `share_file(self, id_file, emails)`: Shares a file with specified email addresses.

### `def create_and_send_df_from_spark(spark_df, csv_path):`
Converts a PySpark DataFrame to a pandas DataFrame, saves it as a CSV file, and returns the DataFrame.

### `def upload_and_share_file(drive_folder_id, email_to_share, csv_path):`
Uploads a CSV file to Google Drive and shares it with a specified email address.

## Usage

### Setting Up Google Drive Integration
1. Ensure you have a valid `credentials.json` file for Google Drive API access.
2. Place the `credentials.json` file in the appropriate path specified in your code.

### Example Usage

```python
# Example of how to use some functions in this repository

# Clean symbols from a column
cleaned_column = clean_symbols_column("example_column")

# Encrypt specified columns
encrypted_columns = encrypt_column("column1", "column2")

# Upload and share a file on Google Drive
drive_folder_id = "your_drive_folder_id"
email_to_share = "example@example.com"
csv_path = "/path/to/your/csvfile.csv"

upload_and_share_file(drive_folder_id, email_to_share, csv_path)
