# CSV Data Validator

A GitHub Pages web application for analyzing CSV data quality with automated validation rules.

## Features

- **CSV File Upload**: Drag and drop or click to upload CSV files
- **Interactive Data Table**: View your data in a clean, sortable table format
- **Color-Coded Validation**: Visual indicators for data quality issues
  - White: Valid data (no issues detected)
  - Yellow: Moderate doubt (suspicious patterns)
  - Red: Doubtful (likely invalid data)

## Validation Rules

### 1. Date Validation
- Detects common date formats (MM/DD/YYYY, YYYY-MM-DD, etc.)
- Flags invalid dates as doubtful (red)
- Flags dates outside reasonable ranges (1900-2100) as moderate doubt (yellow)
- Flags dates more than 1 year in the future as moderate doubt (yellow)

### 2. Integer Fraud Detection
- **Benford's Law Analysis**: Flags numbers with unusual first digit distributions
- **Pattern Detection**: Identifies suspicious patterns like:
  - All identical digits (11111, 99999) - flagged as doubtful (red)
  - Sequential patterns (12345, 54321) - flagged as moderate doubt (yellow)
  - High digit repetition - flagged as moderate doubt (yellow)
- **Round Number Bias**: Flags round numbers that may indicate estimation rather than actual measurement

## Usage

1. Open the web application
2. Click "Choose File" or drag a CSV file to upload
3. View the color-coded table with validation results
4. Hover over colored cells to see detailed validation reasons
5. Check the validation summary at the bottom for overall data quality statistics

## Sample Data

A `sample_data.csv` file is included to test the application with various data quality issues including:
- Invalid dates
- Future dates
- Employee IDs with suspicious digit patterns
- Round salary numbers

## Technical Implementation

- Pure HTML5, CSS3, and JavaScript (no dependencies)
- Client-side processing (no data sent to servers)
- Responsive design for mobile and desktop
- CSV parsing with proper quote handling
- Extensible validation rule system

## GitHub Pages

This application is designed to work seamlessly with GitHub Pages. Simply push to your repository and enable Pages to deploy.

## Browser Support

Supports all modern browsers with ES6+ features including:
- Chrome 60+
- Firefox 55+
- Safari 12+
- Edge 79+