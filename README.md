# The PC Store — IEEE Web Dev Capstone Project

> **IEEE MUST Web Development Committee — Duo CSS Capstone Project**  
> Built with HTML & CSS only. No JavaScript. No frameworks.

---

## Achievement

**2nd Place** — out of all competing teams in the IEEE MUST Web Dev Capstone Competition.

---

## Team

| Role | Name |
|------|------|
| Team Leader | Mohamed Sayed |
| Team Member | Mohamed Abdulaal |

---

## Project Overview

A multi-page e-commerce website for a custom PC store based in Egypt. Users can browse pre-built gaming systems or interactively configure their own PC by selecting slots on a 3D animated motherboard — all driven purely by CSS.

---

## Pages

| Page | File | Description |
|------|------|-------------|
| Home | `index.html` | Landing page with CTA buttons, feature highlights, and store stats |
| Ready PCs | `ready-pcs.html` | Three pre-built system tiers (Entry / Performer / Beast) with modal detail popups |
| Build Your Own PC | `M&M.html` | Interactive CSS-driven PC configurator with live component cart |
| About | `about.html` | Store mission and background |

---

## How to Run

Open `index.html` in any modern browser — no server or build step required.

---

## Tech Stack

- **HTML5** — semantic markup, multi-page structure
- **CSS3** — layouts, animations, 3D transforms, glassmorphism effects

> **IEEE Constraint:** This project uses **HTML and CSS only — no JavaScript whatsoever.**  
> All interactivity (motherboard slot selection, live build cart, modal popups) is implemented purely using CSS checkbox/radio state management and the `:target` pseudo-class.

---

## Features

- Dark gaming aesthetic with cyan/neon accent colors and glow effects
- 3D animated motherboard with floating animation and RGB border glow
- Pure CSS interactive PC builder — click a slot, pick a component, watch it appear in the cart
- CSS-only modal popups for detailed PC specs (`:target` pseudo-class)
- Fully responsive layout with mobile breakpoints at 768px and 400px
- Custom RazerF5 gaming font

---

## Project Structure

```
├── index.html           Home page
├── ready-pcs.html       Pre-built systems listing
├── M&M.html             Interactive PC builder
├── about.html           About page
├── main.css             Unified stylesheet (all pages merged)
└── images/              All product & component images
    ├── Beast.png
    ├── Entry.png
    ├── Performer.png
    └── ...              (CPU, GPU, RAM, storage component images)
```

---

## Competition Rules (Met)

| Rule | Status |
|------|--------|
| HTML & CSS only — no JavaScript | Satisfied |
| No CSS frameworks (Bootstrap, Tailwind, etc.) | Satisfied |
| Custom CSS written from scratch | Satisfied |
| Responsive on laptop, tablet, and mobile | Satisfied |
| Minimum one fully polished page | Satisfied (4 pages) |
