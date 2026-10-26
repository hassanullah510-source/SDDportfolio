# AGENTS.md

Guidance for AI agents and contributors working on this repository.

## Project overview

Personal portfolio for **Hassan Ullah**, a Full Stack / JavaScript developer.
It is a **single-file static website**: all markup, CSS, and JavaScript live in
`index.html`. There is no framework, bundler, package manager, test suite, or
build step.

- Live content owner: Hassan Ullah (`hassanullah510@gmail.com`)
- Repo: `https://github.com/hassanullah510-source/my-portfolio`
- Default branch: `main`

## Repository layout

```
index.html    # The entire site: HTML + <style> + <script>
AGENTS.md     # This file
spec driven/  # Empty; reserved for spec-driven development notes
```

`C:\Users\Hassan Ullah\Desktop\Hassan Ullah _ Portfolio.html` is a standalone
copy of `index.html`, not part of this repo. Do not edit it unless asked.

## Running locally

No install is required. Either:

- Open `index.html` directly in a browser, or
- Serve the folder for a realistic environment:

```powershell
# from the repo root, any static server works
npx serve .
# or
python -m http.server 8000
```

Then visit the printed URL. Refresh the page after edits; there is no HMR.

## Architecture

`index.html` is intentionally ordered top-to-bottom:

1. `<head>`: meta, Google Fonts (Sora, Manrope), and one large `<style>` block.
2. `<body>`: decorative background, fixed header/nav, `<main>` with sections,
   footer, back-to-top button, toast container.
3. One `<script>` block at the end containing data and behavior.

Sections (ids are used by nav links, footer links, and scroll-spy):

| id           | Section        |
| ------------ | -------------- |
| `#home`      | Hero           |
| `#about`     | About + stats  |
| `#skills`    | Skills         |
| `#projects`  | Projects       |
| `#experience`| Experience     |
| `#services`  | Services       |
| `#contact`   | Contact        |

### JavaScript structure

The script is plain ES6+ and runs in the global scope, in this order:

- `$` — tiny `querySelector` helper.
- `skills` — array of `[name, percent]`; rendered into `#skillGrid`.
- `projects` — array of `[title, description, tags[], gradient, icon]`;
  rendered into `#pjGrid`.
- `svc` — array of `[icon, title, description]`; rendered into `#svcGrid`.
- `toast()` — transient message used by placeholder "Live Demo" links.
- Mobile menu (`#burger`, `#links`, Escape key).
- `IntersectionObserver` for `.rv` reveal animations and skill-bar widths.
- Second `IntersectionObserver` for active nav highlighting.
- Contact form validation, then a `mailto:` handoff.
- Scroll progress bar (`#prog`) and back-to-top button (`#top`).
- Typed rotating phrases in the hero (`#ty`), disabled under reduced motion.

## Content editing guide

Most routine changes are data edits, not markup edits:

- **Skills**: edit the `skills` array (line ~280).
- **Projects**: edit the `projects` array (line ~282). Each entry is
  `[title, description, [tags], "css-gradient", "icon text"]`.
  Replace the placeholder `href="#projects"` / `https://github.com/` links in
  the render template with real project and repo URLs.
- **Services**: edit the `svc` array (line ~290).
- **About copy and stats**: edit the `#about` section markup.
- **Experience timeline**: edit the `.tl` block in `#experience`.
- **Hero copy**: `#home` section; typed phrases are in `ph` (line ~331).
- **Contact email**: appears in the `mailto:` links and in the form handler—
  update **all three** occurrences if it changes.
- **Social links**: the footer links are placeholders
  (`https://github.com/`, `https://www.linkedin.com/`, `https://x.com/`).
- **Portrait**: the hero image is an inline base64 JPEG. Prefer replacing it
  with a normal file (for example `assets/portrait.jpg`) referenced via `src`,
  which keeps `index.html` readable.

## Conventions

- Keep the site a **single self-contained `index.html`** unless there is a
  strong reason to split files. If assets are added, use a top-level
  `assets/` folder and relative paths.
- No frameworks, no npm dependencies, no build output.
- Match the existing terse style: two-space indentation, semicolon-terminated
  JS, short single-purpose functions, template literals for rendering.
- Use the existing design tokens in `:root` (`--bg`, `--tx`, `--mu`, `--b`,
  `--p`, `--c`, `--k`, `--g`, `--gl`, `--bd`) instead of new hard-coded colors.
  Accent gradient: `linear-gradient(120deg, #4f7cff, #9b5cff, #ff4fa3)`.
- Reuse utility classes: `.wrap`, `.glass`, `.btn.pri`, `.btn.sec`, `.title`,
  `.sub`, and `.rv` (scroll reveal).
- Add `.rv` to new blocks that should animate in; the observer assigns stagger
  delays automatically.
- Preserve accessibility behavior: `aria-label` on icon-only links, `alt` text
  on images, `aria-expanded` on the burger, `role="status"` on live regions,
  visible `:focus-visible` outlines, and preserved keyboard operability.
- Respect `prefers-reduced-motion`: all new animations must be covered by the
  existing reduced-motion media query and the typed-text guard.
- Responsive breakpoint is `max-width: 860px`. Verify changes at mobile
  (~375px), tablet (~768px), and desktop widths.

## Known constraints

- **Form is client-side only.** It validates input and opens the visitor's
  email client via `mailto:`. There is no backend, so do not claim messages
  are sent automatically.
- **Project and demo links are placeholders.** The "Live Demo" buttons show a
  toast; the GitHub links point to the GitHub homepage.
- No analytics, cookies, or third-party scripts besides Google Fonts.
- The inline base64 portrait makes the HTML file large; avoid adding more
  inline binary data.

## Git workflow

```powershell
git status
git add index.html AGENTS.md
git commit -m "Describe the change"
git push origin main
```

Keep commits focused. Do not commit local copies, screenshots, or the
standalone Desktop HTML export.
