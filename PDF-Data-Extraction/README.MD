# 📄 PDF Data Extraction

## 🧭 Overview
This UiPath workflow automates the extraction of structured invoice data from a folder of PDF files and consolidates it into a clean Excel report. It intelligently distinguishes between native and scanned PDFs, applying OCR only when necessary, and uses regular expressions to pinpoint key financial fields. Designed for reliability and scalability, this solution eliminates manual data entry, reduces errors, and accelerates downstream reporting.

Whether you're processing a handful of invoices or scaling to hundreds, this automation ensures consistent output and seamless integration with your broader analytics or audit workflows.

https://github.com/user-attachments/assets/800a354c-eb2f-4f4e-8c08-4342883be3b0

---

## 🎯 Objectives
- Automate extraction of invoice data from PDFs  
- Handle both scanned and native PDFs with conditional logic  
- Export extracted data to a structured Excel sheet

---


## ✨ Key Features
- ✅ Dynamic folder iteration for batch processing  
- ✅ OCR fallback for scanned PDFs  
- ✅ Regex-based data extraction for invoice number, date, and total  
- ✅ Real-time logging for process transparency  
- ✅ Consolidated output in Excel format

---


## 🛠️ Tools & Technologies
- UiPath Studio  
- UiPath.PDF.Activities  
- UiPath.Excel.Activities  
- Tesseract OCR Engine  
- Regular Expressions (`System.Text.RegularExpressions`)

---


## 🔄 Workflow Model/Structure
- **Build Data Table**  
  Initializes schema for storing extracted data  

- **For Each File in Folder**  
  Iterates through all PDFs  
  - `Assign`: Captures full file path  
  - `If PDF is Scanned`:  
    - `Log Message`: "Scanned PDF File"  
    - `Read PDF Text`: Attempts native text extraction  
    - `If Empty`:  
      - `Log Message`: "Reading PDF With OCR"  
      - `Read PDF With OCR`: Uses OCR to extract text  
    - `Else`:  
      - `Log Message`: "Reading PDF Without OCR"  

- **Multiple Assign**  
  Extracts data using Regex:  
  ```vbnet
  strInvoiceNumber = System.Text.RegularExpressions.Regex.Match(strPDFText, "Invoice Number: (\d+)").Groups(1).Value  
  strInvoiceDate = System.Text.RegularExpressions.Regex.Match(strPDFText, "Invoice Date: (\d{2}/\d{2}/\d{4})").Groups(1).Value  
  strInvoiceTotal = System.Text.RegularExpressions.Regex.Match(strPDFText, "Total Amount: (\d+\.\d{2})").Groups(1).Value  

- **Add Data Row**  
  Appends extracted data to the table

- **Write Range Workbook**
Outputs the final data table to Exce

---

## 📊 Result

The automation generates a structured Excel file containing invoice metadata extracted from all PDFs in the target folder. Each row represents one invoice, with the following columns:

| Invoice Number | Invoice Date | Due Date   | Total    |
|----------------|--------------|------------|----------|
| 38114          | 21/07/2016   | 30/07/2016 | $50.00   |
| 11222          | 21/07/2020   | 12/08/2016 | $4130.00 |
| 45321          | 05/02/2019   | 25/02/2019 | $80.00   |
| 54321          | 05/12/2017   | 30/01/2018 | $30.00   |
| 43214          | 21/09/2020   | 12/10/2020 | $2110.00 |

### ✅ Output Highlights
- Clean tabular format ready for analysis or reporting  
- Extracts all key fields using Regex: `Invoice Number`, `Invoice Date`, `Due Date`, and `Total`  
- Handles both scanned and native PDFs with fallback OCR logic  
- Ideal for financial audits, dashboard integration, or archival

> Note: This workflow currently runs in **attended mode** via UiPath Studio. For full automation, consider deploying it through **UiPath Orchestrator** with scheduling and exception handling.

---

## 🎨 Workflow Diagram

![Workflow Diagram](https://github.com/Jerin-Abraham-George/UiPath-Projects/blob/main/PDF-Data-Extraction/Main%20Sequence.jpg)

---
