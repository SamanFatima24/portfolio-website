# Personal Portfolio Website &mdash; Web Engineering Assignment 1

A modern, responsive, professional student portfolio website engineered using **pure HTML5 and CSS3 only** (Zero JavaScript, Zero Frameworks).

---

## Project Overview

- **Project Title:** Personal Portfolio Website
- **Course:** Web Engineering (CS-312)
- **Author:** Saman Fatima
- **Technology Stack:** Pure HTML5 &amp; CSS3
- **Repository URL:** [https://github.com/SamanFatima24/portfolio-website](https://github.com/SamanFatima24/portfolio-website)

---

## Key Features

1. **10 Dedicated Semantic Pages:**
   - `index.html` &mdash; Welcome hero area, bio highlights, stats, and project showcases.
   - `about.html` &mdash; Detailed background, engineering values, goals, and personal interests.
   - `skills.html` &mdash; Technical proficiencies with animated CSS skill bars and soft skill cards.
   - `education.html` &mdash; Clean academic timeline, university degree info, honors, and coursework tags.
   - `projects.html` &mdash; 6 academic and personal projects with technical tags and feature lists.
   - `services.html` &mdash; Frontend engineering offerings, checklists, and 4-step workflow roadmap.
   - `gallery.html` &mdash; Responsive 3-column media grid with pure CSS `:target` modal lightboxes.
   - `blog.html` &mdash; 3 in-depth technical articles on HTML semantics, CSS layouts, and pure CSS techniques.
   - `contact.html` &mdash; Campus lab address, contact details, and an accessible HTML contact form.
   - `faq.html` &mdash; Interactive pure CSS accordion FAQ powered by native `<details>` and `<summary>`.

2. **Zero JavaScript Interactivity:**
   - **Pure CSS Mobile Navigation:** Uses the checkbox hack (`<input type="checkbox" id="nav-toggle">` + `.nav-toggle:checked ~ .site-nav`) to toggle the mobile menu and animate the hamburger icon into an "X".
   - **Pure CSS Modal Lightbox:** Uses the CSS `:target` pseudo-class for full-screen image inspection on the Gallery page.
   - **Pure CSS Accordions:** Styled `<details>` and `<summary>` tags with animated indicator icons.
   - **Pure CSS Form Submission Feedback:** Uses `:target` pseudo-class to render a success banner upon form submission.

3. **Design System & Styling:**
   - Harmonious color palette: Deep navy blue (`#0f172a`), purple (`#6366f1`), cyan (`#0ea5e9`), and clean light surfaces (`#f8fafc`).
   - Reusable CSS custom properties (`:root`) for colors, shadows, border radii, and transitions.
   - Modern layout systems: CSS Grid for 2D multi-column cards and Flexbox for 1D alignments.
   - Full responsiveness across desktop, tablet, and mobile displays via media queries.
   - 100% self-contained vector SVG assets for lightning-fast, offline-ready rendering.

4. **Web Accessibility (WCAG 2.1 AA Compliant):**
   - High color contrast between typography and backgrounds exceeding the 4.5:1 ratio.
   - Visible `:focus-visible` keyboard focus indicators.
   - Explicit `for` and `id` mapping on all form inputs.
   - Semantic HTML5 landmark tags (`<header>`, `<nav>`, `<main>`, `<article>`, `<aside>`, `<footer>`).

---

## File Structure

```
portfolio-website/
├── index.html              # Home Page
├── about.html              # About Me Page
├── skills.html             # Skills & Toolkit Page
├── education.html          # Education Timeline Page
├── projects.html           # Projects Showcase Page
├── services.html           # Web Services Page
├── gallery.html            # Visual Gallery & Lightbox Page
├── blog.html               # Developer Blog Page
├── contact.html            # Contact Page & Accessible Form
├── faq.html                # Frequently Asked Questions Page
├── css/
│   └── style.css           # Master External CSS3 Stylesheet
├── images/                 # Local SVG Asset Directory
│   ├── favicon.svg         # Site Favicon Monogram
│   ├── avatar.svg          # Hero Developer Portrait
│   ├── about-illustration.svg # Workstation Illustration
│   ├── project-1.svg       # EcoTrack Dashboard Preview
│   ├── project-2.svg       # Campus Hub Portal Preview
│   ├── project-3.svg       # AlgoScope Visualizer Preview
│   ├── project-4.svg       # Culinary Craft App Preview
│   ├── project-5.svg       # FocusFlow Timer Preview
│   ├── project-6.svg       # Atmosphere Weather Preview
│   ├── gallery-1.svg       # UI Wireframes Mockup
│   ├── gallery-2.svg       # CSS Design Tokens Graphic
│   ├── gallery-3.svg       # Development Setup Snapshot
│   ├── gallery-4.svg       # Responsive Testing Diagram
│   ├── gallery-5.svg       # Color & Typography System
│   ├── gallery-6.svg       # Demo Day Presentation
│   ├── blog-1.svg          # Semantic HTML Graphic
│   ├── blog-2.svg          # CSS Grid & Flexbox Graphic
│   └── blog-3.svg          # Zero JS Responsive Graphic
├── ARCHITECTURE.md         # Detailed Architectural Notes
└── README.md               # Project Documentation & Setup Guide
```

---

## How to Run the Website Locally

Since the project uses pure HTML5 and CSS3 with no build steps or dependencies, you can run it instantly using any of the following methods:

### Method 1: Direct Browser Opening (Easiest)
1. Navigate to the `portfolio-website/` directory on your computer.
2. Double-click `index.html` (or right-click and choose **Open With > Google Chrome / Firefox / Microsoft Edge**).
3. The website will open immediately with full navigation and responsiveness.

### Method 2: VS Code Live Server
1. Open the `portfolio-website/` folder in Visual Studio Code.
2. If installed, click the **Go Live** button in the bottom status bar (or right-click `index.html` and select **Open with Live Server**).
3. The site will launch at `http://127.0.0.1:5500/index.html`.

### Method 3: Python Built-in HTTP Server
Run the following command in PowerShell / Terminal inside the `portfolio-website/` directory:
```bash
python -m http.server 8000
```
Then visit `http://localhost:8000/` in your browser.

---

## Deployment Instructions (GitHub Pages)

To publish this portfolio online for free using GitHub Pages:

1. **Initialize Git & Push to GitHub:**
   ```bash
   cd portfolio-website
   git init
   git add .
   git commit -m "feat: complete 10-page responsive HTML/CSS portfolio website"
   git branch -M main
   git remote add origin https://github.com/<your-username>/web-engineering-assignment-1.git
   git push -u origin main
   ```

2. **Enable GitHub Pages:**
   - In your GitHub repository, click on **Settings** (top right tab).
   - In the left sidebar under the "Code and automation" section, click **Pages**.
   - Under **Build and deployment > Source**, ensure **Deploy from a branch** is selected.
   - Under **Branch**, select `main` and choose folder `/ (root)`.
   - Click **Save**.

3. **Verify Deployment:**
   - GitHub will build and publish your site in 1 to 2 minutes.
   - Your live website will be available at:
     `https://<your-username>.github.io/web-engineering-assignment-1/`

---

## Submission Checklist for Teachers & Evaluators

- [x] Multi-page architecture with **10 distinct HTML pages**.
- [x] All 10 pages connected via a unified navigation bar and footer.
- [x] Active page indicator on navigation links (`class="nav-link active"`).
- [x] All styles maintained in a single external stylesheet: `css/style.css`.
- [x] Strictly zero JavaScript and zero CSS/JS frameworks.
- [x] Pure CSS mobile hamburger drawer with checkbox hack.
- [x] Pure CSS modal lightboxes using `:target`.
- [x] Pure CSS accordions using `<details>` and `<summary>`.
- [x] Accessible form elements with explicitly matched labels and inputs.
- [x] Responsive layouts tested across desktop, tablet, and mobile resolutions.
- [x] Complete architecture documentation in `ARCHITECTURE.md`.
