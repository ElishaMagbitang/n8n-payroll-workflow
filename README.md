# n8n-payroll-workflow

**Payroll Workflow Automation using n8n**

This workflow automates the testing and validation of payroll processes. Instead of manually creating test data and checking results, it uses Google Sheets + n8n + Payroll System API to handle everything step by step.

Here’s what it does:

1. Reads test setup from Google Sheets

- Tester defines rules (number of employees, shifts, contracts, absences, holidays, overtime, etc.).

2. Generates test payroll data automatically

- Creates employee records, shifts, attendance, and transactions following the rules.

- Saves the generated dataset back to a sheet for visibility.

3. Imports generated data to the payroll system

- Sends the dataset through the payroll API (or via CSV if required).

4. Runs payroll processing

- Triggers the HRIS/Payroll system to calculate salaries, deductions, overtime, etc.

5. Extracts system output

- Retrieves the processed payroll results from the system.

- Stores the results into a separate Google Sheet.

6. Compares expected vs actual results

- n8n checks line by line whether the payroll output matches the generated dataset.

- Logs mismatches (e.g., incorrect deductions, missing overtime).

7. Reports & Alerts

- Writes a comparison report to a sheet.

- Sends an email alert if discrepancies are found.
