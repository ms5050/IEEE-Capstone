# The PC Store — IEEE Capstone Project

A multi-page e-commerce website for a custom PC store based in Egypt. Users can browse pre-built gaming systems or interactively configure their own PC by clicking slots on a 3D animated motherboard.

## Pages

| Page | File | Description |
|------|------|-------------|
| Home | `index.html` | Landing page with CTA buttons, feature highlights, and store stats |
| Ready PCs | `ready-pcs.html` | Three pre-built system tiers (Entry / Performer / Beast) with modal detail popups |
| Build Your Own PC | `M&M.html` | Interactive CSS-driven PC configurator with live build cart |
| About | `about.html` | Store mission and background |

## How to Run

Open `index.html` in any modern browser — no server or build step required.

## Technology

- **HTML5** — semantic markup, multi-page structure
- **CSS3** — layouts, animations, 3D transforms, glassmorphism effects

> **IEEE Course Requirement:** This project uses **HTML and CSS only — no JavaScript**.  
> All interactivity (motherboard slot selection, build cart, modal popups) is implemented purely with CSS checkbox/radio state management and the `:target` pseudo-class.

## Project Structure

```
├── index.html           Home page
├── ready-pcs.html       Pre-built systems listing
├── M&M.html             Interactive PC builder
├── about.html           About page
├── main.css             Single merged stylesheet (all pages)
├── img/                 Pre-built PC product images
│   ├── Beast.png
│   ├── Entry.png
│   └── Performer.png
└── Product-materials/   Component images (CPUs, GPUs, RAM, etc.)
```

## Features

- Dark gaming aesthetic with cyan/neon-green accent colors and glow effects
- 3D animated motherboard with floating and RGB border animations
- Pure CSS interactive PC builder — click a slot, choose a component, see it added to the cart
- CSS-only modal popups for detailed PC specs (`:target` pseudo-class)
- Fully responsive layout with mobile breakpoints at 768px and 400px
- Custom RazerF5 gaming font
