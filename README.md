<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:152238,100:3D6EA5&height=220&section=header&text=Student%20Risk%20Dashboard&fontSize=46&fontColor=ffffff&fontAlignY=38&desc=Live%20Early-Intervention%20Dashboard%20%E2%80%94%20Not%20a%20Mock-Up&descAlignY=58&descSize=17&animation=fadeIn" width="100%"/>

<img src="https://readme-typing-svg.demolab.com/?font=Cambria&size=21&duration=3000&pause=1000&color=3D6EA5&center=true&vCenter=true&width=700&lines=Real+Inputs.+Real+API+Call.+Real+Prediction.;Powered+by+a+Tuned+Random+Forest+Regressor;No+Fake+Data.+No+Static+Demo.+Genuinely+Live.;%F0%9F%8E%93+Built+for+Asansol+Engineering+College" alt="Typing SVG" />

<br/>

[![Live Demo](https://img.shields.io/badge/🟢_LIVE_DEMO-Visit_Now-2E7D6B?style=for-the-badge)](https://dropout-dashboard-static.onrender.com/)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](#)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](#)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](#)
[![Render](https://img.shields.io/badge/Hosted_on-Render-46E3B7?style=for-the-badge&logo=render&logoColor=white)](https://render.com/)

<img src="https://img.shields.io/badge/Backend-Flask_API-000000?style=flat-square" />
<img src="https://img.shields.io/badge/Model-Random_Forest-D9A441?style=flat-square" />
<img src="https://img.shields.io/badge/Status-Live-success?style=flat-square" />

</div>

<br/>

## 🖥️ What Is This?

A clean, multi-page dashboard that lets anyone — counsellor, teacher, curious visitor — type in a few real student attributes and get back a **genuine, live-computed Dropout Risk Score**, straight from a trained Random Forest model running on a real backend.

No static demo. No "simulated heuristic." No fake JSON sitting in a JS file pretending to be a model. 🙅‍♀️

**This dashboard sends real input → hits a real Flask API → gets a real prediction → shows you a real risk category.** We verified it ourselves: the same input run through this dashboard and run directly inside the source Colab notebook produces *identical* numbers. 🔬✅

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=0:EEF2F8,100:EEF2F8&height=2&section=header" width="100%"/>
</div>

## 📑 Table of Contents

- [🎬 See It Live](#-see-it-live)
- [✨ Pages & Features](#-pages--features)
- [🏗️ How It Actually Works](#️-how-it-actually-works)
- [📁 Repository Structure](#-repository-structure)
- [⚙️ Running It Locally](#️-running-it-locally)
- [🔗 Related Repository](#-related-repository)
- [😴 A Note on Cold Starts](#-a-note-on-cold-starts)
- [👥 Team](#-team)
- [📜 License](#-license)

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=0:EEF2F8,100:EEF2F8&height=2&section=header" width="100%"/>
</div>

## 🎬 See It Live

<div align="center">

### 👉 [dropout-dashboard-static.onrender.com](https://dropout-dashboard-static.onrender.com/) 👈

*(give the API ~20 seconds to wake up on first load — free hosting naps when nobody's visiting 😴)*

</div>

## ✨ Pages & Features

| Page | What it does |
|---|---|
| 📝 **Assess a Student** | Enter age, admission grade, previous qualification grade → get a **live** Random Forest prediction with a Low / Medium / High badge |
| 📂 **Student Directory** | Browse illustrative student records |
| 📊 **Risk Analytics** | Visual breakdown of risk distribution |
| 🔍 **Data Quality** | See exactly what noise was injected and how it was cleaned |
| ⚖️ **Model Comparison** | All 5 regression models, side by side, real metrics |
| 📝 **Project Notes** | The full story behind the methodology |

```
┌──────────────────────────────────────────┐
│  🎓 Enter: Age · Admission Grade · Prev Grade │
│                    │                         │
│                    ▼                         │
│        🌐  POST /predict  (Flask API)        │
│                    │                         │
│                    ▼                         │
│      🌲  Tuned Random Forest (R²=0.830)      │
│                    │                         │
│                    ▼                         │
│   📊  Risk Score + Low/Medium/High Category   │
└──────────────────────────────────────────┘
```

## 🏗️ How It Actually Works

1. 🧑‍🎓 You fill in 3 real fields on the **Assess a Student** page
2. 📡 The page sends a `fetch()` POST request to the live Flask API (hosted separately — see [`Dropout-Risk`](https://github.com/KK-Dev0/Dropout-Risk))
3. 🧠 The API loads the exact pickled Random Forest, fills in the other 27 features with training-set medians, and predicts
4. 📬 You get back real JSON: `{ "score": 23.1, "category": "Low" }`
5. 🎨 The dashboard renders it with a spinner, a color-coded badge, and zero fakery

## 📁 Repository Structure

```
Dropout-Dashboard-Static/
├── 🏠 index.html          # entry point
├── 🎨 css/
│   └── style.css          # theme, cards, spinner, responsive layout
├── ⚡ js/
│   ├── app.js              # page logic + the real fetch() call to the API
│   ├── data.js              # illustrative student directory data
│   └── views.js             # page templates & copy
└── 📘 README.md           # you are here 👋
```

## ⚙️ Running It Locally

No build step, no `npm install`, no drama — it's plain HTML/CSS/JS. 🎉

```bash
# 1️⃣ Clone it
git clone https://github.com/KK-Dev0/Dropout-Dashboard-Static.git
cd Dropout-Dashboard-Static

# 2️⃣ Just open it
open index.html        # macOS
# or double-click index.html on Windows/Linux
```

> ⚠️ The **Assess a Student** page calls a live hosted API by default. Point `API_BASE_URL` in `js/app.js` at your own locally running Flask API (see the [`Dropout-Risk`](https://github.com/KK-Dev0/Dropout-Risk) repo) if you want fully offline predictions.

## 🔗 Related Repository

<div align="center">

🧠 **Model, notebook & Flask API live here** → [`KK-Dev0/Dropout-Risk`](https://github.com/KK-Dev0/Dropout-Risk)

</div>

## 😴 A Note on Cold Starts

This dashboard talks to an API hosted on Render's **free tier**, which suspends after inactivity. The first prediction after a quiet period can take 20–30 seconds while the server wakes up. The dashboard tells you this directly instead of pretending to hang — we'd rather be honest than smooth. 🫡

## 👥 Team

<div align="center">

| 👩‍💻 | Department |
|---|---|
| Swastika Banerjee | CSBS |
| Kripa Das | CSBS |
| Ankita Kundu | BCA |
| Kaushikee Karmakar | BCA |

**Mentor:** Prof. Arnab Chakraborty · Asansol Engineering College 🏫

</div>

## 📜 License

Released under the MIT License — see [`LICENSE`](./LICENSE) for details.

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:3D6EA5,100:152238&height=120&section=footer"/>

**⭐ Star this repo if you believe early intervention should actually ship, not just get graded.**

</div>
