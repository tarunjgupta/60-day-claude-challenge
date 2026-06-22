# 🔐 Day 21 — Digital Privacy Dashboard

## #60DayClaudeChallenge | June 22, 2026

---

## 📋 Task Overview

**Objective:** Use Claude AI to generate an interactive **Digital Privacy Dashboard** — a comprehensive HTML-based visualization that analyzes a user's digital footprint across multiple apps and services.

**Effort Level:** High

---

## 🛠️ What Was Built

A single-page, fully interactive **Digital Privacy Dashboard** (`index.html`) featuring:

| Section | Description |
|---------|-------------|
| **Digital Footprint Score** | Overall score (76/100) measuring digital exposure across 15 apps |
| **Privacy Score** | Privacy health rating (31/100) — Grade: C− |
| **Exposure Heatmap** | Color-coded risk tiles for each app (Critical → Low) |
| **Company Exposure Ranking** | Ranked bar chart of 11 parent companies by data exposure |
| **Data Collection Matrix** | What each app collects — location, biometrics, financials, etc. |
| **Risk Radar** | Chart.js radar chart across 6 risk vectors |
| **Ecosystem Breakdown** | Doughnut chart showing app distribution by company |
| **Digital Twin Profile** | Inferred traits algorithms likely know about the user |
| **WOW Insights** | 6 surprising privacy facts based on app usage |
| **Most Valuable Data Assets** | Ranked by commercial value to advertisers |
| **Privacy Improvement Simulator** | Interactive checklist that boosts privacy score in real time |
| **Final Verdict** | Overall grade with actionable recommendations |

---

## 🎨 Design & Tech Stack

- **HTML5 + CSS3 + Vanilla JavaScript** — Single file, no build tools
- **Chart.js 4.4.1** — Radar & doughnut chart visualizations
- **Google Fonts** — Inter (sans-serif) + JetBrains Mono (monospace)
- **Glassmorphism UI** — Frosted glass cards with `backdrop-filter: blur()`
- **Animated Background** — Floating gradient orbs with CSS keyframe animations
- **Scroll Reveal** — IntersectionObserver-driven section animations
- **Animated Counters** — Smooth number counting on load
- **Floating Navigation** — Side dot-nav for quick section jumping
- **Dark Theme** — Carefully curated color palette with semantic risk colors
- **Fully Responsive** — Mobile-friendly with adaptive grid layouts

---

## 📊 Sample Dataset Analyzed

**15 Apps** across **11 Companies:**

| Risk Level | Apps |
|-----------|------|
| 🔴 Critical | TikTok (ByteDance), Google Search (Alphabet) |
| 🟠 High | Instagram, WhatsApp (Meta), Amazon, Google Pay, Snapchat |
| 🟡 Medium-High | YouTube, Google Photos, PUBG Mobile |
| 🟢 Medium | Discord, Spotify, Roblox, Meesho |
| ✅ Low | iMessage (Apple) |

---

## 🧠 Key Learnings

1. **Privacy Analysis** — Claude can analyze digital ecosystems and estimate privacy exposure based on publicly available privacy policies and app store disclosures.

2. **Risk Assessment** — Identifying tracking risks across multiple dimensions: data breadth, cross-app tracking, geolocation, financial exposure, biometrics, and third-party sharing.

3. **Digital Twin Modeling** — Understanding what platforms can infer from your activity: age, location tier, spending habits, content preferences, and cross-app identity linkability.

4. **Actionable Security** — Generating realistic, prioritized privacy improvement plans with measurable impact (e.g., deleting TikTok = +10 points, switching to DuckDuckGo = +8 points).

5. **Interactive Visualization** — Building complex, data-rich dashboards as single HTML files with no dependencies beyond a charting library.

---

## 📁 Files

| File | Description |
|------|-------------|
| `index.html` | Complete interactive Digital Privacy Dashboard |
| `Day21.md` | This documentation file |

---

## 🔗 Links

- **GitHub Repository:** [60-day-claude-challenge](https://github.com/tarunjgupta/60-day-claude-challenge)
- **Challenge:** #60DayClaudeChallenge — Day 21 of 60

---

*Built with Claude AI · Tarunj Gupta · ABES Engineering College · 2026*
