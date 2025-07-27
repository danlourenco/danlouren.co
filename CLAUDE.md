# CLAUDE.md
## Dan Lourenço Portfolio & Blog Project

This document contains all the context, design system, brand guidelines, and project knowledge for building Dan Lourenço's portfolio and blog using Astro.

---

## Project Overview

### Core Brand Concept
**"Thoughtful innovation through focused craftsmanship"**

Dan represents the intersection of deep technical expertise and genuine human connection. He brings the rare combination of introvert's depth with creative problem-solving, delivering solutions that are both technically excellent and meaningfully impactful.

### Target Positioning
- **The Humane Technologist**: Building technology that serves humanity rather than exploiting it
- **Values-Driven Professional**: Attracted to projects with sustainability and positive social impact
- **Thoughtful Architect**: Processes complex problems with analytical precision and creative insight
- **Authentic Connector**: Prefers meaningful collaboration over superficial networking

---

## Brand Personality & Value Proposition

### Primary Traits

**Thoughtful Architect**
- Naturally processes complex problems with both analytical precision and creative insight
- Sees possibilities others might miss while maintaining pragmatic implementation focus
- Values understanding the "why" behind decisions, not just the "what"

**Authentic Connector**
- Prefers meaningful one-on-one conversations over surface-level networking
- Builds genuine relationships based on shared commitment to quality and craft
- Values direct, context-rich communication that respects everyone's time

**Focused Craftsperson**
- Thrives in deep work environments where concentration leads to breakthrough solutions
- Finds energy in simplification—whether in code, documentation, or workflows
- Approaches each project with the care of someone who takes personal pride in their work

**Values-Driven Professional**
- Drawn to projects that align with personal values, especially sustainability and positive social impact
- Believes technology should serve people, not the other way around
- Seeks work that contributes to something larger than individual achievement

### What Dan Brings to Teams

**Deep Problem-Solving Capability**
Dan doesn't just implement features—he understands systems. His introverted nature allows for the sustained focus needed to work through complex technical challenges that require both creative thinking and analytical rigor.

**Quality-First Mindset**
With Dan, "done" means truly finished—accessible, performant, and maintainable. His natural inclination toward simplification means he creates code and documentation that future developers will thank him for.

**Sustainable Innovation**
Dan's approach to learning and implementation is sustainable. He builds mental models that last, creates documentation that helps others, and approaches new technologies with both enthusiasm and appropriate skepticism.

---

## Strategic Market Positioning

### Target Organizations

**Mission-Driven Tech Companies**
- Organizations working on climate solutions, digital equity, educational technology
- Companies with B-Corp certifications or explicit social impact missions
- Startups focused on mental health, digital wellness, or ethical AI

**Forward-Thinking Established Companies**
- Tech giants investing in sustainability initiatives and responsible AI
- Companies implementing "humane design" principles in their products
- Organizations with Chief Sustainability Officers or Ethics in AI teams

### Content Strategy Alignment
Dan's positioning aligns perfectly with the Center for Humane Technology's mission and the growing focus on sustainability in tech (a major trend in 2025). Content should emphasize:
- Technology that serves users rather than exploits them
- Sustainable coding practices and environmental consciousness
- Accessibility-first development and ethical design decisions
- Moving beyond the attention economy toward human flourishing

---

## Design System & Aesthetic

### Core Design Philosophy

**Aesthetic Preferences**
- Favor clean, purposeful interfaces over decorative elements
- Appreciate retro computing aesthetics that prioritize function
- Value consistency between development tools and personal branding
- Prefer authentic materials and interactions over superficial polish

**Technical Philosophy**
- Quality implementation over rapid feature delivery
- Sustainable, maintainable solutions over quick fixes
- Creative problem-solving within practical constraints
- Tools that enhance focus rather than create distraction

### Visual Design Language

**Terminal-Inspired Aesthetic**
The entire site uses a cohesive terminal/command-line aesthetic that reinforces Dan's identity as a thoughtful developer:

- **Section Headers**: Terminal commands that relate to content
  - About: `dan@localhost:~ $ whoami`
  - Projects: `dan@localhost:~ $ ls -la projects/`
  - Blog: `dan@localhost:~ $ cat blog/*.md`
  - Contact: `dan@localhost:~ $ ./connect.sh`

- **Visual Hierarchy**: Aesthetic portions (prompt, path, $) at 50% opacity, meaningful content fully opaque and bold

**Color Palette** (Semantic Design Tokens)
```css
/* Base Colors - Current Theme: Deep Navy */
--color-bg-primary: #0a192f;      /* Main background */
--color-bg-secondary: #112240;    /* Card backgrounds, elevated surfaces */
--color-bg-tertiary: #233554;     /* Borders, dividers, subtle backgrounds */

/* Text Colors */
--color-text-primary: #ccd6f6;    /* Headings, high emphasis text */
--color-text-secondary: #a8b2d1;  /* Secondary text, medium emphasis */
--color-text-tertiary: #8892b0;   /* Body text, low emphasis */
--color-text-inverse: #e6f1ff;    /* Text on dark backgrounds, highest contrast */

/* Accent Colors */
--color-accent-primary: #64ffda;  /* Primary actions, links, highlights */
--color-accent-secondary: #f57dff; /* Secondary accent (pink) */
--color-accent-tertiary: #57cbff;  /* Tertiary accent (blue) */

/* Interactive States */
--color-accent-hover: rgba(100, 255, 218, 0.1); /* Hover backgrounds */
--color-accent-focus: rgba(100, 255, 218, 0.2);  /* Focus states */
--color-accent-active: rgba(100, 255, 218, 0.3); /* Active states */

/* Semantic Colors */
--color-success: #22c55e;    /* Success states, positive actions */
--color-warning: #f59e0b;    /* Warnings, attention needed */
--color-error: #ef4444;      /* Errors, destructive actions */
--color-info: #3b82f6;       /* Information, neutral notifications */

/* Terminal-specific Colors */
--color-terminal-prompt: var(--color-accent-primary);  /* Terminal prompt text */
--color-terminal-command: var(--color-text-primary);   /* Command text */
--color-terminal-output: var(--color-text-secondary);  /* Command output */
--color-terminal-comment: var(--color-text-tertiary);  /* Comments, metadata */

/* Component-specific Tokens */
--color-code-bg: var(--color-bg-primary);
--color-code-text: var(--color-accent-primary);
--color-blockquote-border: var(--color-accent-primary);
--color-link: var(--color-accent-primary);
--color-link-hover: var(--color-text-inverse);

/* Future Theme Support */
/* 
   Light Theme Example:
   --color-bg-primary: #ffffff;
   --color-bg-secondary: #f8fafc;
   --color-bg-tertiary: #e2e8f0;
   --color-text-primary: #1e293b;
   --color-text-secondary: #475569;
   --color-text-tertiary: #64748b;
   
   High Contrast Theme Example:
   --color-bg-primary: #000000;
   --color-text-primary: #ffffff;
   --color-accent-primary: #00ff00;
*/
```

**Theme Implementation Strategy**
```css
/* Base theme (default) */
[data-theme="dark"] {
  /* Current navy theme tokens above */
}

/* Future themes */
[data-theme="light"] {
  --color-bg-primary: #ffffff;
  --color-bg-secondary: #f8fafc;
  --color-bg-tertiary: #e2e8f0;
  --color-text-primary: #1e293b;
  --color-text-secondary: #475569;
  --color-text-tertiary: #64748b;
  --color-text-inverse: #ffffff;
  --color-accent-primary: #059669; /* Adjusted for light theme */
  /* ... other semantic mappings */
}

[data-theme="high-contrast"] {
  --color-bg-primary: #000000;
  --color-bg-secondary: #1a1a1a;
  --color-text-primary: #ffffff;
  --color-accent-primary: #00ff00;
  /* ... high contrast mappings */
}
```

**Typography**
- **Primary**: 'Calibre', 'Inter', 'San Francisco', 'SF Pro Text', system-ui, sans-serif
- **Monospace**: 'SF Mono', 'Fira Code', 'Fira Mono', 'Roboto Mono', monospace
- **Scale**: Uses relative units (rem) for accessibility and scalability

---

## Content Strategy & Messaging

### Hero Section Messaging
```
Hi, my name is
Dan Lourenço.
I'm a full-stack developer who cares about building thoughtfully.

I specialize in crafting sustainable, accessible, and meaningful digital experiences. 
My approach combines deep technical expertise with creative problem-solving to 
build solutions that amplify human potential rather than exploit it.
```

### About Section Content
```
I believe technology should amplify human potential, not exploit human psychology. 
My approach combines analytical precision with creative insight to build solutions 
that are both technically excellent and meaningfully impactful.

As an introvert who thrives in deep work, I bring sustained focus to complex problems 
and find elegant solutions within real-world constraints. I'm drawn to projects that 
align with sustainability and positive social impact.
```

### Core Values
- Quality implementation over rapid feature delivery
- Sustainable solutions over quick fixes
- Human dignity in digital experiences
- Meaningful collaboration over superficial networking

### Sample Project Descriptions

**Sustainable UX Dashboard**
Carbon-aware web application that adapts its interface based on the user's energy grid. Reduces digital carbon footprint through intelligent design choices and demonstrates how environmental consciousness can guide UX decisions.

**Focus-First Task Manager**
Productivity tool designed around deep work principles. No notifications, no gamification—just thoughtful task organization that respects human attention and promotes sustainable productivity habits.

**Accessible Documentation System**
Open-source documentation platform built with accessibility as a core requirement, not an afterthought. Used by several non-profit organizations to share knowledge inclusively with their communities.

### Blog Content Themes

**Suggested Article Topics**
- "Building for Human Dignity: Lessons from Sustainable UX"
- "The True Cost of Technical Debt: Environmental and Social Impact"
- "Crafting Code That Serves: Moving Beyond the Attention Economy"
- "Sustainable Development Practices: Reducing Digital Carbon Footprints"
- "Accessibility-First Design: Making the Web Work for Everyone"

---

## Technical Implementation Guidelines

### Astro Project Structure
```
src/
├── components/
│   ├── Terminal.astro
│   ├── ProjectCard.astro
│   ├── BlogPost.astro
│   └── TerminalHeader.astro
├── layouts/
│   ├── BaseLayout.astro
│   ├── BlogLayout.astro
│   └── ProjectLayout.astro
├── pages/
│   ├── index.astro
│   ├── about.astro
│   ├── projects/
│   └── blog/
├── styles/
│   ├── global.css
```

### Key Components to Build

**Terminal Header Component**
```astro
---
interface Props {
  command: string;
  path?: string;
  emphasizedPart?: string;
}
---
<h2 class="terminal-section-header">
  <span class="terminal-prompt">dan@localhost</span>
  <span class="terminal-path">~{path || ""}</span>
  <span class="terminal-dollar">$</span>
  <span class="terminal-command">{command}</span>
  {emphasizedPart && <span class="emphasized">{emphasizedPart}</span>}
</h2>
```

**Terminal Window Component**
```astro
<div class="terminal">
  <div class="terminal-header">
    <div class="terminal-controls">
      <span class="close"></span>
      <span class="minimize"></span>
      <span class="maximize"></span>
    </div>
    <span class="terminal-title">dan@localhost</span>
  </div>
  <div class="terminal-content">
    <slot />
  </div>
</div>
```

### Performance & Accessibility Requirements

**Performance**
- Optimize for Core Web Vitals
- Use Astro's static generation for blog posts
- Implement proper image optimization
- Minimize JavaScript bundle size

**Accessibility**
- WCAG 2.1 AA compliance minimum
- Proper semantic HTML structure
- Focus management for interactive elements
- Screen reader friendly terminal aesthetics
- Color contrast ratios meet accessibility standards

**Sustainability**
- Implement carbon-aware features where possible
- Optimize for minimal energy consumption
- Use efficient, clean code practices
- Consider digital carbon footprint in design decisions

---

## Content Management

### Blog Post Structure
```markdown
---
title: "Article Title"
subtitle: "Brief description that appears in meta"
date: "2025-03-15"
readTime: "8 min"
tags: ["sustainability", "ux-design", "humane-tech"]
featured: true
---

Article content with markdown support...
```

### Project Data Structure
```json
{
  "title": "Project Name",
  "description": "Brief description for cards",
  "longDescription": "Detailed description for project pages",
  "technologies": ["React", "Node.js", "Accessibility"],
  "links": {
    "demo": "https://example.com",
    "github": "https://github.com/user/repo",
    "caseStudy": "/projects/project-name"
  },
  "featured": true,
  "sustainability": true,
  "accessibility": true
}
```

---

## SEO & Metadata Strategy

### Target Keywords
- "humane technology developer"
- "sustainable web development"
- "accessibility-first developer"
- "ethical technology consultant"
- "carbon-aware web design"

### Meta Descriptions
**Homepage**: "Dan Lourenço is a thoughtful technologist building sustainable, accessible digital experiences that serve humanity. Specializing in humane technology and environmental consciousness."

**Blog**: "Insights on sustainable web development, humane technology, and building digital experiences that respect both users and the planet."

---

## Implementation Checklist

### Phase 1: Core Site
- [ ] Set up Astro project with TypeScript
- [ ] Implement design system with CSS custom properties
- [ ] Create terminal-themed components
- [ ] Build homepage with hero, about, projects sections
- [ ] Implement responsive design with mobile-first approach

### Phase 2: Blog System
- [ ] Set up markdown processing for blog posts
- [ ] Create blog listing and individual post layouts
- [ ] Implement terminal-themed blog post design
- [ ] Add RSS feed generation
- [ ] Create tag-based filtering system

### Phase 3: Advanced Features
- [ ] Add search functionality
- [ ] Implement carbon-aware features
- [ ] Set up analytics (privacy-focused)
- [ ] Create contact form with validation
- [ ] Add progressive web app features

### Phase 4: Content & Launch
- [ ] Write initial blog posts
- [ ] Create project case studies
- [ ] Optimize for performance and accessibility
- [ ] Set up deployment pipeline
- [ ] Launch and test across devices

---

## Brand Voice & Tone

### Voice Characteristics
- **Thoughtful**: Takes time to consider implications and nuances
- **Authentic**: Genuine without being overly casual
- **Knowledgeable**: Demonstrates expertise without being condescending
- **Human-centered**: Always considers the human impact of technology
- **Pragmatic**: Balances idealism with practical implementation

### Tone Guidelines
- Use inclusive language that welcomes diverse audiences
- Explain technical concepts clearly without dumbing them down
- Show passion for meaningful work without being preachy
- Balance confidence with humility
- Use concrete examples to illustrate abstract concepts

### Writing Style
- Prefer active voice and clear, direct sentences
- Use technical terminology when appropriate, but always explain context
- Include practical examples and real-world applications
- Break up long content with subheadings and visual elements
- End sections with actionable insights or thought-provoking questions
- Incorporate humor and personality; doesn't take himself too seriously

---

## Maintenance & Evolution

### Content Calendar
- **Weekly**: One blog post on technical topics, sustainability, or industry insights
- **Monthly**: Project case study or major update
- **Quarterly**: Review and update project showcase
- **Annually**: Brand and messaging review

### Analytics & Success Metrics
- **User Experience**: Time to value, task completion rates
- **Content Performance**: Reading time, return visits, social shares
- **Professional Impact**: Contact form submissions, speaking opportunities
- **Sustainability**: Site carbon footprint, performance metrics

This document should serve as your comprehensive guide for building Dan's portfolio and blog. The terminal aesthetic, sustainability focus, and human-centered approach should be consistent throughout all implementations.

---

## Development Environment & Commands

### Core Commands
- **Development server**: `npm run dev` - Starts Astro dev server on http://localhost:4321
- **Build production**: `npm run build` - Creates optimized production build in ./dist
- **Preview production**: `npm run preview` - Preview production build locally
- **Linting**: [To be configured with ESLint]
- **Type checking**: `npm run astro check` - TypeScript type checking
- **Testing**: `npm run test` - Run tests with Vitest
- **Test watch**: `npm run test:watch` - Run tests in watch mode
- **Test coverage**: `npm run test:coverage` - Generate test coverage report

### Development Setup
```bash
# Install dependencies
npm install

# Run development server
npm run dev

# Before committing
npm run build  # Ensure build succeeds
npm run test   # Ensure tests pass
```

### Environment Variables
```env
# .env.local (for local development)
PUBLIC_SITE_URL=http://localhost:4321
PUBLIC_GA_MEASUREMENT_ID=your-ga-id  # Optional analytics

# Production environment variables
PUBLIC_SITE_URL=https://www.danlouren.co
```

---

## Component API Documentation

### TerminalHeader Component
```astro
---
interface Props {
  command: string;           // Required: The command to display
  path?: string;             // Optional: Current directory path
  emphasizedPart?: string;   // Optional: Part of command to emphasize
  animate?: boolean;         // Optional: Enable typewriter animation
}
---
```

**Usage Examples:**
```astro
<!-- Basic usage -->
<TerminalHeader command="whoami" />

<!-- With path -->
<TerminalHeader command="ls -la" path="/projects" />

<!-- With emphasis -->
<TerminalHeader 
  command="cat blog/" 
  emphasizedPart="*.md"
  animate={true}
/>
```

**CSS Classes:**
- `.terminal-prompt` - The user@host portion
- `.terminal-path` - Current directory display
- `.terminal-dollar` - The $ symbol
- `.terminal-command` - The actual command text
- `.emphasized` - Highlighted portion of command

### Terminal Window Component
```astro
---
interface Props {
  title?: string;    // Optional: Terminal window title
  height?: string;   // Optional: Fixed height (e.g., "400px")
  variant?: 'default' | 'minimal' | 'full';  // Window style variant
}
---
```

**Usage Examples:**
```astro
<!-- Basic terminal window -->
<Terminal>
  <p>Output content here...</p>
</Terminal>

<!-- With custom title and height -->
<Terminal title="npm run dev" height="300px">
  <pre>Starting development server...</pre>
</Terminal>
```

### ProjectCard Component
```astro
---
interface Props {
  title: string;
  description: string;
  technologies: string[];
  links?: {
    demo?: string;
    github?: string;
    caseStudy?: string;
  };
  featured?: boolean;
  sustainability?: boolean;
  accessibility?: boolean;
}
---
```

### BlogPost Component
```astro
---
interface Props {
  title: string;
  subtitle?: string;
  date: string;
  readTime: string;
  tags: string[];
  featured?: boolean;
}
---
```

---

## Animation & Interaction Guidelines

### Core Animations

**Terminal Cursor Blink**
```css
@keyframes blink {
  0%, 50% { opacity: 1; }
  51%, 100% { opacity: 0; }
}

.terminal-cursor {
  animation: blink 1s infinite;
  background-color: var(--color-accent-primary);
}
```

**Typewriter Effect** (Optional for hero section)
```css
@keyframes typewriter {
  from { width: 0; }
  to { width: 100%; }
}

.typewriter {
  overflow: hidden;
  white-space: nowrap;
  animation: typewriter 2s steps(40, end);
}
```

### Interaction States

**Hover Effects**
- Links: Transition color to `--color-text-inverse` with underline
- Cards: Subtle elevation with `transform: translateY(-2px)`
- Buttons: Background color transition with `--color-accent-hover`

**Focus States**
- Always visible focus ring using `--color-accent-focus`
- Never remove focus indicators, only style them
- Keyboard navigation must be smooth and logical

**Page Transitions**
- Prefer fade transitions (150-200ms) for route changes
- No jarring animations or excessive motion
- Respect `prefers-reduced-motion` media query

### Loading States
- Terminal-style progress indicators using ASCII characters
- Example: `[████████░░] 80% Loading...`
- Skeleton screens should use terminal-aesthetic placeholders

---

## Error Handling & Edge Cases

### Error Pages

**404 Page Design**
```astro
<Terminal>
  <TerminalHeader command="cd /nonexistent-page" />
  <pre class="error-output">
bash: cd: /nonexistent-page: No such file or directory

$ ls suggestions/
../  about/  blog/  contact/  projects/
  </pre>
</Terminal>
```

**500 Error Page**
```astro
<Terminal variant="full">
  <pre class="error-output">
[ERROR] Internal Server Error
Stack trace:
  at Object.serverError (/src/pages/[...slug].astro:42:15)
  
$ ./report-issue.sh
  </pre>
</Terminal>
```

### Empty States

**No Projects**
```
$ ls -la projects/
total 0
drwxr-xr-x  2 dan  staff  64 Mar 15 10:00 .
drwxr-xr-x  5 dan  staff 160 Mar 15 10:00 ..

$ echo "Projects coming soon..."
```

**No Blog Posts**
```
$ find . -name "*.md" -type f
$ echo "First post in progress..."
```

### Form Validation
- Error messages in terminal output style
- Example: `[ERROR] Email format invalid: missing @ symbol`
- Success messages: `[SUCCESS] Message sent successfully`
- Field-level validation with real-time feedback

### Network Errors
- Graceful degradation for offline functionality
- Cache strategic resources for offline viewing
- Display connection status in terminal style:
  ```
  $ ping api.danlouren.co
  ping: cannot resolve api.danlouren.co: No connection
  ```

---

## File Naming Conventions

### Components
- **Astro Components**: PascalCase (e.g., `TerminalHeader.astro`, `ProjectCard.astro`)
- **React/Vue Components**: PascalCase with extension (e.g., `ContactForm.tsx`)
- **Component Tests**: Same name with `.test.ts` (e.g., `TerminalHeader.test.ts`)

### Pages
- **Route Pages**: kebab-case (e.g., `about-me.astro`, `contact.astro`)
- **Dynamic Routes**: Square brackets (e.g., `[slug].astro`, `[...path].astro`)
- **API Routes**: kebab-case (e.g., `api/send-email.ts`)

### Styles
- **Global Styles**: kebab-case (e.g., `global.css`, `reset.css`)
- **Component Styles**: Match component name (e.g., `terminal-header.css`)
- **Utility Classes**: kebab-case (e.g., `utilities.css`)

### Scripts/Utilities
- **TypeScript Files**: camelCase (e.g., `formatDate.ts`, `parseMarkdown.ts`)
- **Config Files**: Exact names (e.g., `astro.config.mjs`, `tsconfig.json`)
- **Test Utilities**: camelCase (e.g., `testHelpers.ts`)

### Content
- **Blog Posts**: `YYYY-MM-DD-slug-name.md` (e.g., `2025-03-15-sustainable-ux-patterns.md`)
- **Project Files**: kebab-case (e.g., `carbon-aware-dashboard.md`)
- **Images**: kebab-case with size (e.g., `hero-image-1920x1080.webp`)

### Data Files
- **JSON Data**: kebab-case (e.g., `projects-data.json`, `site-config.json`)
- **TypeScript Types**: PascalCase (e.g., `ProjectTypes.ts`, `BlogTypes.ts`)

---

## Deployment & Infrastructure

### Hosting Platform
- **Primary**: Netlify (recommended for Astro)
- **Alternative**: Vercel, Cloudflare Pages
- **Static Output**: Compatible with any static host

### Build Configuration
```toml
# netlify.toml
[build]
  command = "npm run build"
  publish = "dist"

[build.environment]
  NODE_VERSION = "18"

[[headers]]
  for = "/*"
  [headers.values]
    X-Frame-Options = "DENY"
    X-Content-Type-Options = "nosniff"
    Referrer-Policy = "strict-origin-when-cross-origin"
```

### Environment Variables
```bash
# Production
PUBLIC_SITE_URL=https://www.danlouren.co
PUBLIC_GA_MEASUREMENT_ID=G-XXXXXXXXXX  # If using analytics
PUBLIC_CARBON_API_KEY=xxx  # For carbon-aware features

# Build-time only
GITHUB_TOKEN=xxx  # For fetching GitHub data
```

### Performance Optimization
- Enable Netlify/Vercel Edge Functions for dynamic features
- Configure aggressive caching for static assets
- Set up Cloudflare CDN for global distribution
- Implement service worker for offline support

### Domain Configuration
- Primary: `www.danlouren.co`
- Redirect: `danlouren.co` → `www.danlouren.co`
- SSL: Automatic via hosting platform
- DNS: Configure A/CNAME records as per host

### Monitoring
- Uptime monitoring via Better Uptime or similar
- Error tracking with Sentry (privacy-conscious config)
- Performance monitoring with Web Vitals
- Carbon footprint tracking with Website Carbon API

---

## Testing Strategy

### Testing Framework
**Vitest** - Fast unit testing framework with Vite integration

### Test Structure
```
tests/
├── unit/
│   ├── components/
│   │   ├── TerminalHeader.test.ts
│   │   └── ProjectCard.test.ts
│   ├── utils/
│   │   └── formatDate.test.ts
│   └── setup.ts
├── integration/
│   ├── navigation.test.ts
│   └── forms.test.ts
└── e2e/
    ├── user-journey.test.ts
    └── accessibility.test.ts
```

### Testing Configuration
```typescript
// vitest.config.ts
import { defineConfig } from 'vitest/config'
import { getViteConfig } from 'astro/config'

export default defineConfig(
  getViteConfig({
    test: {
      globals: true,
      environment: 'jsdom',
      setupFiles: './tests/setup.ts',
      coverage: {
        provider: 'v8',
        reporter: ['text', 'json', 'html'],
        exclude: ['node_modules/', 'dist/']
      }
    }
  })
)
```

### Test Examples
```typescript
// TerminalHeader.test.ts
import { describe, it, expect } from 'vitest'
import { render } from '@testing-library/vue'
import TerminalHeader from '@/components/TerminalHeader.astro'

describe('TerminalHeader', () => {
  it('renders command correctly', () => {
    const { getByText } = render(TerminalHeader, {
      props: { command: 'whoami' }
    })
    expect(getByText('whoami')).toBeTruthy()
  })
})
```

### Accessibility Testing
- **Tools**: 
  - axe-core for automated testing
  - Pa11y for CI/CD integration
  - Manual screen reader testing (NVDA, JAWS, VoiceOver)
- **Checklist**:
  - [ ] Keyboard navigation works throughout site
  - [ ] All images have appropriate alt text
  - [ ] Color contrast ratios meet WCAG AA
  - [ ] Focus indicators are visible
  - [ ] ARIA labels are properly implemented

### Performance Testing
- **Benchmarks**:
  - LCP < 2.5s
  - FID < 100ms
  - CLS < 0.1
  - Total bundle size < 200KB
- **Tools**:
  - Lighthouse CI in build pipeline
  - WebPageTest for real-world testing
  - Bundle analyzer for size optimization

### Browser Support Matrix
- Chrome/Edge: Last 2 versions
- Firefox: Last 2 versions
- Safari: Last 2 versions
- Mobile: iOS Safari 14+, Chrome Android

### Device Testing Checklist
- [ ] iPhone (various sizes)
- [ ] Android phones
- [ ] iPad/Tablets
- [ ] Desktop (1920x1080, 1366x768)
- [ ] Ultra-wide monitors
- [ ] Screen readers

---

## Content Guidelines

### Image Requirements

**Formats & Optimization**
- Primary format: WebP with JPEG/PNG fallbacks
- Use Astro's Image component for automatic optimization
- Lazy loading for below-fold images

**Standard Sizes**
- Hero images: 1920x1080 (16:9)
- Project cards: 600x400 (3:2)
- Blog post headers: 1200x630 (OG image size)
- Inline blog images: 800px max width
- Thumbnails: 300x200

**Alt Text Requirements**
- Descriptive, not redundant with surrounding text
- Include relevant details for context
- Avoid "image of" or "picture of" prefixes
- Empty alt="" for decorative images only

**Terminal-Themed Screenshots**
- Consistent terminal window styling
- Use SF Mono or Fira Code font
- Apply syntax highlighting for code
- Include window chrome (traffic lights) for context

### Code Examples

**Syntax Highlighting Theme**
```css
/* Based on terminal color scheme */
.hljs {
  background: var(--color-bg-secondary);
  color: var(--color-text-secondary);
}
.hljs-keyword { color: var(--color-accent-secondary); }
.hljs-string { color: var(--color-accent-primary); }
.hljs-comment { color: var(--color-text-tertiary); }
.hljs-function { color: var(--color-accent-tertiary); }
```

**Language Support**
- JavaScript/TypeScript (primary)
- HTML/CSS
- Python
- Bash/Shell
- JSON/YAML
- Markdown

**Code Block Format**
````markdown
```typescript
// Always include language identifier
function sustainableCode(): void {
  // Use comments to explain complex logic
  const result = computeEfficiently();
  return result;
}
```
````

**Terminal Command Formatting**
```markdown
$ npm install        # Comments after commands
$ npm run dev        # Start development server
```

### Writing Guidelines

**Blog Post Structure**
1. Hook - Engaging opening that states the problem
2. Context - Why this matters now
3. Solution - Practical approach with examples
4. Implementation - Code samples and walkthrough
5. Impact - Real-world implications
6. Call to Action - Next steps for readers

**SEO Optimization**
- Focus keyword in title, URL, and first paragraph
- Meta descriptions 150-160 characters
- Use semantic HTML (h2, h3 hierarchy)
- Internal linking to related content
- Schema markup for articles

**Accessibility in Content**
- Heading hierarchy must be logical
- Links have descriptive text (not "click here")
- Complex concepts have simple explanations
- Technical jargon is defined on first use
- Lists used for sequential information