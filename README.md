# 202449720-NorahAljammaz-assignment1 
# Personal Protfolio
## Project Description
This is my personal portfolio website, built for Assignment 1 of SWE 206. It introduces
me, showcases two of my real projects — **Breaker** (a campus social app concept) and
**Darsi** (an on-demand tutor marketplace) — and provides a way to get in touch. It's
built with plain HTML, CSS, and JavaScript (no framework), and is responsive across
desktop, tablet, and mobile.

**Sections included:**
- **About Me** — short intro, tagline, and profile photo
- **Projects** — Breaker and Darsi, with descriptions, live design links, and preview images
- **Skills** — a quick list of tools and strengths
- **Contact** — a form (front-end only) plus direct email, phone, and LinkedIn links

**Interactive features (JavaScript):**
- Dark / light theme toggle (saved between visits with `localStorage`)
- Time-of-day greeting message ("Good morning / afternoon / evening")
- Mobile hamburger navigation menu
- Contact form validation with inline feedback

## Folder Structure
```
assignment-1/
├── README.md
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── script.js
├── assets/
│   └── images/
├── docs/
│   ├── ai-usage-report.md
│   └── technical-documentation.md
└── .gitignore
```

## Setup Instructions (Run Locally)
No build tools or installations are required.

1. Clone this repository:
   ```
   git clone https://github.com/<your-username>/202449720-NorahAljammaz-assignment1.git
   ```
2. Open the project folder.
3. Double-click `index.html` to open it in your browser, **or** use a live-reload tool
   such as the VS Code "Live Server" extension for automatic refresh while editing.

That's it — everything runs entirely in the browser.
## AI Use Summary
I used a few AI tools throughout this project, each for a different part:
- **Claude** generated the initial site template (HTML/CSS/JS structure) as a starting
  point, and I later used it again for a final review pass that caught a few things I'd
  missed.
- **Gemini** helped write my project descriptions and generated my logo image.

I reviewed and edited everything the AI produced — fixing broken or mismatched code,
rewriting content to reflect my actual work, and adjusting the styling myself. AI sped
up the process significantly, but it didn't get everything right on its own; figuring
out how the files linked together correctly was something I had to work through myself.
Full details, including the specific benefits, challenges, and how I verified the
output, are in [`docs/ai-usage-report.md`](docs/ai-usage-report.md).
