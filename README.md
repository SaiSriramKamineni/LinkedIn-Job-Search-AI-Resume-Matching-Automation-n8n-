 Job Search & AI Resume Matching Automation (n8n)
# LinkedIn<img width="1877" height="920" alt="Screenshot 2025-12-22 014544" src="https://github.com/user-attachments/assets/ab417731-b9a1-4d85-8015-1330e8db7bd9" />


## Overview

This n8n automation template enables **fully automated LinkedIn job discovery, resume matching, and alerting**.

The workflow periodically searches LinkedIn jobs based on customizable criteria, compares each job description with your resume using **AI (Google Gemini or OpenAI)**, generates a **match score and a tailored cover letter**, and stores the results in **Google Sheets**.
High-matching jobs trigger **real-time Telegram alerts**, enabling faster and more targeted job applications.

This system eliminates repetitive job searching and replaces it with an **AI-driven, personalized job intelligence pipeline**.

---

## Key Features

* 🔍 **Automated LinkedIn job search** using dynamic filters
* 📄 **Resume parsing from PDF** (Google Drive)
* 🤖 **AI-powered job–resume matching**
* ✍️ **Auto-generated sample cover letters**
* 📊 **Centralized job tracking in Google Sheets**
* 🔔 **Telegram alerts for high-match jobs**
* ⏰ **Scheduled daily execution**

---

## High-Level Workflow

1. **Scheduled Trigger**

   * Runs daily (customizable interval)

2. **Resume Ingestion**

   * Downloads resume PDF from Google Drive
   * Converts PDF content to text for AI processing

3. **Job Search Configuration**

   * Reads job search filters from Google Sheets:

     * Keywords
     * Location
     * Experience level
     * Remote / Onsite
     * Job type
     * Easy Apply option

4. **LinkedIn Job Discovery**

   * Constructs LinkedIn search URLs dynamically
   * Fetches job listings and extracts job links

5. **Job Processing Loop**

   * Fetches each job page (with rate limiting)
   * Extracts:

     * Job title
     * Company
     * Location
     * Job description
     * Apply link

6. **AI Resume Matching**

   * AI compares resume with job description
   * Outputs:

     * Match score (0–100)
     * Matching analysis
     * Tailored sample cover letter

7. **Data Storage**

   * Parses AI output into structured JSON
   * Appends or updates job records in Google Sheets

8. **Smart Alerts**

   * Filters jobs above a configurable score threshold
   * Sends Telegram alerts for high-quality matches

---

## Prerequisites

### AI Provider (Choose One)

* **Google Gemini API Key**
  OR
* **OpenAI API Key**

### Integrations & Credentials

* **Telegram Bot Token** (via `@BotFather`)
* **Google Sheets OAuth2 Credentials**
* **Google Drive OAuth2 Credentials**
* **n8n instance** (cloud or self-hosted)

---

## Setup Guide

### 1️⃣ Upload Your Resume (Google Drive)

* Upload your resume **in PDF format** to Google Drive
* Configure the **Google Drive node** to:

  * Authenticate using OAuth2
  * Read files from your Drive
  * Select your resume from the file list

> ℹ️ Google OAuth2 credentials must be configured in n8n beforehand.
> Refer to n8n documentation for Google OAuth setup.

---

### 2️⃣ Create Google Sheet for Job Configuration & Results

You must create a Google Sheet with **two worksheets**:

#### Sheet 1: Job Filter Configuration

Used to define job search criteria such as:

* Keywords
* Location
* Experience level
* Job type
* Remote preference
* Easy Apply filter

#### Sheet 2: Job Results

Stores:

* Job details
* AI match score
* AI-generated cover letter
* Apply links
* Processing timestamps

📄 You can **download the provided Google Sheet template** and copy it to your personal Google Drive.

> ℹ️ Configure Google Sheets OAuth2 in n8n and grant access.

---

### 3️⃣ Configure Telegram Bot

* Create a Telegram bot using **@BotFather**
* Copy the **Bot Token**
* Add the token to the Telegram node in n8n
* Obtain your **TELEGRAM_CHAT_ID** (your Telegram user ID)
* Paste the Chat ID into the Telegram node configuration

Once configured, you’ll receive job alerts directly on Telegram.

---

## Customization Options

* ⏱ Change workflow execution frequency
* 🎯 Modify AI match score threshold
* 🔎 Adjust job search filters dynamically via Google Sheets
* ✍️ Customize AI prompt for cover letter style
* 🤖 Switch between Gemini and OpenAI models

---

## Why This Project Matters

* Demonstrates **end-to-end automation**
* Combines **AI, scraping, document processing, and messaging**
* Solves a **real-world productivity problem**
* Shows strong skills in:

  * Workflow orchestration
  * AI integration
  * Data structuring
  * System design

---

## Use of AI Tools

AI tools were used to:

* Compare resumes with job descriptions
* Generate structured matching scores
* Draft contextual cover letters
* Assist in refining prompt design and documentation clarity

All workflow design, system logic, and integration decisions were implemented and validated manually.

---

