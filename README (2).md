# 🚀 CareerForge AI — AI-Powered Career Assistant for Indian Job Seekers

> Final Year Major Project | Computer Engineering | DBATU  
> Built with **n8n** · **Groq LLM** · **Apify** · **Google Sheets** · **Gmail**

---

## 📌 Overview

CareerForge AI is a full-stack career automation platform that helps Indian freshers and job seekers land jobs faster using AI. It combines a polished frontend UI with a powerful n8n workflow backend — all without writing a single line of backend server code.

---

## ✨ Features

| Module | What it does |
|---|---|
| 🔍 **Job Search** | Scrapes live job listings from Indeed & LinkedIn via Apify |
| 📝 **Resume Tailor** | Rewrites your resume bullets to match a specific JD |
| 🎯 **ATS Keyword Injector** | Injects missing ATS keywords without making it sound robotic |
| 🎤 **Mock Interview Simulator** | 15-question interview prep for any role, India-specific |
| 🏢 **Company Research** | Deep-dives on company culture, growth, and interview style |
| 🤝 **Networking Message Generator** | Cold outreach + LinkedIn connection messages |
| ⚖️ **Offer Comparison** | Side-by-side offer analysis with a final recommendation |
| 🔄 **Career Pivot Advisor** | Roadmap to switch domains with skill gap analysis |
| 📅 **30-Day Sprint Plan** | Personalized 30-day job search action plan |
| 📄 **Cover Letter Writer** | Role-specific cover letters with 3 tone options |
| 🎯 **Job Match Analyzer** | Match score, ATS gap, and recruiter red flags |

---

## 🏗️ Architecture

```
Frontend (careerforge.html)
        │
        ▼
  n8n Webhook → Intent Router
        │
        ├── Job Search Agent     → Apify Scraper → Google Sheets
        ├── Resume/ATS Agents    → Groq LLM (llama-3.3-70b)
        ├── Interview Agent      → Groq LLM
        ├── Research Agent       → Groq LLM + Web
        └── All responses        → Gmail notification (optional)
```

The entire backend is a single **n8n workflow** (`dd09.json`) — no Express, no Flask, no deployment needed.

---

## 🛠️ Tech Stack

- **Frontend** — Vanilla HTML/CSS/JS (single file, zero dependencies)
- **Workflow Automation** — n8n (self-hosted)
- **LLM** — Groq API (`llama-3.3-70b-versatile`)
- **Job Scraping** — Apify (Indeed + LinkedIn scrapers)
- **Storage** — Google Sheets (job results cache)
- **Notifications** — Gmail OAuth2
- **PDF Export** — html2pdf.app API

---

## 🚀 Getting Started

### Prerequisites
- [n8n](https://n8n.io/) (self-hosted or cloud)
- Groq API key — [console.groq.com](https://console.groq.com)
- Apify account — [apify.com](https://apify.com)
- Google Sheets + Gmail OAuth2 credentials

### Setup

1. **Clone the repo**
   ```bash
   git clone https://github.com/YOUR_USERNAME/careerforge-ai.git
   cd careerforge-ai
   ```

2. **Import the n8n workflow**
   - Open your n8n instance
   - Go to **Workflows → Import from file**
   - Select `dd09.json`

3. **Configure credentials** in n8n:
   | Credential | Used for |
   |---|---|
   | Groq API | All LLM agents |
   | Apify API | Job scraping |
   | Google Sheets OAuth2 | Job result caching |
   | Gmail OAuth2 | Email notifications |

4. **Update the webhook URL** in `careerforge.html`:
   ```js
   const WEBHOOK_URL = "https://your-n8n-instance.com/webhook/careerforge";
   ```

5. **Open `careerforge.html`** in your browser — done!

---

## 📁 Project Structure

```
careerforge-ai/
├── careerforge.html     # Frontend UI (single file)
├── dd09.json            # n8n workflow (full backend)
└── README.md
```

---

## 📸 Screenshots

> *(Add screenshots of the UI, workflow canvas, and sample outputs here)*

---

## 🎓 Academic Context

This project was developed as a **Final Year Major Project** for the Bachelor of Engineering (Computer Engineering) program at **Dr. Babasaheb Ambedkar Technological University (DBATU)**, Semester VII.

**Key learning outcomes:**
- No-code/low-code AI workflow orchestration
- LLM prompt engineering for structured outputs
- API integration (REST, OAuth2, webhooks)
- Real-world product thinking for the Indian job market

---

## 📄 License

MIT License — feel free to fork and build on this.

---

## 🤝 Connect

**Siddharth** — Computer Engineering, DBATU  
[LinkedIn](https://linkedin.com/in/YOUR_PROFILE) · [GitHub](https://github.com/YOUR_USERNAME)
