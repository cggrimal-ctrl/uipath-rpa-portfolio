# Invoice Processing Automation

## Overview

This project automates the processing and validation of digital PDF invoices using UiPath Studio.

The automation extracts invoice information, applies business validation rules, detects duplicate invoice numbers, and generates an Excel report containing accepted and rejected invoices.

This project is part of my UiPath RPA Developer Portfolio.

## Business Scenario

A company receives multiple PDF invoices from different suppliers. The automation processes these documents and consolidates their information into a structured report, reducing manual data entry and improving consistency.

## Key Features

- Batch processing of PDF invoices
- Text extraction from digital PDFs
- Invoice data validation
- Argentine CUIT format validation
- Duplicate invoice detection
- Rejection reason tracking
- Excel report generation
- Modular workflow design

## Workflow

The automation follows this process:

1. Retrieve PDF files from the input folder.
2. Extract invoice information.
3. Validate the extracted data.
4. Check whether the invoice number has already been processed.
5. Determine the invoice status.
6. Add the invoice information to the reporting DataTable.
7. Generate the final Excel report.

## Business Rules

| Rule | Description |
|---|---|
| Invoice number | Must not be empty |
| Supplier CUIT | Must follow the expected format and validation rules |
| Invoice date | Must be valid |
| Invoice amount | Must be greater than zero |
| Duplicate invoices | Duplicate invoice numbers are rejected |
| Rejected invoices | Must include a rejection reason |

## Technology Stack

- UiPath Studio
- UiPath PDF Activities
- UiPath Excel Activities
- Visual Basic .NET expressions
- DataTables and Collections
- Git and GitHub

## Project Structure

```text
InvoiceProcessing/
├── Main.xaml
├── project.json
├── Workflows/
│   ├── Initialization/
│   ├── Processing/
│   └── Reporting/
├── Data/
│   ├── Input/
│   ├── Output/
│   └── Config/
└── Documentation/
```

## Test Scenarios

The automation was tested using fictional PDF invoices.

| Test Case | Expected Result |
|---|---|
| Valid invoice | Accepted |
| Second valid invoice | Accepted |
| Duplicate invoice number | Rejected |
| Missing supplier CUIT | Rejected |

## Output

The automation generates an Excel report containing:

- Invoice number
- Supplier name
- Supplier CUIT
- Invoice date
- Currency
- Net amount
- VAT amount
- Total amount
- Invoice status
- Rejection reason

## Limitations

- Currently supports digital PDFs with selectable text.
- Scanned invoices requiring OCR are not included in this version.
- Test invoices are fictional and intended exclusively for automation testing.

## Future Improvements

- OCR support for scanned invoices
- Configuration-driven validation rules
- Enhanced exception handling
- Integration with UiPath Orchestrator
- Automated email notifications
- Additional unit and workflow tests

## Author

UiPath RPA Developer Portfolio

This project demonstrates practical RPA development, workflow modularization, data validation, exception handling, and reporting.