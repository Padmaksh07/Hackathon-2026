# 🚀 LaunchPad – Student Opportunity & Internship Matching Portal

A clean, full-stack hackathon MVP that matches students with internships, startup roles, and hackathons based on their skills, with match scoring and skill gap analysis.

---

## 📁 Folder Structure

```
opportunity-portal/
├── backend/
│   ├── server.js          # Express API server
│   ├── opportunities.json # Mock dataset (10 opportunities)
│   └── package.json
└── frontend/
    ├── public/
    │   └── index.html
    ├── src/
    │   ├── App.jsx             # Root app + routing
    │   ├── index.js            # Entry point
    │   ├── index.css           # Global styles + design tokens
    │   ├── components/
    │   │   └── UI.jsx          # Shared UI components
    │   ├── pages/
    │   │   ├── Landing.jsx     # Home page
    │   │   ├── Profile.jsx     # Profile + resume upload
    │   │   ├── Dashboard.jsx   # Opportunity listing
    │   │   ├── Detail.jsx      # Opportunity detail + skill gap
    │   │   └── Recommendations.jsx
    │   └── utils/
    │       └── api.js          # API calls
    └── package.json
```

---

## 🚀 How to Run Locally

### Prerequisites
- Node.js 16+ installed
- npm or yarn

### 1. Start the Backend

```bash
cd opportunity-portal/backend
npm install
npm start
# Server runs on http://localhost:3001
```

### 2. Start the Frontend

```bash
cd opportunity-portal/frontend
npm install
npm start
# App opens at http://localhost:3000
```

The frontend is pre-configured to proxy `/api` requests to `localhost:3001`.

---

## ⭐ Features

### 1. Student Profile
- Manual skill input with quick-add suggestions
- Paste resume text → auto skill extraction via keyword matching
- Name + email capture

### 2. Opportunity Dashboard
- 10 curated mock opportunities (internships, startup roles, hackathons)
- Filter by type, search by title/company/skill
- Sort by match score, deadline, or bookmarks
- Visual match score progress bar on each card
- Bookmark functionality

### 3. Matching Algorithm
- Compares student skills to required skills (case-insensitive)
- Calculates match percentage
- Visual progress bar with color coding:
  - 🟢 80%+ = Strong Match
  - 🟡 50–79% = Good Match  
  - 🔴 <50% = Partial Match

### 4. Skill Gap Analysis (Detail Page)
- Shows matched vs missing skills clearly
- Color coded: ✓ green (matched), ✗ red (missing), ◎ yellow (nice to have)
- Animated match score ring

### 5. Recommendations Page
- Top skills to learn ranked by "opportunities unlocked"
- Learning resources (platform, time estimate) for key skills
- "Almost there" opportunities (40-79% match) to target
- 6 actionable career tips

---

## 🛠️ API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/match` | Match all opportunities for a skills array |
| POST | `/api/match/:id` | Match single opportunity |
| POST | `/api/recommendations` | Get skill recommendations |
| POST | `/api/extract-skills` | Extract skills from resume text |

### Example Request

```bash
curl -X POST http://localhost:3001/api/match \
  -H "Content-Type: application/json" \
  -d '{"skills": ["React", "JavaScript", "Node.js"]}'
```

---

## 🎨 Design System

- **Font**: Syne (headings) + DM Sans (body)
- **Theme**: Dark with purple accent (#7c5cfc) + green highlights (#22d3a0)
- **Animations**: Fade-up page entrances, animated progress bars, hover micro-interactions

---

## 🧠 Matching Logic

```javascript
function matchSkills(studentSkills, requiredSkills) {
  const normStudent = studentSkills.map(normalizeSkill); // lowercase, remove spaces
  const matched = requiredSkills.filter(req => normStudent.includes(normalizeSkill(req)));
  const missing = requiredSkills.filter(req => !normStudent.includes(normalizeSkill(req)));
  const score = Math.round((matched.length / requiredSkills.length) * 100);
  return { matched, missing, score };
}
```

Skills are normalized (lowercase, no whitespace/dots) before comparison to handle "Node.js" vs "nodejs" etc.

---

## 📦 Tech Stack

| Layer | Tech |
|-------|------|
| Frontend | React 18, vanilla CSS (no Tailwind needed) |
| Backend | Node.js + Express |
| Data | Mock JSON (no database) |
| Fonts | Google Fonts (Syne + DM Sans) |

---

Built with ❤️ for a 24-hour hackathon.
