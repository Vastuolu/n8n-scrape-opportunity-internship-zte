# 📡 ZTE Market Intelligence Automation (n8n + Firecrawl)

Automated B2B & B2G market intelligence pipeline for telecom, ICT, and digital infrastructure opportunities in Indonesia.

---

## 🚀 Overview

This workflow transforms raw web data into actionable business intelligence:

- Scrapes news & tender sources (Bisnis, Kontan, CNBC)
- Converts into B2B & B2G opportunity signals
- Structures results into consistent JSON
- Sends insights to Slack

---

## ⚙️ Architecture

Trigger  
├── B2G Flow (Tender Intelligence)  
│   ├── Firecrawl Agent  
│   ├── Wait (Async)  
│   ├── Status Check + Retry  
│   └── Slack Report  
│  
└── B2B Flow (Market Intelligence)  
    ├── Firecrawl Agent  
    ├── Wait (Async)  
    ├── Status Check + Retry  
    └── Slack Report  

---

## 🧩 Key Components

### Firecrawl Agent
- Scrapes and analyzes sources
- Uses LLM prompt for structured output

### Retry Mechanism
- Handles async execution
- Retries until completed or failed

### Slack Integration
- Sends formatted insights (not raw JSON)
- Optimized for readability

---

## 📊 Output Structure

- extraction_metadata  
- executive_summary  
- zte_relevant_opportunities  
- market_intelligence  
- strategic_recommendations  

---

## 💼 B2B Intelligence Focus

- 5G & telecom infrastructure
- Fiber & broadband rollout
- Data center investments
- AI & digital transformation
- Network upgrades

---

## 🏛️ B2G Intelligence Focus

- Government tenders
- National infrastructure projects
- Digital transformation programs

---

## 🛠️ Setup

### Requirements
- n8n
- Firecrawl API
- Slack Bot

### Environment Variables

FIRECRAWL_API_KEY=your_key  
SLACK_BOT_TOKEN=your_token  

---

## ⚠️ Common Issues

### Slack shows null
Fix JSON path:

$json.data?.data?.zte_relevant_opportunities || []

### Firecrawl stuck
Increase wait time or retry limit

---

## 🎯 Use Cases

- Sales intelligence
- Market research
- Lead generation
- Strategy planning

---

## 📄 License

MIT
