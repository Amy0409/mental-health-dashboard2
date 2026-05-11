# 🎯 Prompt: Mental Health Dashboard Generator

This file contains the engineered prompt used to generate this dashboard from raw survey data.
Copy and adapt it for your own datasets.

---

## The Prompt

```
You are a senior data analyst and frontend engineer specialising in public-health visualisation.

I have a CSV dataset of mental health survey responses with 261,328 rows and the following columns:
Gender, Country, Occupation, SelfEmployed, FamilyHistory, Treatment, DaysIndoors,
HabitsChange, MentalHealthHistory, IncreasingStress, MoodSwings, SocialWeakness,
CopingStruggles, WorkInterest, MentalHealthInterview, CareOptions.

Most values are categorical: Yes/No/Maybe, High/Medium/Low, or ordinal ranges like
"1-14 days", "15-30 days", "31-60 days", "More than 2 months", "Go out Every day".

Your task: Build a fully self-contained, single-file HTML dashboard focused on
**descriptive statistics** that can be deployed to GitHub Pages.

─── DATA ANALYSIS REQUIREMENTS ───────────────────────────────────────────────
1. Compute and display these descriptive stats:
   - Total record count
   - Gender distribution (count + %)
   - Treatment rate — overall and broken down by gender
   - Treatment rate by occupation
   - Mood swing severity distribution (High/Medium/Low counts + %)
   - Days Indoors distribution — ordered from least to most isolated
   - Increasing Stress distribution (Yes/No/Maybe counts + %)
   - Care Options availability (Yes/Not sure/No counts + %)
   - Family history prevalence (%)
   - Coping struggles prevalence (%)
   - Top 8 countries by response count
   - Self-employed rate among respondents

2. Derive at least 6 actionable insights, such as:
   - What % of high-mood-swing individuals are untreated?
   - How does treatment-seeking differ between genders?
   - What % of respondents have no access to care?
   - What is the dominant indoor confinement duration?

─── DASHBOARD DESIGN REQUIREMENTS ────────────────────────────────────────────
1. Layout:
   - Sticky header with dataset title, total record count, and country count
   - Row of 4–5 metric cards (KPIs) at the top
   - 2-column responsive chart grid below
   - Full-width charts for distributions with many categories
   - Insight cards section at the bottom (colour-coded: warning/info/good/danger)
   - Footer with data source attribution

2. Charts (use Chart.js 4.x from cdnjs):
   - Donut chart: gender split
   - Stacked bar: treatment rate by gender (as %)
   - Horizontal bar: occupation breakdown (coloured differently per bar)
   - Pie or doughnut: mood swing severity
   - Bar chart: days indoors distribution (ordered logically)
   - Doughnut: increasing stress (Yes/Maybe/No)
   - Pie: care options (Yes/Not sure/No)
   - Horizontal bar: top 8 countries

3. Styling:
   - Respect `prefers-color-scheme` for automatic light/dark mode
   - Use CSS custom properties for all colours and spacing
   - Colour palette: blues for neutral/male, pink/coral for female comparisons,
     red for danger/untreated, amber for warning, green for positive, teal for counts
   - Cards: white background, subtle 0.5px border, 14px border-radius
   - Typography: system-ui font stack; 600 weight for headings; 400 for body
   - Metric cards: muted background, uppercase 10px label, 30px value
   - Responsive: single column on mobile (<640px)

4. Insight cards:
   - Use colour-coded left border: red=danger, blue=info, amber=warning, green=positive
   - Each card has a pill tag (e.g. "Treatment Gap", "Gender Disparity")
   - Short, punchy 1–2 sentence finding with bold key stat

5. Accessibility:
   - Every <canvas> must have role="img" and aria-label describing the chart
   - Fallback text inside <canvas> tags

─── OUTPUT REQUIREMENTS ───────────────────────────────────────────────────────
- Single self-contained index.html file (no external CSS files, no build tools)
- Chart.js loaded from cdnjs.cloudflare.com CDN only
- No framework dependencies (pure HTML/CSS/JS)
- Must work by simply opening index.html in a browser or deploying to GitHub Pages
- All chart data hardcoded from the pre-computed statistics (not loaded from CSV at runtime)
- Include a footer crediting the dataset and Chart.js
```

---

## Prompt Engineering Notes

**Why this prompt works well:**

1. **Role-setting** — Framing as "senior data analyst + frontend engineer" anchors the model
   to produce production-quality output, not a prototype.

2. **Data schema up-front** — Listing all column names and value types prevents the model
   from hallucinating column names or misreading categorical distributions.

3. **Explicit insight derivations** — Rather than asking for "insights", the prompt names
   *specific analytical questions* (e.g. "what % of high mood swing people are untreated?").
   This forces quantitative reasoning rather than generic commentary.

4. **Chart-to-data mapping** — Each chart type is explicitly matched to its data source.
   This prevents the model from choosing inappropriate chart types for categorical data.

5. **Colour semantics** — Specifying "red for danger/untreated, amber for warning" ensures
   the colour encoding carries meaning, not just aesthetic variety.

6. **Constraint: no runtime CSV parsing** — Requiring hardcoded data removes a common
   failure mode (fetch errors, CORS issues on GitHub Pages) and forces pre-analysis.

7. **Accessibility requirements** — Explicitly listing `role="img"` and `aria-label`
   requirements means they don't get omitted in the generated code.

8. **Dark mode** — Specifying `prefers-color-scheme` support results in proper CSS variable
   usage rather than hardcoded colours that break in dark themes.

---

## Adapting for Your Dataset

Replace the column list and computed statistics with your own data.
The structural prompt (layout, chart types, insight format) can remain unchanged.

Key variables to customise:
- `[COLUMN LIST]` — your CSV headers
- `[KEY METRIC 1-5]` — your top-level KPIs
- `[CHART TYPES]` — adjust to match your data's cardinality
- `[INSIGHT QUESTIONS]` — the analytical questions specific to your domain
