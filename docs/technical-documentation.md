# Technical Documentation

## Overview
A static, single-page portfolio site built with vanilla HTML5, CSS3, and
JavaScript (ES6+). No frameworks, build tools, or backend are used — the
site runs directly in the browser from `index.html`.

## Architecture
```
index.html   → structure/content (semantic sections: header, main, footer)
css/styles.css → all styling, using CSS custom properties for theming
js/script.js   → all interactivity, organized into small named functions
```

## Key Technical Decisions

### 1. CSS Custom Properties for Theming
Colors, spacing, and radii are defined once as CSS variables under `:root`,
and overridden under `[data-theme="dark"]`. This means every component
(buttons, cards, form fields) automatically re-colors when the theme
attribute on `<html>` changes — no per-component dark-mode rules needed.

### 2. Responsive Layout
- The hero section and project grid use **CSS Grid** with
  `repeat(auto-fit, minmax(...))` so the project cards reflow automatically
  from a 2-column desktop layout to a single column on mobile, with no
  media query required for that specific grid.
- A single media query at `800px` switches the hero to a stacked layout and
  swaps the horizontal nav for a toggled mobile menu.
- `clamp()` is used for hero typography so font size scales smoothly between
  breakpoints instead of jumping.

### 3. JavaScript Structure
`script.js` is organized into small, single-purpose functions called once
on `DOMContentLoaded`:
- `setupMobileNav()` — toggles the `.open` class on the nav list and updates
  `aria-expanded` for accessibility.
- `setupThemeToggle()` — reads/writes the theme preference to
  `localStorage` so it persists across visits.
- `setGreetingByTime()` — reads `Date().getHours()` to show a morning /
  afternoon / evening greeting.
- `setupContactForm()` — intercepts form submission, validates required
  fields and email format client-side, and shows inline status text. There
  is intentionally no backend — this satisfies the assignment's "no backend
  needed" requirement.

### 4. Accessibility Considerations
- Form inputs are tied to `<label>` elements via `for`/`id`.
- The mobile nav toggle exposes `aria-expanded` state.
- Focus states are visible on interactive elements (`:focus-visible` on
  buttons/links).
- `prefers-reduced-motion` is respected by disabling smooth scroll and hover
  transforms for users who request less motion.

## Known Limitations
- The contact form does not send data anywhere; it's front-end validation
  only, as specified by the assignment.
- Project images use placeholder URLs (`placehold.co`) until real
  screenshots are added to `assets/images/`.

## Browser Support
Tested in current versions of Chrome, Firefox, and Edge. Uses standard
CSS Grid/Flexbox and ES6 JavaScript, both widely supported in modern
browsers.
