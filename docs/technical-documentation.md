# Technical Documentation

## Overview
A static, single-page portfolio site built with vanilla HTML5, CSS3, and
JavaScript (ES6+). No frameworks, build tools, or backend are used — the
site runs directly in the browser from `index.html`.

## How to Run This Project Locally
No installation, build step, or dependencies are required.

1. Clone or download the repository.
2. Open the project folder on your computer.
3. Double-click `index.html` — it opens directly in your default browser.
   - **Alternative:** open the folder in VS Code and use the "Live Server"
     extension for automatic reload on save while editing.
4. To test responsiveness, open your browser's DevTools (F12 or
   Right-click → Inspect), toggle Device Toolbar, and preview at different
   screen widths (mobile, tablet, desktop).
5. To test the theme toggle, click the moon/sun icon in the navbar — the
   preference is saved in `localStorage`, so it should persist after
   refreshing the page.
6. To test the contact form, fill in all fields and submit — since there's
   no backend, a confirmation message appears inline instead of actually
   sending anything (this is intentional, see "Known Limitations" below).

No environment variables, API keys, or servers are needed — everything runs
client-side in the browser.

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
- The `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
  tag in `index.html` tells the browser to render the page at the device's
  actual width rather than a scaled-down desktop layout — this is what
  makes the responsive CSS below actually take effect on real phones and
  tablets, not just in browser DevTools.

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
- Project preview images are static screenshots/splash screens rather than
  live embeds of the linked Figma prototypes.

## Browser Support
Tested in current versions of Chrome, Firefox, and Edge. Uses standard
CSS Grid/Flexbox and ES6 JavaScript, both widely supported in modern
browsers.
