# 🧠 Mental Health Survey Dashboard

A responsive, interactive data dashboard visualising descriptive statistics from a global mental health survey of **261,328 respondents** across 17 countries.

**→ [Live Demo](https://your-username.github.io/mental-health-dashboard)**

![Dashboard Preview](preview.png)

---

## 📊 Dataset Overview

| Field | Details |
|-------|---------|
| Total records | 261,328 |
| Countries | 17 (USA, UK, Canada, Netherlands, Ireland, Germany, Australia, India, and more) |
| Columns | 17 (Gender, Occupation, Treatment, Mood Swings, Coping Struggles, etc.) |
| Source | Mental Health in Tech / General population survey |

---

## 🔍 Key Insights

| Insight | Finding |
|---------|---------|
| 🚨 Treatment gap | 50.7% of those with **high mood swings** are untreated |
| ⚖️ Gender disparity | Women 23 pp more likely to seek treatment (69.4% vs 46.4%) |
| 🏥 Care access | Only **1 in 3** has confirmed access to mental health care options |
| 🏠 Social withdrawal | 41% of respondents spent 1–2+ months indoors |
| 📈 Stress | Only 31.5% report *no* increasing stress (68.5% affected) |
| 🧬 Hereditary risk | 38% have a family history of mental illness |

---

## 📈 Dashboard Charts

- **Gender distribution** — Donut chart (88.3% Male / 11.7% Female)
- **Treatment rate by gender** — Stacked bar comparison
- **Occupation breakdown** — Horizontal bar (5 occupation groups)
- **Mood swing severity** — Pie chart (High / Medium / Low)
- **Days spent indoors** — Distribution bar chart
- **Increasing stress levels** — Doughnut chart
- **Care options awareness** — Pie chart
- **Top 8 countries** — Horizontal bar chart
- **6 Key Insight cards** — Colour-coded by severity/type

---

## 🚀 How to Use

### Option 1 — Open locally
```bash
git clone https://github.com/your-username/mental-health-dashboard.git
cd mental-health-dashboard
open index.html   # macOS
# or double-click index.html on Windows/Linux
```

### Option 2 — Deploy to GitHub Pages
1. Fork or push this repo to your GitHub account
2. Go to **Settings → Pages**
3. Set source to `main` branch, `/ (root)`
4. Your dashboard will be live at `https://your-username.github.io/mental-health-dashboard`

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| HTML5 / CSS3 | Structure and styling |
| [Chart.js 4.4](https://www.chartjs.org/) | Interactive charts |
| CSS Custom Properties | Light/dark mode theming |
| Zero dependencies | No build step needed |

---

## 📁 Project Structure

```
mental-health-dashboard/
├── index.html          ← Main dashboard (single file, self-contained)
├── README.md           ← This file
└── Mental_Health_dataset1.csv   ← Source data (add your own)
```

---

## 📋 Descriptive Statistics Summary

| Variable | Distribution |
|----------|-------------|
| Gender | Male 88.3%, Female 11.7% |
| Treatment | Yes 49.1%, No 50.9% |
| Family History | Yes 38%, No 62% |
| Mood Swings | High 31.3%, Medium 34.5%, Low 34.1% |
| Coping Struggles | Yes 46.7%, No 53.3% |
| Increasing Stress | Yes 33.8%, Maybe 34.7%, No 31.5% |
| Care Options | Yes 32.2%, Not sure 26.1%, No 41.7% |
| Days Indoors | Peaks at 1–14 days (22.1% of respondents) |

---

## 🤝 Contributing

Pull requests welcome. If you'd like to add:
- Country-level filtering
- Year-over-year comparison
- Predictive modelling overlay

Please open an issue first.

---

## 📄 Licence

MIT — free to use, adapt, and share with attribution.

---

*Built with Chart.js · Data from mental health survey dataset · Dashboard designed for LinkedIn portfolio sharing*
