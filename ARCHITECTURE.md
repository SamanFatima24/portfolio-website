# Architecture Documentation

**Course:** Web Engineering (CS-312)  
**Project Title:** Personal Portfolio Website (Assignment 1)  
**Author:** Saman Fatima  
**Technology Restrictions Complied:** 100% Pure HTML5 and CSS3 (Zero JavaScript, Zero Frameworks)

---

## 1. Website Overview & Purpose

This website is a complete, multi-page, responsive student portfolio designed and engineered for **Web Engineering Assignment 1**. The primary objective is to demonstrate proficiency in core web standards:
- Structuring documents using semantic HTML5 elements.
- Styling multi-page layouts using modern CSS3 features without reliance on external CSS frameworks (such as Bootstrap or Tailwind).
- Constructing fluid, mobile-friendly interfaces using CSS Grid and CSS Flexbox.
- Achieving sophisticated interactivity (mobile navigation toggles, modal lightboxes, and collapsible FAQ accordions) strictly using native HTML and CSS techniques without a single line of JavaScript.

---

## 2. Page Inventory & Purpose

The portfolio consists of **10 distinct, fully realized HTML pages**, each serving a specific role:

| # | Page File | Page Title | Purpose & Architectural Role |
|---|---|---|---|
| 1 | `index.html` | Home Page | Entry portal featuring the hero banner, personal introduction, call-to-action buttons, quick highlight cards, and recent showcase snippets. |
| 2 | `about.html` | About Me | Detailed biographical narrative, engineering values, short/long-term goals, and personal interests. |
| 3 | `skills.html` | Skills & Toolkit | Categorized presentation of frontend competencies, CS core concepts, and soft skills using animated CSS progress bars and chips. |
| 4 | `education.html` | Education Timeline | Chronological academic timeline with vertical gradient indicator lines, degrees, coursework tags, and university distinctions. |
| 5 | `projects.html` | Projects Showcase | Curated exhibition of 6 academic and personal projects with technical tags, feature checklists, and action buttons. |
| 6 | `services.html` | Web Services | Description of freelance/academic offerings (HTML authoring, CSS layouts, audits, peer tutoring) and a 4-step workflow roadmap. |
| 7 | `gallery.html` | Visual Gallery | Responsive 3-column grid of design wireframes and workspace previews featuring pure CSS modal lightboxes via `:target`. |
| 8 | `blog.html` | Developer Blog | Three comprehensive articles discussing semantic HTML, CSS Grid vs Flexbox, and zero-JS interactive techniques, complete with code blocks and a sidebar. |
| 9 | `contact.html` | Contact Page | Direct reach information (campus lab, email, phone) alongside an accessible multi-field HTML contact form with CSS-only feedback. |
| 10 | `faq.html` | Frequently Asked Questions | Interactive pure CSS accordion powered by semantic `<details>` and `<summary>` elements addressing design and architecture questions. |

---

## 3. Navigation Architecture

Inter-page navigation is unified and consistent across all 10 pages:
1. **Universal Navigation Bar:** Every page includes identical header markup containing relative links to all 10 pages (`href="index.html"`, `href="about.html"`, etc.).
2. **Current Page Highlighting:** The active page is visually indicated in the navigation using the `class="nav-link active"` attribute. This applies a distinct background tint (`var(--color-purple-light)`), bold weight, and a pure CSS bottom indicator bar.
3. **Logo Connection:** The brand emblem and title link back to `index.html`.
4. **Pure CSS Mobile Navigation (The Checkbox Hack):**
   - On screen viewports under `768px`, navigation links hide into a slide-down mobile menu.
   - An invisible checkbox `<input type="checkbox" id="nav-toggle" class="nav-toggle">` is controlled by a stylized `<label for="nav-toggle">` (the 3-bar hamburger icon).
   - Tapping the label checks the box, triggering the CSS sibling selector:
     ```css
     .nav-toggle:checked ~ .site-nav {
       display: flex;
     }
     ```
   - The hamburger bars transform into an "X" via CSS rotations—achieving a fully functional mobile menu with **zero JavaScript**.

---

## 4. Shared External Stylesheet & Design System

All CSS rules across the entire website reside inside a single external stylesheet: `css/style.css`.
Every HTML document includes the stylesheet in its `<head>`:
```html
<link rel="stylesheet" href="css/style.css">
```

### CSS Custom Properties (`:root` Variables)
Centralizing design tokens in CSS variables guarantees consistent colors, typography, and elevations:
- **Primary Navy / Slate:** `--color-primary: #0f172a`, `--color-primary-light: #1e293b`
- **Purple Brand:** `--color-purple: #6366f1`, `--color-purple-dark: #4f46e5`, `--color-purple-light: #e0e7ff`
- **Accents:** `--color-accent-cyan: #0ea5e9`, `--color-accent-teal: #10b981`, `--color-accent-amber: #f59e0b`
- **Surfaces:** `--bg-page: #f8fafc`, `--bg-card: #ffffff`, `--bg-subtle: #f1f5f9`
- **Elevation Shadows:** `--shadow-sm`, `--shadow-md`, `--shadow-lg`, `--shadow-xl`
- **Transitions:** `--transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1)`

---

## 5. Modern Layout & Interactivity Techniques

### CSS Grid vs. Flexbox Integration
- **CSS Grid (2D Matrix):** Used for multi-column page structures, project catalogs, and gallery grids. Utilizing `grid-template-columns: repeat(3, 1fr)` and fluid `repeat(auto-fit, minmax(280px, 1fr))` creates robust multi-column grids that adapt dynamically.
- **CSS Flexbox (1D Linear Flow):** Used for single-axis alignment: headers, navigation item distribution, button groups, badge rows, and footer alignments.

### Mobile-First Media Queries
Layout responsiveness is controlled via three primary media query breakpoints:
1. `@media (max-width: 1024px)`: Adjusts large hero typography, collapses 4-column grids to 2-column configurations.
2. `@media (max-width: 768px)`: Switches navigation to the pure CSS mobile drawer, aligns content grids to a single vertical column, and adjusts padding.
3. `@media (max-width: 480px)`: Optimizes touch targets and spacing for compact mobile screens.

### Pure CSS Interactivity Highlights (Zero JavaScript)
1. **Interactive Lightbox Modal (`gallery.html`):** Uses the CSS `:target` pseudo-class. Clicking an item (`href="#preview-1"`) activates `.lightbox-modal:target { display: flex; }`. Clicking the close button (`href="#gallery"`) clears the hash and dismisses the modal.
2. **Interactive FAQ Accordions (`faq.html`):** Uses native `<details>` and `<summary>` elements with custom CSS chevron pseudo-elements (`::after`) that rotate on toggle.
3. **Interactive Form Confirmation (`contact.html`):** Uses the form action `action="#submitted"` to display an accessible green success banner via `#submitted:target`.
4. **Smooth Transitions & Micro-Interactions:** Cards elevate on hover (`transform: translateY(-4px); box-shadow: var(--shadow-lg)`), buttons subtly translate, and hero image illustrations float gracefully using `@keyframes float`.

---

## 6. Project Folder Structure

```
portfolio-website/
  ├── index.html          # 1. Home Page
  ├── about.html          # 2. About Me Page
  ├── skills.html         # 3. Skills & Toolkit Page
  ├── education.html      # 4. Education Timeline Page
  ├── projects.html       # 5. Projects Showcase Page
  ├── services.html       # 6. Web Services Page
  ├── gallery.html        # 7. Visual Gallery Page
  ├── blog.html           # 8. Developer Blog Page
  ├── contact.html        # 9. Contact Page & Form
  ├── faq.html            # 10. Frequently Asked Questions Page
  ├── css/
  │   └── style.css       # Unified External CSS3 Stylesheet
  ├── images/             # Vector SVG assets (self-contained & offline-ready)
  │   ├── favicon.svg
  │   ├── avatar.svg
  │   ├── about-illustration.svg
  │   ├── project-1.svg to project-6.svg
  │   ├── gallery-1.svg to gallery-6.svg
  │   └── blog-1.svg to blog-3.svg
  ├── ARCHITECTURE.md     # Engineering architecture documentation
  └── README.md           # Project guide, features, and setup instructions
```

---

## 7. Technology Restrictions Compliance Confirmation

- [x] **HTML5 Only:** 100% semantic HTML5 elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`, `<figure>`).
- [x] **CSS3 Only:** External stylesheet (`css/style.css`) leveraging CSS Grid, Flexbox, Custom Properties, Transitions, and Media Queries.
- [x] **Zero JavaScript:** Exactly 0 `<script>` tags, 0 inline `on*` event handlers, and 0 external JavaScript libraries.
- [x] **Zero Third-Party Frameworks:** Completely devoid of Bootstrap, Tailwind, jQuery, or React.
- [x] **Accessibility:** Form labels explicitly mapped with `for` and `id`, meaningful image `alt` tags, and high-contrast color choices meeting WCAG 2.1 AA standards.
