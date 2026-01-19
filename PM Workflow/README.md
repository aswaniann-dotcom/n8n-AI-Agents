# AI Research & PRD Automation Flow — n8n Orchestrated Multi-Agent Pipeline

This repository showcases an **n8n-based multi-agent automation workflow** that analyzes market or user research requests, intelligently routes them to the appropriate expert agent, and optionally generates a **Product Requirements Document (PRD)** using a predefined template.

The workflow is powered by an **Orchestration Agent**, specialized research agents, a PRD generation agent, a user decision handler, and automated file creation—forming an end-to-end research-to-PRD pipeline.

----

## 🚀 Overview

This n8n workflow automates the following sequence:

- Accept an incoming user message  
- Detect user intent → Market Research, User Research, or PRD creation  
- Route the request to the relevant expert agent  
- Retrieve additional insights using external search (Tavily)  
- Persist and reuse memory across research steps  
- Return a consolidated response to the user  
- Ask whether the user wants a PRD generated  
- If confirmed → generate a PRD using a standard template  
- Convert the PRD into a downloadable file  
- Deliver the final output to the user  

This enables a **fully automated Research → Insights → PRD generation pipeline**.

---

## 🧠 Architecture Diagram

<img width="559" height="308" alt="image" src="https://github.com/user-attachments/assets/dd0b314f-eed3-486b-9ee3-cec921f74409" />


---

## 🧩 Agents Under the Orchestration Layer

### Market Research Agent
- Competitive landscape analysis  
- Market sizing and opportunity assessment  
- Pricing and positioning insights  
- Industry trends and strategic recommendations  

### User Research Analyst
- User behavior and pain-point analysis  
- Interview-style synthesis  
- Usability and experience insights  

### PRD Generator
- Consumes research output  
- Applies a predefined PRD template  
- Produces structured product documentation  

Each agent leverages:
- OpenAI Chat Models  
- Simple Memory  
- Tavily Search Tool (optional external research)

---

## 🔧 Component Breakdown

### 1. Trigger: When Chat Message Received
The workflow entry point that captures user input.

---

### 2. Orchestration Agent
A centralized LLM responsible for:
- Interpreting user intent  
- Routing requests to:
  - Market Research Agent  
  - User Research Analyst  
  - PRD Generator (only when explicitly requested)  
- Determining downstream execution paths  

**Example routing logic:**
- Market, competitors, pricing, or industry queries → Market Research Agent  
- User needs, interviews, or pain points → User Research Analyst  
- Explicit PRD requests → PRD Generator  

---

### 3. Market Research Agent
Handles:
- Competitor comparisons  
- Market structure and dynamics  
- Strategic and business insights  

Uses:
- OpenAI Chat Model  
- Memory  
- Tavily Search  

---

### 4. User Research Analyst
Focuses on:
- Synthesizing user feedback  
- Identifying friction points  
- Mapping user journeys  
- Recommending UX improvements  

Uses:
- OpenAI Chat Model  
- Memory  
- Tavily Search  

---

### 5. Response Handling
Once an expert agent completes its analysis:
- The response is returned via **Respond to Chat**
- The system prompts the user:
  > *“Would you like me to generate a PRD based on this research?”*

---

### 6. User Input Handler (IF Node)
- If the user responds **“yes”**, the workflow proceeds to PRD generation  
- If **“no”**, the workflow responds and exits  

---

### 7. PRD Generator Agent
This agent:
- Consumes accumulated research insights  
- Applies the predefined PRD template  
- Generates structured sections including:
  - Problem Statement  
  - Goals & Success Metrics  
  - Target Users  
  - Product Requirements  
  - Competitive Context  
  - Feature Breakdown  
  - Risks & Open Questions  

Uses:
- OpenAI Chat Model  
- Memory  

---

### 8. Convert to File Node
- Transforms PRD text into a downloadable file  
- Supports `.txt` (extendable to PDF or Markdown)

---

### 9. Final Response Node
Outputs:
- Research insights  
- PRD file (if generated)

---

## 📁 Repository Structure

├── README.md
├── PM workflow.json # Exported n8n workflow


---

## 💡 Key Capabilities

- ✔ **Multi-Agent LLM Architecture** for intelligent task routing  
- ✔ **Automated PRD Generation** from research insights  
- ✔ **Memory-Aware Processing** for contextual consistency  
- ✔ **Human-in-the-Loop Control** for PRD creation  
- ✔ **External Research Integration** via Tavily  

---

## 📦 How to Use

1. Import `PM workflow.json` into your n8n instance  
2. Configure API keys:
   - **OpenAI API** – required for all agents  
   - **Tavily API** – required for external research  
3. The PRD template is preconfigured in the PRD Generator’s system prompt  
4. Activate the workflow  
5. Start interacting — the system automatically routes queries to the correct agent  

> **Note:** The PRD Generator is triggered only when explicitly requested  
> (e.g., *“generate a PRD”*, *“create a product requirements document”*).

---

## 🔮 Future Enhancements

- Jira / Trello integration for automatic ticket creation  
- Export PRDs as PDF or Google Docs  
- Additional agents:
  - Competitive Intelligence Agent  
  - UX Design Agent  
- Analytics and reporting dashboards  

---




*(Derived from the n8n workflow)*

