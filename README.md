# 🌀 Automated Lead Management Workflow (n8n)

This project is a **fully automated lead pipeline** built with [n8n].  
It captures leads from forms, cleans & validates the data, enriches it with company details, and then routes valid leads to a CRM + sales team automatically.

## 🚀 Features
- Captures new leads from **Jotform** submissions in real-time  
- Extracts structured data from unstructured input using AI  
- Logs all leads into a **Google Sheet database** for backup  
- Validates emails with **Abstract API** to ensure deliverability  
- Enriches company info (city, country, industry, employee count) using **Abstract API**  
- Filters invalid leads (missing company / bad email)  
- Stores valid leads in **Airtable CRM**  
- Notifies the **sales team via Telegram bot** instantly  

---

## ⚙️ Workflow Overview

1. **Webhook (Trigger)**  
   - Captures new form submissions from Jotform.

2. **Data Extractor (AI Parsing)**  
   - Extracts clean structured fields like:
     ```json
    {
    "Name": "Rohit Mehra",
    "Email": "rohit.mehra@payverse.com",
    "Phone Number": "+91-9876543210",
    "Company Name": "PayVerse",
    "Job Title": "Co-Founder & CEO",
    "Interests": "Partnerships & Collaborations",
    "Country": "India",
    "Message": "Looking to explore potential fintech collaborations",
    "Company Domain": "payverse.com"
  }

     ```

3. **Google Sheet (Database)**  
   - Logs every raw lead for backup & tracking.

4. **Email Validator (Abstract API)**  
   - Checks if the email is deliverable.

5. **Company Enrichment (Abstract API)**  
   - Uses the company domain to fetch extra details:
     - City  
     - Country  
     - Industry  
     - Employee Count  

6. **IF Node (Validation)**  
   - If **email is valid** AND **company name is not empty** → send to CRM.  
   - Else → ignored (no operation).

7. **Airtable (Main CRM Database)**  
   - Stores enriched valid leads with fields:
     - Name  
     - Email  
     - Phone Number  
     - Job Title  
     - Interest  
     - Message  
     - Company Name  
     - Domain  
     - City  
     - Country  
     - Industry  
     - Employee Count  

8. **Telegram Bot (Sales Notification)**  
   - Sends valid leads directly to the sales team chat.

---

## 🛠️ Tech Stack
- **n8n** → Automation engine  
- **Docker** → Containerized setup  
- **ngrok** → Public tunneling for webhooks  
- **Google Sheets** → Lead backup database  
- **Abstract API** → Email validation & company enrichment  
- **Airtable** → CRM database  
- **Telegram Bot API** → Instant sales alerts  
---

## 🌟 Why This Project?
This project demonstrates how to automate lead management like a **real-world SaaS workflow**.  
It reduces manual work, ensures clean data, and gives sales teams valid enriched leads in real-time.  
---

**The json of the workflow is available on workflow.json**
**Screenshot of the workflow is availabe on the screenshots.md**

