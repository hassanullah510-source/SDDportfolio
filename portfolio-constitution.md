# Constitution of Hassan Ullah Portfolio

**Adopted:** October 26, 2026  
**Last Updated:** October 26, 2026  
**Status:** Active  
**Governing Document:** This constitution establishes the fundamental principles, rules, and standards for the Hassan Ullah Portfolio project.

## Preamble

We, the contributors to this portfolio project, establish this Constitution to preserve its core identity as a fast, accessible, self-contained personal portfolio. We commit to maintaining simplicity, performance, and professional presentation while showcasing the skills and experience of Hassan Ullah.

## Article I: Project Purpose

### Section 1.1 Mission
The mission of this portfolio is to professionally showcase Hassan Ullah as a Full Stack and JavaScript developer with 6+ years of experience, providing potential employers and clients with a clear view of skills, projects, experience, and contact information.

### Section 1.2 Core Values
- **Simplicity:** No unnecessary complexity, dependencies, or abstractions
- **Performance:** Fast loading, minimal JavaScript, optimized for all devices
- **Accessibility:** Usable by everyone, regardless of ability or preference
- **Professionalism:** Clean, polished presentation that reflects code quality
- **Authenticity:** Accurate representation of skills and experience
- **Maintainability:** Easy to understand and modify without build tools

## Article II: Architectural Principles

### Section 2.1 Single-File Doctrine
**MANDATORY:** The portfolio SHALL remain a single self-contained `index.html` file containing all HTML, CSS, and JavaScript. 

**Exceptions:** Only with unanimous agreement and documented justification may assets be split. If split, all assets MUST go in a top-level `assets/` folder with relative paths.

### Section 2.2 Zero-Dependency Rule
**MANDATORY:** 
- No npm packages, node_modules, or package.json
- No frameworks (React, Vue, Angular, etc.)
- No bundlers, transpilers, or build tools
- No CSS preprocessors requiring compilation
- Only approved third-party resources: Google Fonts (Sora, Manrope)

### Section 2.3 Progressive Enhancement
The site SHALL function with core content accessible even if JavaScript is disabled. Interactive enhancements (animations, form validation, mobile menu) are acceptable as long as they don't break basic navigation.

## Article III: Design Standards

### Section 3.1 Design System Compliance
All styling MUST use the established CSS custom properties:
```css
--bg, --bg2, --tx, --mu, --b, --p, --c, --k, --g, --gl, --bd
```

The signature accent gradient MUST remain: `linear-gradient(120deg, #4f7cff, #9b5cff, #ff4fa3)`

### Section 3.2 Visual Consistency
- **Typography:** Sora for headings, Manrope for body text
- **Spacing:** Follow existing padding/margin patterns
- **Components:** Reuse existing utility classes (`.wrap`, `.glass`, `.btn`, `.title`, `.sub`, `.rv`)
- **Effects:** Maintain glassmorphism aesthetic with backdrop-filter
- **Animations:** Subtle, purposeful, and performant

### Section 3.3 Responsive Requirements
- **Mobile-first consideration:** Must work on screens as small as 375px
- **Breakpoint:** Responsive behavior at `max-width: 860px`
- **Tablet:** Must display correctly at ~768px
- **Desktop:** Optimal at 1120px container width
- **Safe areas:** Respect device safe area insets

## Article IV: Code Standards

### Section 4.1 JavaScript Conventions
- **Style:** ES6+ in global scope
- **Formatting:** Two-space indentation, semicolon-terminated
- **Functions:** Short, single-purpose functions
- **Rendering:** Use template literals for DOM generation
- **Variables:** Clear, descriptive naming
- **Data structure:** Keep content in arrays/objects at top of script

### Section 4.2 HTML Standards
- **Semantics:** Use semantic HTML5 elements where appropriate
- **Accessibility:** Include `alt` attributes, ARIA labels where needed
- **IDs:** Preserve existing section IDs for navigation
- **Structure:** Maintain top-to-bottom order as documented

### Section 4.3 CSS Standards
- **Organization:** Group by sections, maintain current structure
- **Specificity:** Keep selectors simple and maintainable
- **Animations:** Use `transform` and `opacity` for performance
- **Units:** Prefer `rem`, `em`, `clamp()`, `vw/vh` where appropriate
- **Comments:** Minimal, only where necessary

## Article V: Content Governance

### Section 5.1 Data Management
Content MUST be managed as follows:
- **Skills:** Edit `skills` array only
- **Projects:** Edit `projects` array only (update placeholders with real URLs when available)
- **Services:** Edit `svc` array only
- **Phrases:** Edit `ph` array for typed animation
- **Static content:** Edit HTML directly with care

### Section 5.2 Contact Information
**CRITICAL:** The email `hassanullah510@gmail.com` MUST appear consistently. When updating:
1. Contact section mailto link
2. Footer mailto link  
3. Form submission handler

All three locations MUST be updated simultaneously.

### Section 5.3 Social Links
Social media links in footer are placeholders by default. They MAY be updated to real URLs when available. All must include `target="_blank"` and `rel="noopener"` for external links.

### Section 5.4 Project Links
"Live Demo" buttons currently show toast notifications. When real project URLs become available, replace `href="#projects"` with actual URLs. GitHub links should point to specific repositories, not homepage.

## Article VI: Accessibility & Inclusion

### Section 6.1 Core Requirements
- **Keyboard Navigation:** All interactive elements must be keyboard accessible
- **Focus States:** Visible `:focus-visible` outlines required
- **ARIA:** Proper ARIA attributes where semantic HTML falls short
- **Alt Text:** Descriptive `alt` attributes for all images
- **Color Contrast:** Maintain sufficient contrast ratios
- **Live Regions:** Use `role="status"` for dynamic messages

### Section 6.2 Motion Preferences
**MANDATORY:** All animations MUST respect `prefers-reduced-motion`. 
- Animations disabled under reduced motion
- Transitions disabled under reduced motion
- Typed text shows static first phrase under reduced motion
- Scroll reveal becomes immediately visible

### Section 6.3 Responsive Text
Text MUST scale appropriately using `clamp()` where beneficial. No horizontal scrolling on any viewport size.

## Article VII: Performance & Optimization

### Section 7.1 Performance Standards
- **Minimal DOM:** Efficient rendering, avoid unnecessary elements
- **CSS Efficiency:** Use efficient selectors, avoid expensive properties
- **JavaScript:** Minimal, event delegation where appropriate
- **Images:** Prefer optimized formats; inline base64 only for small critical images
- **Fonts:** Use `display=swap` for web fonts (Google Fonts handles this)

### Section 7.2 Loading Strategy
- CSS in head, JavaScript at end of body
- No render-blocking resources beyond fonts
- Smooth scrolling with `scroll-behavior: smooth`
- IntersectionObserver for performance-friendly animations

## Article VIII: Git & Version Control

### Section 8.1 Commit Standards
- **Focused commits:** Each commit should address one logical change
- **Clear messages:** Descriptive commit messages in English
- **Staged files:** Typically `index.html` and `AGENTS.md`
- **No artifacts:** Never commit local copies, screenshots, or Desktop HTML exports

### Section 8.2 Branching
- **Default branch:** `main`
- **Direct commits:** Acceptable for this personal project
- **Pull requests:** Optional but encouraged for significant changes

## Article IX: Amendments

### Section 9.1 Amendment Process
This Constitution may be amended by:
1. Documenting the proposed change with clear rationale
2. Updating the relevant sections
3. Incrementing the "Last Updated" date
4. Committing with message "Amend Constitution: [description]"

### Section 9.2 Supreme Law
In case of conflict between this Constitution and other documents, this Constitution SHALL take precedence for matters of core principles and mandatory rules.

## Article X: Ratification

This Constitution is hereby ratified on October 26, 2026 and shall govern all development, maintenance, and modification of the Hassan Ullah Portfolio.

**Signed in principle by the project maintainers.**

---

*This document is a living constitution. It serves as the foundation for maintaining the integrity, quality, and purpose of this portfolio.*