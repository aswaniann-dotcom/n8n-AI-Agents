# Daily AI News Summary & Email Digest 

This project contains an **n8n automation workflow** that fetches the latest AI-related news, summarizes it using an AI agent, and delivers a **concise daily digest via email**.

The workflow supports both **manual execution** and **scheduled daily runs**, making it ideal for staying up to date with AI trends without manual effort.

---

## 🚀 Overview

This n8n workflow automates the following:

- Fetch the latest AI news from external sources
- Summarize articles using an AI-powered agent
- Format the summary for readability
- Send a daily AI news digest via email
- Support scheduled and on-demand execution

This creates a **fully automated daily AI news briefing system**.

---

## 🔄 Workflow Execution Flow

### 1️⃣ Trigger: Manual Execution
- The workflow can be started by clicking **Execute Workflow**.
- Useful for testing or on-demand summaries.

---

### 2️⃣ Trigger: Scheduled Execution
- The workflow runs automatically **every day at 7:00 AM**.
- Ensures timely delivery of the daily news digest.

---

### 3️⃣ Get AI News
- Fetches the latest AI-related news articles.
- Acts as the primary data source for summarization.

---

### 4️⃣ AI Summary Agent
- Core intelligence of the workflow.
- Uses:
  - OpenAI Chat Model
  - Tool integration for news retrieval
- Produces:
  - Concise summaries
  - Key highlights
  - Actionable insights

---

### 5️⃣ Output
- Displays the generated summary within n8n.
- Useful for validation and debugging.

---

### 6️⃣ Send Summary by Email
- Sends the summarized AI news via email.
- Can be configured for:
  - Individual recipients
  - Mailing lists
  - Internal teams

---

## 🧠 Architecture Summary

<img width="557" height="277" alt="image" src="https://github.com/user-attachments/assets/6d160973-ee0f-4be1-84f9-58e95bd30823" />


---

## 🧩 Key Components

- **Manual Trigger** – On-demand execution
- **Cron Trigger** – Daily execution at 7 AM
- **AI Summary Agent** – AI-powered content summarization
- **OpenAI Chat Model** – Natural language processing
- **News Retrieval Tool** – Source of AI news
- **Email Node (Gmail/SMTP)** – Digest delivery

---

## 📁 Folder Structure (Recommended)

daily-ai-news-digest/
├── README.md
├── daily-ai-news-workflow.json


---

## 🔐 Required Credentials

- **OpenAI API**
  - Required for summarization
- **News API / RSS Source**
  - Required to fetch AI news
- **Email Provider (Gmail / SMTP)**
  - Required for email delivery

---

## 📦 How to Use

1. Import the workflow JSON into n8n
2. Configure credentials:
   - OpenAI
   - News source
   - Email provider
3. Adjust the schedule if needed
4. Activate the workflow
5. Receive a daily AI news summary at 7:00 AM

---

## 💡 Use Cases

- Daily AI trend monitoring
- Executive AI briefings
- Team knowledge sharing
- Personal learning automation
- Internal newsletters

---

## 🔮 Future Enhancements

- Topic-based filtering (GenAI, LLMs, Regulation)
- Multi-language summaries
- Slack or MS Teams integration
- User preference personalization
- Analytics on email engagement

---
