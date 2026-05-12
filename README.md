<div align="center">

  # The PC Store

  **IEEE MUST Web Development Committee — Duo CSS Capstone Project**

  [![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
  [![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
  [![No JavaScript](https://img.shields.io/badge/JavaScript-None-lightgrey?style=for-the-badge&logo=javascript&logoColor=white)](/)
  [![No Frameworks](https://img.shields.io/badge/Frameworks-None-lightgrey?style=for-the-badge)](/)
  [![Netlify](https://img.shields.io/badge/Deployed%20on-Netlify-00C7B7?style=for-the-badge&logo=netlify&logoColor=white)](https://netlify.com/)
  [![Live](https://img.shields.io/badge/Live%20Site-ieee--must.netlify.app-brightgreen?style=for-the-badge&logo=googlechrome&logoColor=white)](https://ieee-must.netlify.app/)

</div>

---

> **🏆 2nd Place** — IEEE MUST Web Development Capstone Competition, out of all competing teams.

A multi-page e-commerce website for a custom PC store — featuring a **CSS-only interactive PC configurator** built on a 3D animated motherboard, modal popups, and a live build cart, all without a single line of JavaScript.

---

## Team

| Role | Name |
|---|---|
| Team Leader | Mohamed Sayed |
| Team Member | Mohamed Abdulaal |

---

## Project Overview

The PC Store allows users to browse pre-built gaming systems or interactively configure a custom PC by selecting component slots directly on a 3D animated motherboard. Every interactive element — slot selection, component detail panels, live cart updates, and modal popups — is driven **purely by CSS state management**, satisfying the competition's strict no-JavaScript constraint.

**Live Preview:** [https://ieee-must.netlify.app/](https://ieee-must.netlify.app/)

---

## Key Features & Technical Implementation

### 1. CSS-Only Interactive PC Builder

The most technically demanding feature of the project. Users click motherboard slots (CPU, GPU, RAM, Storage, Cooling, Sound Card) and component options appear in a live build cart — with zero JavaScript.

**How it works:**

Hidden `<input type="radio">` and `<input type="checkbox">` elements act as persistent state stores. `<label>` elements styled as UI components trigger them on click. CSS sibling selectors (`~`) propagate that state visually across the page:

```css
/* Hide all inputs — they exist only as state */
input[type="radio"], input[type="checkbox"] { display: none; }

/* When a CPU radio is checked, reveal its cart row */
#c-cpu1:checked ~ .info-panel .cart-panel #cr-cpu1,
#c-cpu2:checked ~ .info-panel .cart-panel #cr-cpu2,
#c-cpu3:checked ~ .info-panel .cart-panel #cr-cpu3 {
    display: flex;
}
```

This pattern is repeated across all component categories (CPU, GPU, RAM, Storage, Cooling, Sound Card), creating a fully stateful UI without a scripting layer. Selecting a component in one panel instantly reflects it in the cart — all via the CSS general sibling combinator.

---

### 2. CSS-Only Modal Popups

Pre-built PC detail modals (Entry / Performer / Beast) are triggered using the CSS `:target` pseudo-class — no `addEventListener`, no `classList.toggle`:

```css
/* Modal is hidden by default */
.modal { display: none; }

/* Becomes visible when its ID matches the URL hash */
.modal:target { display: flex; }
```

Clicking a "View Details" anchor sets the URL hash; the browser matches it to the modal's `id`, and CSS makes it visible. Clicking the close link clears the hash, hiding the modal.

---

### 3. 3D Animated Motherboard

The PC configurator's centerpiece is a CSS `perspective` scene with a motherboard rendered in 3D using `rotateX` / `rotateZ` transforms, a continuous float animation, and an RGB border glow cycle:

```css
.motherboard {
    transform: rotateX(60deg) rotateZ(-45deg);
    transform-style: preserve-3d;
    animation: floatBoard 6s ease-in-out infinite;
}

@keyframes floatBoard {
    0%,100% { transform: rotateX(60deg) rotateZ(-45deg) translateZ(0px); }
    50%      { transform: rotateX(60deg) rotateZ(-45deg) translateZ(15px); }
}

@keyframes rgb-border-anim {
    /* Cycles hue across the full spectrum */
    0%   { border-color: #ff0000; }
    33%  { border-color: #00ff00; }
    66%  { border-color: #0000ff; }
    100% { border-color: #ff0000; }
}
```

Component slot hotspots on the board use a `pulsing` keyframe animation to draw the user's eye, and expand into a detail panel on label activation.

---

### 4. Dark Gaming UI — Pure Custom CSS

- Dark base palette with **cyan/neon accent colors** and glow `box-shadow` effects — no design framework used.
- **Glassmorphism** cards with `backdrop-filter: blur` for the pre-built PC listings.
- Custom **RazerF5** gaming font loaded locally for brand-consistent typography.
- CSS `transition` and `transform: scale` hover states applied consistently across cards, buttons, and nav links.
- `slideIn` keyframe animation for component detail panels:

```css
@keyframes slideIn {
    from { opacity: 0; transform: translateX(-30px); }
    to   { opacity: 1; transform: translateX(0); }
}
```

---

### 5. Responsive Layout — No Framework

- Fully responsive across **laptop, tablet (768px), and mobile (400px)** breakpoints.
- Built entirely with CSS `flexbox` and media queries — no Bootstrap, no Tailwind, no grid framework.
- Navigation, cards, the motherboard scene, and the build cart all reflow correctly at every breakpoint.

---

## Pages

| Page | File | Description |
|---|---|---|
| Home | `index.html` | Landing page with CTA, feature highlights, and store statistics |
| Ready PCs | `ready-pcs.html` | Three pre-built tiers (Entry / Performer / Beast) with CSS modal spec sheets |
| Build Your Own PC | `M&M.html` | Interactive CSS-driven configurator — 3D motherboard, slot selection, live cart |
| About | `about.html` | Store mission and background |

---

## Tech Stack

<div align="center">

| Layer | Technology |
|---|---|
| **Markup** | HTML5 (semantic, multi-page) |
| **Styling & Interactivity** | CSS3 — custom, from scratch |
| **Animations** | CSS `@keyframes`, `transform`, `transition` |
| **State Management** | CSS `:checked` + sibling selectors, `:target` pseudo-class |
| **Typography** | Custom RazerF5 gaming font |
| **Deployment** | Netlify |
| **JavaScript** | None |
| **CSS Frameworks** | None |

</div>

<br/>

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![Netlify](https://img.shields.io/badge/Netlify-Deployed-00C7B7?style=flat-square&logo=netlify&logoColor=white)

---

## Project Structure

```
├── index.html           Home page
├── ready-pcs.html       Pre-built systems listing
├── M&M.html             Interactive PC builder (configurator)
├── about.html           About page
├── main.css             Unified stylesheet — all pages, all components
└── images/              Product & component images
    ├── Beast.png
    ├── Entry.png
    ├── Performer.png
    ├── Board.png        Motherboard graphic
    └── ...              CPU, GPU, RAM, storage, cooling, sound card images
```

---

## Competition Rules

| Constraint | Status |
|---|---|
| HTML & CSS only — no JavaScript | ✅ Satisfied |
| No CSS frameworks (Bootstrap, Tailwind, etc.) | ✅ Satisfied |
| All CSS written from scratch | ✅ Satisfied |
| Responsive on laptop, tablet, and mobile | ✅ Satisfied |
| Minimum one fully polished page | ✅ Satisfied — 4 pages delivered |

---

<div align="center">
  <sub>IEEE MUST Web Development Committee &nbsp;·&nbsp; Capstone Competition &nbsp;·&nbsp; 2nd Place &nbsp;·&nbsp; 2026</sub>
</div>
