# 🚀 Starlink Usage Dashboard

A modern data-monitoring platform built for Starlink subscribers that automatically collects, analyzes, and visualizes internet usage statistics through an intuitive web dashboard.

---

## 📖 Overview

Starlink Usage Dashboard automates the process of gathering bandwidth consumption data from your Starlink account. Instead of manually checking usage reports, the application retrieves data automatically and presents it through interactive charts, analytics, and exportable reports.

The scraper utilizes Playwright's network monitoring capabilities to capture usage information directly from Starlink's backend responses, resulting in greater reliability compared to traditional page scraping methods.

---

## ✨ Highlights

### 🔐 Smart Authentication

* One-time login process
* Persistent session storage
* Automatic session reuse
* Re-authentication only when required

### 📡 Automated Data Collection

* Playwright-powered browser automation
* Network request interception
* Multi-month historical retrieval
* Background scraping support

### 📊 Advanced Analytics

* Daily consumption tracking
* Monthly trend analysis
* Usage summaries and insights
* Interactive visual reports

### 📁 Data Export

* Lightweight CSV generation
* Residential usage-focused output
* Quick download functionality

### 🎨 Modern Interface

* Responsive design
* Dark-mode inspired theme
* Real-time dashboard updates
* Searchable and sortable tables

---

## 🏗️ Architecture

```text
┌─────────────────┐
│  Starlink Web   │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ Playwright Bot  │
│ Network Capture │
└────────┬────────┘
         │
         ▼
┌─────────────────┐
│ FastAPI Backend │
└────────┬────────┘
         │
 ┌───────┴────────┐
 ▼                ▼
SQLite       Dashboard UI
Database     Charts & Stats
```

---

## 🛠 Technology Stack

| Layer         | Tools                 |
| ------------- | --------------------- |
| Backend API   | FastAPI, Uvicorn      |
| Automation    | Playwright            |
| Storage       | SQLite, aiosqlite     |
| Frontend      | HTML, CSS, JavaScript |
| Visualization | Chart.js              |
| Language      | Python 3.10+          |

---

## 📂 Repository Layout

```text
Starlink_Scraper
│
├── backend/
│   ├── app.py
│   ├── config.py
│   ├── database.py
│   ├── models.py
│   └── routes/
│
├── scraper/
│   ├── auth.py
│   ├── browser.py
│   ├── extractor.py
│   └── tasks.py
│
├── frontend/
│   ├── index.html
│   ├── css/
│   └── js/
│
├── data/
├── .env.example
├── requirements.txt
└── run.py
```

---

## ⚡ Quick Start

### Requirements

* Python 3.10+
* Pip
* Chromium Browser (via Playwright)

### Installation

#### Clone the Project

```bash
git clone <repository-url>
cd Starlink_Scraper
```

#### Create Virtual Environment

```bash
python -m venv venv
```

Windows:

```bash
venv\Scripts\activate
```

Linux/macOS:

```bash
source venv/bin/activate
```

#### Install Dependencies

```bash
pip install -r requirements.txt
```

#### Install Browser Engine

```bash
playwright install chromium
```

#### Configure Environment

```bash
copy .env.example .env
```

Update:

```env
STARLINK_URL=YOUR_STARLINK_USAGE_PAGE
```

#### Launch Application

```bash
python run.py
```

Access the dashboard:

```text
http://127.0.0.1:8000
```

---

## 🔑 First Login Workflow

1. Open the dashboard.
2. Press **Start Scraping**.
3. A Chromium browser window will appear.
4. Sign in to your Starlink account.
5. Session data is automatically saved.
6. Scraping continues in headless mode.
7. Future runs use the saved session automatically.

---

## 📊 Available Endpoints

### Usage Data

| Endpoint             | Purpose           |
| -------------------- | ----------------- |
| `/api/usage/daily`   | Daily statistics  |
| `/api/usage/monthly` | Monthly summaries |
| `/api/usage/all`     | Complete dataset  |
| `/api/usage/summary` | Dashboard metrics |

### Scraper Controls

| Endpoint              | Purpose            |
| --------------------- | ------------------ |
| `/api/scrape/start`   | Start scraper      |
| `/api/scrape/status`  | Check progress     |
| `/api/scrape/stop`    | Stop running task  |
| `/api/scrape/history` | View previous jobs |

### Export

| Endpoint          | Purpose            |
| ----------------- | ------------------ |
| `/api/export/csv` | Download usage CSV |

---

## 🧰 Common Fixes

### Session Problems

Delete the saved session folder and authenticate again:

```text
data/session/
```

### Browser Missing

```bash
playwright install chromium
```

### Empty Results

Check application logs. Starlink may have changed internal page structures or API responses.

### Port Conflict

Modify the port in your `.env` file:

```env
PORT=8080
```

---

## 📄 Disclaimer

This project is an independent utility created for personal data monitoring and analysis. It is not affiliated with, endorsed by, or maintained by SpaceX or Starlink.

Starlink® is a registered trademark of SpaceX.
