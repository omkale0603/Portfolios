# Om Nagnath Kale - Engineering Sketchbook Portfolio

A handcrafted, high-performance portfolio website built for **Om Nagnath Kale** — Artificial Intelligence & Data Science Student, Python & SQL Developer, and Data Analyst.

Featuring a **Hand-Drawn Engineering Sketchbook** visual identity on warm drawing paper (`#F7F4EC`) with graphite typography, engineering-blue accents, and technical diagrams.

Migrated from React/Vite to a clean, production-ready **Single-File Python Flask Application** (`app.py`) using **Flask + Jinja2 + HTML5 + CSS3** with **zero custom JavaScript**.

---

## 🏗️ Architecture & Technology Stack

| Layer | Implementation |
| :--- | :--- |
| **Complete Application** | **Single Python file: [`app.py`](./app.py)** |
| **Backend & Routing** | Python 3.x, Flask, Jinja2 template rendering (`render_template_string`) |
| **Data Layer** | Centralized Python dictionaries & lists embedded in `app.py` |
| **Frontend & Styling** | Embedded HTML5 & CSS3 (Tailwind utility system + bespoke sketchbook classes) |
| **Interactions** | 100% Pure CSS (role ticker, scrollbar, mobile toggle, hover effects) — **Zero Custom JavaScript** |
| **Form Processing** | Server-side Python validation, honeypot spam protection, flash status alerts |
| **Production WSGI** | Gunicorn (included in `requirements.txt` & `Procfile`) |

---

## 📁 Final Project Structure

```
portfolio/
├── app.py                     # Single-file Flask app (all application logic, data, HTML & CSS)
├── requirements.txt           # Python dependencies (Flask, requests, gunicorn)
├── Procfile                   # WSGI server command for cloud deployments
├── .env.example               # Environment variables template
├── .gitignore                 # Ignored files (pycache, env, logs)
├── README.md                  # Project documentation
├── start_portfolio.bat        # Windows one-click launcher
├── contact_messages.json      # Persistent local record of contact form submissions
└── static/                    # Canonical image and document assets
    ├── images/
    │   └── mep.jpeg           # Profile photograph (single canonical copy)
    └── assets/
        └── resume.pdf         # Academic resume PDF (single canonical copy)
```

---

## 🚀 Running the Application Locally

### 1. Install Dependencies
```bash
pip install -r requirements.txt
```

### 2. Start the Server
```bash
python app.py
```
Or run the helper script on Windows:
```cmd
start_portfolio.bat
```

### 3. Open in Browser
* **Portfolio Website**: [http://localhost:5000/](http://localhost:5000/)
* **Server Health Status**: [http://localhost:5000/api/status](http://localhost:5000/api/status)
* **Profile Data API**: [http://localhost:5000/api/profile](http://localhost:5000/api/profile)

---

## 🛠️ Customizing Portfolio Data

All personal information, projects, technical skills, coursework, and contact links are organized in sections 2–7 of:

📂 **[`app.py`](./app.py)**

1. **`portfolio_data`**: Central dictionary with identity, tagline, bio, and marginal specs.
2. **`primary_skills` & `secondary_skills`**: Toolbox items and complementary tools.
3. **`projects`**: Featured case studies, tech stacks, and GitHub links.
4. **`journey`**: 8 milestone progression roadmap steps.
5. **`education`**: Degree, college, university, GPA, and coursework tags.
6. **`socials`**: GitHub, LinkedIn, email, and phone contact links.
7. **Resume**: Replace `static/assets/resume.pdf` with your updated PDF.
8. **Photograph**: Replace `static/images/mep.jpeg` with your photograph.

---

## ☁️ Deployment Guide (Python Cloud Platforms)

### Option 1: Render.com (Recommended - Free Tier)
1. Push this repository to GitHub.
2. Go to [Render.com](https://render.com) and create a **New Web Service**.
3. Connect your GitHub repository.
4. Set:
   * **Runtime**: `Python 3`
   * **Build Command**: `pip install -r requirements.txt`
   * **Start Command**: `gunicorn app:app`
5. Click **Deploy Web Service**!

### Option 2: Railway.app
1. Push this repository to GitHub.
2. Go to [Railway.app](https://railway.app) and create a **New Project** from GitHub repo.
3. Railway automatically detects `Procfile` / `requirements.txt` and runs `gunicorn app:app`.

### Option 3: PythonAnywhere / VPS
1. Clone the repository.
2. Create a virtual environment and install `requirements.txt`.
3. Configure WSGI pointing to `app:app`.

### Option 4: GitHub Pages (Static Snapshot)
1. Push this repository to GitHub on branch `main` or `master`.
2. The included GitHub Actions workflow ([`.github/workflows/deploy.yml`](./.github/workflows/deploy.yml)) automatically builds a static HTML/CSS snapshot with `python app.py --export-static` and deploys it to GitHub Pages.

