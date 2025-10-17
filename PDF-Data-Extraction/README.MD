# 📄 PDF Data Extraction

## 🧭 Overview
This UiPath automation extracts structured data from a folder of PDF invoices and writes the results into an Excel file. It intelligently handles both native and scanned PDFs using OCR when necessary.

---

## 🎯 Objectives
- Automate extraction of invoice data from PDFs  
- Handle both scanned and native PDFs with conditional logic  
- Export extracted data to a structured Excel sheet

--


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

The automation produces a structured Excel file containing key invoice metadata extracted from all PDFs in the target folder. Each row in the output represents one invoice, with the following columns:

| Invoice Number | Invoice Date | Total Amount |
|----------------|--------------|--------------|
| 10234          | 15/09/2025   | 1,250.00     |
| 10235          | 16/09/2025   | 980.50       |
| ...            | ...          | ...          |

### ✅ Output Highlights
- Consistent formatting across all entries  
- Accurate extraction using Regex, even from scanned PDFs  
- Minimal manual effort — just one click to run  
- Compatible with downstream reporting tools like Power BI or Excel dashboards

> Note: This workflow is designed for **attended execution** via UiPath Studio. To make it fully unattended, consider deploying it through **UiPath Orchestrator** with proper scheduling and exception handling.

---
