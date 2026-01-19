# AI Research Knowledge Byte Generator

This project contains an **n8n automation workflow** that generates **AI-powered research knowledge bytes** from user input, formats them into a **styled HTML template**, and distributes them via **email** or API response.

The workflow is designed for use cases such as **internal newsletters, learning digests, research summaries, and executive knowledge sharing**, with minimal human intervention.

---

## 🚀 Overview

This n8n workflow automates the following steps:

- Accept a research topic via webhook
- Configure workflow parameters dynamically
- Perform AI-driven research and content generation
- Structure the output using a predefined schema
- Convert the content into a rich HTML knowledge byte
- Send the generated knowledge byte via email
- Optionally respond back to a UI or API caller

This creates an **end-to-end research → content → delivery pipeline**.

---

## 🔄 Workflow Execution Flow

### 1️⃣ Trigger: Webhook Trigger
- The workflow starts when an HTTP **POST request** is received.
- Accepts input such as:
  - Research topic
  - Target audience
  - Tone or depth (optional)

---

### 2️⃣ Workflow Configuration
- Normalizes and enriches incoming parameters.
- Sets defaults for missing inputs.
- Acts as a centralized configuration layer.

---

### 3️⃣ Wait Node
- Introduces controlled delay if needed.
- Useful for rate limiting or asynchronous execution.

---

### 4️⃣ AI Research Agent
- Core intelligence layer of the workflow.
- Uses:
  - OpenAI Chat Model
  - Memory for contextual consistency
  - Structured Output Parser for predictable results
- Generates:
  - Key concepts
  - Insights
  - Examples
  - Takeaways

---

### 5️⃣ Create HTML Knowledge Byte
- Transforms structured AI output into a styled **HTML template**.
- Produces visually consistent, shareable knowledge content.
- Suitable for email and web display.

---

### 6️⃣ Send Knowledge Byte Email
- Sends the generated HTML content via email.
- Can be configured for:
  - Individual recipients
  - Mailing lists
  - Internal distribution groups

---

### 7️⃣ Respond to UI / Webhook
- Returns the generated content to:
  - UI client (if active)
  - Calling system via webhook response
- Enables integration with frontend applications or dashboards.

---

## 🧠 Architecture Summary

<img width="768" height="198" alt="image" src="https://github.com/user-attachments/assets/a7aa110a-7720-44a1-b64a-4f6197abbb3f" />


---

## 🧩 Key Components

- **Webhook Trigger** – Entry point for external systems
- **Workflow Configuration Node** – Centralized parameter handling
- **AI Research Agent** – Research and content generation
- **Structured Output Parser** – Enforces output consistency
- **HTML Template Generator** – Visual formatting
- **Email Node (Gmail)** – Content distribution
- **Respond to Webhook** – API-based response handling

---

## 📁 Folder Structure (Recommended)

knowledge-byte-generator/
├── README.md
├── knowledge-byte-workflow.json


---

## 🔐 Required Credentials

- **OpenAI API**
  - Required for AI research and content generation
- **Gmail / Email Provider**
  - Required for sending knowledge bytes via email
- **Webhook Configuration**
  - Required for external triggering

---

## 📦 How to Use

1. Import the workflow JSON into n8n
2. Configure credentials:
   - OpenAI
   - Email provider (Gmail or SMTP)
3. Activate the workflow
4. Send a POST request to the webhook with a research topic
5. Receive:
   - HTML knowledge byte via email
   - Optional API response

---

## 💡 Use Cases

- Internal learning newsletters
- Research summaries for leadership
- Daily or weekly knowledge bytes
- Product, tech, or market explainers
- AI-powered content automation

---

## 🔮 Future Enhancements

- Add scheduling for daily/weekly digests
- Support multiple HTML themes
- Integrate with Slack or MS Teams
- Add analytics (open rate, engagement)
- Enable multi-language content generation

---


