# Media Intel Agent

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-Modern%20Web%20Framework-009688.svg)](https://fastapi.tiangolo.com/)
[![Gemini AI](https://img.shields.io/badge/Gemini%20AI-Content%20Analysis-orange.svg)](https://deepmind.google/technologies/gemini/)

A sophisticated News Intelligence Agent that transforms fragmented RSS feeds into actionable insights. By leveraging Large Language Models (LLMs), the agent automatically fetches, summarizes, and classifies news articles, providing a unified interface for natural language discovery.

---

## Key Features

### Fast Ingestion
- **Parallel Analysis**: Uses background `ThreadPoolExecutor` to process multiple articles simultaneously, reducing analysis time by up to 60%.
- **Smart Pull Limits**: Configurable article limits for both manual and scheduled ingestion ensuring consistent performance.
- **BeautifulSoup Optimized**: Robust HTML parsing with automatic tag discovery for featured images.

### Smart Scheduling & Automation
- **Autonomous Ingestion**: Integrated `APScheduler` for robust background updates at configurable intervals (2h to Weekly).
- **Graceful Shutdown**: Native FastAPI lifespan management ensures background tasks terminate cleanly.

### Advanced Feed Discovery
- **Dynamic Filtration**: Effortlessly sort your feed by **Category** or **Date Range** (From/To).
- **Persistence**: Filter states are automatically saved to your browser, so your view remains consistent across sessions.
- **Bulk Article Life-cycle**: Support for individual article deletion or bulk clearing of the entire feed.

### Modern Flat UI
- **Premium Aesthetics**: A distraction-free, high-performance dark theme dashboard.
- **Interactive Chat**: Natural language interface to query and discover insights from your persistent news database.

---

## Tech Stack

- **Backend**: Python 3.9+, FastAPI, APScheduler
- **AI Engine**: Google Gemini API (google-genai)
- **Data & Parsing**: SQLite, BeautifulSoup4, Feedparser, python-dateutil
- **Development**: Uvicorn, PyYAML, ThreadPoolExecutor

---

## 📁 Project Structure

```text
├── src/
│   ├── analyzer.py   # LLM integration for parallel summarization
│   ├── fetcher.py    # RSS ingestion & Image discovery
│   ├── storage.py    # SQLite management with filtration support
│   ├── interface.py  # Query processing & formatting
├── static/           # Web UI frontend (Flat Design, HTML/CSS/JS)
├── main.py           # CLI Entry point
├── server.py         # FastAPI Web server & Background Scheduler
└── config.yaml       # Scheduling, Feed & Agent configuration
```

---

## ⚙️ Setup & Installation

### 1. Prerequisites
- Python 3.9+
- A Google Gemini API Key (available via [Google AI Studio](https://aistudio.google.com/))

### 2. Clone and Install
```bash
git clone https://github.com/your-username/Media-Intel-Agent.git
cd Media-Intel-Agent
pip install -r requirements.txt
```

### 3. Configuration
1. Create a `.env` file in the root directory:
   ```env
   GOOGLE_API_KEY=your_api_key_here
   ```
2. Customize `config.yaml` to add your RSS feeds, analysis rules, and preferred ingestion schedule.

---

## 📖 Usage

### Web Dashboard (Primary Interface)
Start the server:
```bash
python server.py
```
Visit `http://localhost:8000` to access the dashboard. From there, you can:
- **Refresh**: Trigger a manual parallel ingestion pull.
- **Schedule**: Configure background auto-updates in the Settings view.
- **Chat**: Ask questions like "What are the latest breakthroughs in AI?"
- **Filter**: Narrow down your feed by specific dates or categories.

---

## ⚖️ License

Distributed under the MIT License. See `LICENSE` for more information.

---

*Engineered for intelligence and speed.*
