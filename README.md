# 📡 ZTE Market Intelligence Automation (n8n + Firecrawl)

Automated B2B & B2G market intelligence pipeline for telecom, ICT, and digital infrastructure opportunities in Indonesia.

This workflow uses **Firecrawl Agents + n8n** to scrape, analyze, and deliver structured business signals directly to Slack.

---

## 🚀 Overview

This project transforms raw web data into **actionable business intelligence**:

- 🔍 Scrapes news & tender sources (Bisnis, Kontan, CNBC, etc.)
- 🧠 Reinterprets data into **B2B / B2G opportunity signals**
- 📊 Structures output into consistent JSON format
- 📡 Sends curated insights to Slack for sales & strategy teams

---

## ⚙️ Architecture

```
Trigger
  ├── B2G Flow (Tender Intelligence)
  │     ├── Firecrawl Agent (Scrape)
  │     ├── Wait (async handling)
  │     ├── Status Check (retry loop)
  │     └── Slack (Tender Report)
  │
  └── B2B Flow (Market Intelligence)
        ├── Firecrawl Agent (Scrape)
        ├── Wait (async handling)
        ├── Status Check (retry loop)
        └── Slack (Market Signals)
```

---

## 🧩 Key Components

### 1. Firecrawl Agent (Async)
- Scrapes target sources
- Processes with LLM prompt
- Returns structured JSON

### 2. Retry Mechanism
- Handles async execution
- Retries until:
  - ✅ Completed
  - ❌ Failed (sent to Slack error alert)

### 3. Slack Integration
- Sends formatted insights (NOT raw JSON)
- Uses dynamic templating
- Designed for readability by business teams

---

## 📊 Output Structure

Both B2B and B2G flows follow a **strict JSON schema**:

### Core Sections:
- `extraction_metadata`
- `executive_summary`
- `zte_relevant_opportunities`
- `market_intelligence`
- `strategic_recommendations`

---

## 💼 B2B Intelligence Focus

Instead of just scraping news, this system detects:

- 📡 Telecom infrastructure expansion
- 🌐 Fiber & broadband rollout
- 🏗️ Data center investments
- 🤖 AI & digital transformation initiatives
- 🔄 Network upgrades & integration cycles

---

## 🏛️ B2G Intelligence Focus

- Government tenders
- Public infrastructure projects
- National digital programs (RPJMN, BAKTI, etc.)
- Procurement signals

---

## 📩 Slack Output Example

```
📡 B2B Market Signal — ZTE Indonesia
📅 01 Jun 2026, 10:00 WIB

🌏 MARKET PULSE
Indonesia telecom market shows strong demand...

🎯 OPPORTUNITIES
🔴 5G Expansion - Telkom
🏢 Telkom Indonesia (SOE)
📌 Network Infrastructure | Stage: Expansion
💵 Rp 27.5T
👉 Next: Engage stakeholders

⚡ THIS WEEK
1. Engage XLSmart
2. Strengthen MoraRepublic partnership
```

---

## 🛠️ Setup

### 1. Requirements
- n8n (self-hosted or cloud)
- Firecrawl API access
- Slack Bot Token

---

### 2. Environment Variables

```
FIRECRAWL_API_KEY=your_api_key
```

---

### 3. Import Workflow

1. Open n8n
2. Click **Import Workflow**
3. Upload JSON file from this repo
4. Configure credentials:
   - Firecrawl
   - Slack

---

## 🔧 Customization

### Add New Sources

```
"sources_analyzed": [
  "https://teknologi.bisnis.com",
  "https://www.kontan.co.id",
  "https://www.cnbcindonesia.com/tech"
]
```

---

## 🎯 Use Cases

- Telecom vendor sales intelligence
- Market research automation
- Competitive monitoring
- Strategic planning support
- Lead generation (early signal detection)
