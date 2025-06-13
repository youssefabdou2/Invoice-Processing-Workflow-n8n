

# 📄 Invoice Processing Workflow

This project is an **automated workflow** created with **n8n** to streamline the handling of incoming invoices. The system detects new invoice files in a specified Google Drive folder, extracts key information from PDF files, updates a Google Sheets database, and sends a confirmation email.

---

## 🔧 Features

* **Auto-trigger** on new invoice uploads to Google Drive.
* **PDF text extraction** using n8n's file processing.
* **Smart data parsing** via a language model (OpenAI GPT-4o-mini) to extract:

  * Invoice Number
  * Client Name
  * Client Email
  * Client Address
  * Client Phone
  * Total Amount
  * Invoice Date
  * Due Date
* **Data storage** in a centralized Google Sheet for reporting.
* **Automated email generation** and optional notifications.

---

## 🛠️ Workflow Overview

1. **Google Drive Trigger**: Detects new PDF files in a specific folder.
2. **DownloadFileBinary**: Downloads the PDF file.
3. **Extract from File**: Extracts raw text from the PDF.
4. **Information Extractor**: Uses Langchain + OpenAI to parse structured invoice data.
5. **Update DB**: Appends the structured data to a Google Sheets document.
6. **CreateEmail** *(Optional)*: Generates a follow-up email using AI.
7. **SendEmail** *(Optional)*: Sends the generated email to the client or stakeholder.

---

## 🔗 Resources

* **Watched Folder**: [Google Drive Projects Folder](https://drive.google.com/drive/folders/12wQIR9C4T9ioTZv3dY0uBhL186FUeiAu)
* **Invoice DB**: [Google Sheet Invoice Database](https://docs.google.com/spreadsheets/d/1Or3wD9_YipetihvxYLMdLnLNDd4fQRhZ25A6r7KWUdM/edit#gid=0)

---

## 🔐 Credentials Required

* Google Drive OAuth2
* Google Sheets OAuth2
* OpenAI API key (configured for GPT-4o-mini)

---

## 🚀 How to Deploy

1. Import the JSON into your **n8n** instance.
2. Configure your credentials (Google Drive, Sheets, OpenAI).
3. Adjust folder/document IDs if necessary.
4. Activate the workflow.

---

## 📬 Example Use Case

1. A user drops a new invoice PDF into the Drive folder.
2. The workflow is triggered.
3. Invoice data is extracted and logged in Google Sheets.
4. An email is optionally composed and sent.

---

## 📌 Notes

* Ensure invoice PDFs are text-readable (non-scanned).
* You can further customize the email template or database structure as needed.
* All node names are descriptive for easy editing or debugging.

---


