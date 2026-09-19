# AI Usage Report

## Tools Used & Use Cases
- **Claude (Anthropic)** — Used to scaffold the initial HTML structure, CSS
  layout (Flexbox/Grid, responsive breakpoints, dark/light theme variables),
  and JavaScript interactivity (theme toggle, mobile nav, time-based
  greeting, form validation). Also used to draft the initial wording for the
  README and this report.
- *(Add any others you personally used, e.g. GitHub Copilot for inline code
  completion while editing, or ChatGPT for debugging a specific CSS issue.
  Delete this line and list only tools you actually used.)*

### Recommended AI Tools (reference)
- GitHub Copilot → code completion & generation
- ChatGPT / Claude → problem-solving & explanations
- Cursor → AI-powered code editor
- Replit → AI-assisted online IDE
- AWS CodeWhisperer → AI code generation

## Benefits & Challenges
**Benefits:**
- Speeding up boilerplate: generating the repeating HTML structure (project
  cards, form fields) and CSS reset/base styles took minutes instead of
  significant manual typing.
- Getting a working responsive layout pattern (CSS Grid for the hero and
  project cards, a mobile breakpoint for the nav) without having to look up
  syntax from scratch.
- Having a second pair of eyes to catch small issues, like missing
  `aria-label`s or inconsistent spacing between sections.

**Challenges:**
- AI-generated content is generic by default — the placeholder copy
  ("Your Name", sample project descriptions) had to be rewritten with real,
  personal content to avoid the site feeling templated.
- Needed to double-check that CSS custom properties (`--accent`, `--bg`,
  etc.) were applied consistently, since AI-suggested edits can sometimes
  create selectors that conflict with earlier rules.
- Had to manually verify the site worked correctly across breakpoints by
  resizing the browser — AI suggestions for "responsive design" are a
  starting point, not a guarantee.

## Learning Outcomes
- Reinforced how CSS custom properties (`:root` variables) can drive a
  dark/light theme toggle cleanly, without duplicating style rules.
- Learned how `localStorage` can persist a user preference (theme) across
  page reloads.
- Practiced writing accessible markup (labels tied to inputs, `aria-expanded`
  on the nav toggle, respecting `prefers-reduced-motion`).
- Improved my workflow for using AI as a *starting draft* rather than a
  final answer — I now habitually re-read and test every AI suggestion
  before committing it.

## Responsible Use & Modifications
- All AI-generated code was read line by line, tested in the browser at
  multiple screen widths, and adjusted where it didn't match my intent
  (e.g., renaming placeholder text, adjusting spacing/colors to my own
  taste, adding code comments in my own words).
- Placeholder project content and images must be replaced with my own real
  projects and screenshots before this is considered a finished portfolio —
  none of the final "About Me" or project copy is presented as final without
  my edits.
- No AI-generated text is submitted as personal reflection without review:
  the sections above were adapted to reflect my actual experience completing
  this assignment.
- Commit history reflects incremental, human-reviewed changes rather than a
  single AI-generated dump, in line with academic integrity expectations.
