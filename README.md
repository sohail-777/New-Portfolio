# Shaik Sohail Ahmmad — Portfolio

A futuristic, fully responsive personal portfolio for **Shaik Sohail Ahmmad**, Full-Stack Developer · Software Engineer and AI/ML enthusiast. The whole site is a single self-contained `index.html` file with no build step, no framework and no dependencies to install.

---

## Table of Contents

- [Highlights](#highlights)
- [Sections](#sections)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Deployment](#deployment)
- [Customization](#customization)
- [Responsiveness](#responsiveness)
- [Accessibility](#accessibility)
- [Browser Support](#browser-support)
- [Contact](#contact)

---

## Highlights

- **Animated network background** — a canvas-drawn field of drifting nodes that connect with glowing lines when they get close to each other.
- **Typing terminal hero** — a terminal window that types out `whoami`, `cat skills.json`, current status and education, ending with a blinking cursor.
- **Scroll-reveal animations** — every section and card fades and slides in as it enters the viewport (IntersectionObserver).
- **Scroll progress bar** — a thin gradient bar at the top of the page tracks reading progress.
- **Hover effects everywhere** — cards lift, glow and change border color; skill pills light up; nav links get animated underlines; buttons emit a soft glow.
- **Glassmorphism navbar** — a fixed, blurred header with a hamburger menu on small screens.
- **Dark neon theme** — deep navy background with mint (`#4dffc4`) and violet (`#8d7bff`) accents.
- **Fully static** — open the file and it works. No server required.

---

## Sections

| # | Section | What it shows |
|---|---------|---------------|
| – | **Hero** | Name, role, short intro, call-to-action buttons, quick links (phone, email, LinkedIn, GitHub) and the animated terminal |
| 01 | **About** | Professional summary and stat cards (CGPA, internships, projects, LeetCode problems solved) |
| 02 | **Skills** | Eight skill categories: Languages, Frontend, Backend, AI/ML, Tools, Testing, Core Concepts, Soft Skills |
| 03 | **Experience** | Timeline of three internships — S3D Technologies, Intrainz (virtual) and Ediglobe (virtual) |
| 04 | **Projects** | SkillSwap, SEMS, WordWeaver and SymptTrack, each with description, tech tags and its own GitHub link |
| 05 | **Education** | B.Tech CSE (IARE, Hyderabad) and Intermediate MPC (Sri Chaitanya Junior College, Ongole) |
| 06 | **Certificates** | Certifications, workshops, conference presentations, internship and course completions |
| 07 | **Coding Profiles** | LeetCode, HackerRank, CodeChef and GeeksforGeeks handles and stats |
| 08 | **Contact** | Email, LinkedIn, GitHub and phone buttons |

### Experience

| Role | Company | Period | Mode |
|------|---------|--------|------|
| Software Engineer Intern | S3D Technologies Pvt Ltd | May 2026 – Nov 2026 | — |
| Web Development Intern | Intrainz | Sep 2024 – Nov 2024 | Virtual |
| Machine Learning Intern | Ediglobe | May 2024 – Jun 2024 | Virtual |

### Projects

| Project | Stack | Date | Repository |
|---------|-------|------|------------|
| **SkillSwap** — MERN app with chat, scheduling, real-time skill matching, file uploads | MongoDB, Express.js, React.js, Node.js, Framer Motion | Jul 2026 | [GitHub](https://github.com/sohail-777/SkillSwap) |
| **SEMS** — Smart Event Management System with seat allocation and admin analytics (20+ REST APIs) | React.js, MySQL, Node.js, Express.js, HTML | May 2026 | [GitHub](https://github.com/sohail-777/SEMS---Smart-Event-Management-System) |
| **WordWeaver** — Text-to-image generator (10 RESTful APIs, JWT auth) | React.js, Node.js, MongoDB, Tailwind CSS | Jun 2025 | [GitHub](https://github.com/sohail-777/WordWeaver_AI_SAAS_Application) |
| **SymptTrack** — AI-powered symptom tracking with a diagnosis prediction model (8 APIs) | Flask, Python, CSS, JavaScript, MySQL, HuggingFace, Machine Learning | Mar 2024 | [GitHub](https://github.com/sohail-777/SymptTrack) |

---

## Tech Stack

**Built with**

- HTML5 (semantic sections, inline SVG icons)
- CSS3 (custom properties, Grid, Flexbox, keyframe animations, `backdrop-filter`)
- Vanilla JavaScript (Canvas API, IntersectionObserver, DOM scripting)

**Fonts** (loaded from Google Fonts)

- [Space Grotesk](https://fonts.google.com/specimen/Space+Grotesk) — headings
- [Inter](https://fonts.google.com/specimen/Inter) — body text
- [JetBrains Mono](https://fonts.google.com/specimen/JetBrains+Mono) — terminal, labels and code-style accents

No frameworks, libraries, bundlers or package managers are used.

---

## Project Structure

```
.
├── index.html   # The entire site: markup, styles and scripts
└── README.md    # This file
```

Inside `index.html`, the code is organized top to bottom as:

1. `<style>` — design tokens (CSS variables), layout helpers, then one block per section
2. `<body>` — background layers, navbar, and each section in page order
3. `<script>` — mobile menu, scroll progress, reveal-on-scroll, terminal typing effect, background canvas

---

## Getting Started

### Option 1 — Open directly

Double-click `index.html` to open it in your browser.

### Option 2 — Local server (recommended)

```bash
# Python
python3 -m http.server 8000

# or Node.js
npx serve .
```

Then visit `http://localhost:8000`.

---

## Deployment

Because the site is a single static file, it can be hosted almost anywhere.

**GitHub Pages**

1. Create a repository and push `index.html` and `README.md`.
2. Go to **Settings → Pages**.
3. Under **Source**, choose the `main` branch and the `/ (root)` folder, then save.
4. Your site will be live at `https://<username>.github.io/<repo>/`.

**Netlify**

Drag and drop the folder onto [app.netlify.com/drop](https://app.netlify.com/drop), or connect the repository. No build command is needed; the publish directory is the project root.

**Vercel**

Import the repository at [vercel.com/new](https://vercel.com/new). Use the **Other** framework preset with no build command.

---

## Customization

### Change colors

All colors are CSS variables at the top of the `<style>` block:

```css
:root{
  --bg:#060a12;          /* page background */
  --panel:#0d1424;       /* card background */
  --accent:#4dffc4;      /* primary accent (mint) */
  --accent-2:#8d7bff;    /* secondary accent (violet) */
  --text:#e9edf6;        /* main text */
  --text-dim:#8b99b8;    /* secondary text */
}
```

### Edit the terminal

The hero terminal reads from the `terminalLines` array in the script block. Each entry is either a `prompt` (the typed command) or an `out` (the printed output):

```js
{ type: 'prompt', text: '> cat skills.json' },
{ type: 'out',    text: '[ ... ]' },
```

### Add a project

Copy an existing `.project-card` block inside the `#projects` section, then update the title, date, description, tags and the `href` of its `project-link`.

### Add a skill

Add a `<span class="pill">Your Skill</span>` to the relevant `.skill-card`.

### Tune the background

In the script, `NODE_COUNT` controls how many nodes are drawn (fewer on mobile by default), and the `150` in the distance check controls how far apart two nodes can be and still connect.

---

## Responsiveness

The layout adapts across three breakpoints:

| Width | Behavior |
|-------|----------|
| > 920px | Two-column hero and about sections, full navbar |
| ≤ 920px | Single-column layout, terminal moves above the intro, hamburger menu replaces nav links |
| ≤ 560px | Tighter padding and spacing, header CTA hidden, stacked timeline headings |

Card grids use `repeat(auto-fit, minmax(...))`, so they reflow automatically between one and several columns. The background network also uses fewer nodes on narrow screens for better performance.

---

## Accessibility

- Semantic landmarks (`header`, `nav`, `main`, `section`, `footer`)
- Visible keyboard focus outlines on links and buttons
- `aria-label` on the menu toggle
- External links use `rel="noopener"`
- Respects `prefers-reduced-motion`: animations and transitions are effectively disabled, content is shown immediately and the background stops animating

---

## Browser Support

Works in current versions of Chrome, Edge, Firefox and Safari. It relies on CSS Grid, CSS variables, `backdrop-filter`, the Canvas API and IntersectionObserver.

---

## Contact

**Shaik Sohail Ahmmad**

- Email: [shaiksohail6301295637@gmail.com](mailto:shaiksohail6301295637@gmail.com)
- Phone: +91 6301295637
- LinkedIn: [linkedin.com/in/shaik-sohail-ahmmad](https://linkedin.com/in/shaik-sohail-ahmmad)
- GitHub: [github.com/sohail-777](https://github.com/sohail-777)

Coding profiles: LeetCode `sohailahmmad` · HackerRank `shaiksohail777` · CodeChef `shaiksohail777` · GeeksforGeeks `22951a4ryu`

---

© 2026 Shaik Sohail Ahmmad. All rights reserved.
