# Portfolio Specification - Hassan Ullah

**Version:** 1.0  
**Date:** October 26, 2026  
**Project Type:** Personal Portfolio Website  
**Owner:** Hassan Ullah (hassanullah510@gmail.com)

## 1. Overview

This is a single-file static portfolio website showcasing Hassan Ullah as a Full Stack/JavaScript developer with 6+ years of experience. The entire site (HTML, CSS, JavaScript) lives in `index.html` with no build step, framework, or dependencies.

**Live Repository:** [https://github.com/hassanullah510-source/my-portfolio](https://github.com/hassanullah510-source/my-portfolio)  
**Default Branch:** `main`

## 2. Goals

- Showcase professional profile, skills, and experience
- Display featured projects with tech stacks
- Provide contact mechanism via mailto
- Deliver a modern, animated, responsive user experience
- Maintain accessibility and respect user motion preferences

## 3. Architecture

### Structure
- **Type:** Single self-contained HTML file (`index.html`)
- **Styling:** Embedded CSS in `<style>` block (lines ~9-164)
- **Scripting:** Embedded JavaScript in `<script>` block (lines ~278-333)
- **Assets:** Inline base64 portrait image, Google Fonts (Sora, Manrope)
- **No build tools:** No bundler, package manager, or framework

### Page Sections
| Section ID | Purpose | Key Elements |
|------------|---------|--------------|
| `#home` | Hero | Name, role, experience badge, typed phrases, CTA buttons, profile picture with orbiting tech icons |
| `#about` | About Me | Bio paragraphs, stats cards (6+ years, 15 technologies, 6 projects, 100% responsive) |
| `#skills` | Skills | Dynamically rendered skill bars with percentages |
| `#projects` | Projects | Featured projects grid with tech tags and placeholder links |
| `#experience` | Experience Timeline | 4-item timeline of development focus areas |
| `#services` | Services | 7 service cards offered |
| `#contact` | Contact | Email display and validated form with mailto handoff |

## 4. Design System

### Color Palette (CSS Variables)
```css
--bg: #070b1f        /* Primary background */
--bg2: #0d1333       /* Secondary background */
--tx: #e9ecff        /* Primary text */
--mu: #9aa3cf        /* Muted text */
--b: #4f7cff         /* Blue accent */
--p: #9b5cff         /* Purple accent */
--c: #22d3ee         /* Cyan accent */
--k: #ff4fa3         /* Pink accent */
--g: linear-gradient(120deg, #4f7cff, #9b5cff, #ff4fa3) /* Accent gradient */
--gl: rgba(255,255,255,.055)  /* Glass background */
--bd: rgba(255,255,255,.12)   /* Border color */
```

### Typography
- **Headings:** Sora (400, 600, 800)
- **Body:** Manrope (400, 500, 700)
- **Base size:** 16px

### UI Components
- `.wrap` - Max-width container (1120px)
- `.glass` - Glassmorphism cards with blur, hover effects
- `.btn.pri` - Gradient primary button
- `.btn.sec` - Secondary glass button
- `.title`, `.sub` - Section headings
- `.rv` - Scroll reveal animation class

### Responsive Design
- **Breakpoint:** `max-width: 860px` (mobile/tablet)
- **Mobile optimizations:** Stacked layouts, hamburger menu, adjusted spacing
- **Safe areas:** Respects `env(safe-area-inset-*)`

## 5. Functionality

### Navigation
- Fixed header with blur effect
- Smooth scroll to sections
- Active nav link highlighting via IntersectionObserver
- Mobile hamburger menu with slide-down animation
- Closes on link click or Escape key

### Animations & Effects
- **Background:** Animated gradient with floating blurred orbs
- **Hero:** Profile picture with rotating border gradient, pulsing glow, orbiting tech badges
- **Scroll reveal:** Elements with `.rv` fade/slide in as they enter viewport
- **Skill bars:** Animate to percentage width on reveal
- **Typed text:** Rotating phrases in hero ("responsive web apps", "scalable REST APIs", "fast Next.js sites", "full stack products")
- **Progress bar:** Scroll progress indicator at top
- **Back to top:** Button appears after scrolling 600px
- **Marquee:** Infinite scrolling tech stack banner
- **Hover effects:** Card lifts, button transforms

### Interactive Features
- **Mobile menu:** Toggle with burger button
- **Contact form:** Client-side validation
  - Name: min 2 chars
  - Email: valid email format
  - Subject: min 3 chars
  - Message: min 10 chars
  - On success: Opens mailto to `hassanullah510@gmail.com` with pre-filled content
- **Demo buttons:** Show toast "Live demo link coming soon. Add your project URL here."
- **Smooth scrolling:** Throughout site

### Data-Driven Content
All dynamic content rendered via JavaScript arrays:

```javascript
skills = [["HTML5",95],["CSS3",92],["JavaScript",96],["TypeScript",85],...]
projects = [["Title","Desc",["tags"],"gradient","icon"],...]
svc = [["icon","Title","Description"],...]
ph = ["responsive web apps","scalable REST APIs","fast Next.js sites","full stack products"]
```

## 6. Content Details

### Hero
- Name: Hassan Ullah
- Title: Full Stack Developer & JavaScript Developer
- Experience: 6+ Years
- CTAs: "View My Work" → `#projects`, "Contact Me" → `#contact`
- Orbit icons: `</>`, JS, `{ }`, Node

### About Stats
- 6+ Years experience
- 15 Technologies
- 6 Featured projects
- 100% Responsive builds

### Skills (15 items)
HTML5 (95), CSS3 (92), JavaScript (96), TypeScript (85), React.js (92), Next.js (88), Node.js (90), Express.js (88), MongoDB (85), SQL (82), REST APIs (93), Git & GitHub (90), Responsive Web Design (95), UI/UX (84), Full Stack Development (94)

### Projects (6 items)
1. E-Commerce Website (React, Node.js, MongoDB, Stripe)
2. Admin Dashboard (Next.js, TypeScript, SQL, Charts)
3. Full Stack Banking System (React, Express, SQL, JWT)
4. Task Management App (React, Node.js, MongoDB)
5. Portfolio / CMS (Next.js, MongoDB, REST API)
6. Real-Time Chat Application (React, Socket.io, Node.js)

*Note:* All project demo and GitHub links are placeholders.

### Services (7 items)
Full Stack Web Development, Frontend Development, Backend Development, JavaScript Development, API Development, Database Development, Website Optimization

### Contact
- Email: hassanullah510@gmail.com
- Form opens default mail client (no backend)

## 7. Accessibility

- Semantic HTML structure
- ARIA labels on icon-only links and buttons
- `aria-expanded` on mobile menu
- `role="status"` on live regions (toast, form message)
- `alt` text on images
- `:focus-visible` outlines
- Keyboard navigation support (Escape key closes menu)
- Respects `prefers-reduced-motion` (disables animations, shows first typed phrase)
- Proper heading hierarchy

## 8. Browser Support

Modern browsers supporting:
- CSS Grid, Flexbox
- CSS Custom Properties
- IntersectionObserver
- backdrop-filter
- ES6+ JavaScript

## 9. Development Guidelines

### Conventions
- Single file architecture (keep `index.html` self-contained)
- Two-space indentation
- Semicolon-terminated JavaScript
- Template literals for rendering
- Use existing CSS variables
- Add `.rv` class for scroll-reveal animations
- Follow existing code style

### Editing Guidelines
- **Skills/Projects/Services:** Edit arrays in JavaScript
- **Content:** Edit HTML sections directly
- **Email:** Update in 3 places (mailto links in contact section, footer, form handler)
- **Social links:** Update placeholder URLs in footer
- **Portrait:** Replace base64 with file in `assets/` folder if desired
- **New animations:** Must respect `prefers-reduced-motion`

### Git Workflow
```powershell
git status
git add index.html AGENTS.md
git commit -m "Describe the change"
git push origin main
```

## 10. Known Limitations

- **No backend:** Form uses `mailto:` only, messages not sent automatically
- **Placeholder links:** Project demos and GitHub links need real URLs
- **Large file:** Inline base64 portrait increases HTML size
- **No analytics/tracking:** No third-party scripts except Google Fonts
- **Static only:** No CMS or dynamic content

## 11. File Structure

```
Hassan SMIT/
├── index.html      # Main website (complete)
├── AGENTS.md       # Development guidelines
├── spec driven/    # Reserved for spec-driven development
└── portfolio-spec.md # This specification file
```

## 12. Deployment

No build step required. Can be deployed to any static host:
- GitHub Pages
- Netlify
- Vercel
- Cloudflare Pages
- Or served locally via `npx serve .` or `python -m http.server 8000`
