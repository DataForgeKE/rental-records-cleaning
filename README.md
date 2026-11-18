# Rental Records Data Cleaning

This project uses Python, Pandas, NumPy, and a Jupyter notebook to clean and standardize a rental payment dataset containing 255 records and 12 fields. The workflow addresses inconsistent names, phone numbers, rent formats, dates, payment methods, and missing values. It also generates a profile report for exploratory data analysis.

## Dataset

The raw data is loaded from `rental_records_raw.csv`. The dataset contains the following columns:

- `tenant_id`
- `billing_month`
- `tenant_name`
- `phone`
- `unit`
- `monthly_rent`
- `amount_paid`
- `payment_date`
- `payment_method`
- `mpesa_code`
- `reported_balance`
- `status`

## Cleaning Performed

- Generates an HTML data profile report.
- Standardizes tenant names using title case.
- Removes phone-number spaces and converts Kenyan numbers to `+254` format.
- Marks invalid or missing phone numbers as `Invalid Phone` or `Missing Number`.
- Converts unit names to uppercase.
- Removes KES/KSh text and commas from monthly rent values.
- Converts shorthand rent values such as `8k` to numeric values.
- Converts paid amounts to numeric values.
- Parses mixed payment-date formats.
- Standardizes payment methods, M-Pesa codes, and payment statuses.
- Converts `NAN` text values to missing values.
- Fills missing monthly rent values using the tenant name when available.
- Exports the cleaned records to CSV.

## Project Files

- `clean_rental_records.ipynb` - Complete cleaning and profiling workflow.
- `clean_rental_records.csv` - Cleaned rental records.

## Requirements

- Python 3
- Pandas
- NumPy
- Jupyter Notebook or JupyterLab
- The `data_profiling` package used to generate the profile report

Install the core packages with:

```bash
pip install pandas numpy jupyter
```

## Usage

1. Place `rental_records_raw.csv` in the project input location.
2. Update the input and output paths in `clean_rental_records.ipynb` if necessary.
3. Run the notebook from top to bottom.
4. Open the generated HTML profile report and inspect `clean_rental_records.csv`.

The notebook exports the cleaned dataset to:

```text
C:\Users\1040 G3\OneDrive\Documents\Clean data\clean_rental_records.csv
```

For portability, replace absolute paths with paths relative to the project folder.

## Output

The cleaned CSV preserves the 12-field rental record structure and applies consistent formatting for names, units, phone numbers, currency values, dates, and payment statuses. Missing or invalid values remain identifiable rather than being silently discarded.
