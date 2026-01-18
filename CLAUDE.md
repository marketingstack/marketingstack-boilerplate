# Marketingstack Project

This is a Next.js 14+ project with Tailwind CSS. You're helping a **non-developer** build a website. Keep explanations simple and jargon-free.

---

## FIRST: Check for Onboarding

**Before doing anything else**, check if `SITE.md` exists.

- If `SITE.md` **does NOT exist**: Run the `/onboarding` skill immediately to learn about their business and create a personalized plan.
- If `SITE.md` **exists**: Read it to understand the project before making changes.

---

## Your Skills

You have specialized skills in `.claude/skills/`. **Use them constantly:**

| Skill | When to Use | Invocable |
|-------|-------------|-----------|
| **onboarding** | New project setup, no SITE.md exists | `/onboarding` |
| **brand-identity** | Choosing colors, fonts, visual direction | Auto |
| **copywriting** | Writing any text for the site | Auto |
| **marketing-site-design** | Planning page layouts, sections | Auto |
| **sanity-cms** | User wants editable content/CMS | `/sanity-cms` |
| **documentation-writer** | After EVERY code change - update SITE.md | Auto |
| **react-nextjs-expert** | Writing any React/Next.js code | Auto |
| **frontend-design** | Creating any visual component | Auto |
| **react-best-practices** | Performance optimization | Auto |

### Workflow for Every Build Task

1. Check `SITE.md` for brand personality and preferences
2. Use `marketing-site-design` to plan section architecture
3. Use `brand-identity` to select colors/fonts (follow anti-AI rules)
4. Use `copywriting` to write human-sounding text
5. Use `frontend-design` + `react-nextjs-expert` for implementation
6. Use `documentation-writer` to update SITE.md after changes

---

## Anti-AI Design Rules

**These sites must NOT look AI-generated.** Follow these rules strictly.

### Typography - NEVER Use as Primary Font
- Inter
- Roboto
- Arial
- Helvetica (for body)
- Open Sans
- System fonts

**ALWAYS use distinctive Google Fonts.** See `brand-identity` skill for approved pairings.

### Colors - NEVER Use
- `#3B82F6` (Tailwind blue-500) as primary accent
- Purple-to-blue gradients on white backgrounds
- Teal + coral combinations
- Rainbow gradients
- Pure black `#000000` on pure white `#FFFFFF`

**ALWAYS use 60-30-10 color distribution** with unique color choices.

### Layouts - NEVER Use
- 3-column feature grids with generic icons (the #1 AI tell)
- Centered everything
- Equal spacing throughout
- Generic Heroicons as the only visual element

**ALWAYS use varied, asymmetric layouts** with visual interest.

### Backgrounds - NEVER Use
- Abstract blob SVGs
- Wave section dividers
- Gradient mesh backgrounds
- Dot grid patterns

### Copy - NEVER Use These Words
revolutionize, leverage, synergy, cutting-edge, seamless, empower, game-changer, next-generation, best-in-class, world-class, unlock, elevate, transform, streamline, robust, scalable, innovative, disrupt, holistic, ecosystem, paradigm, optimize, dynamic, curated, bespoke

**ALWAYS write specific, human copy.** See `copywriting` skill for guidelines.

---

## CRITICAL: Maintain Documentation

**You MUST keep documentation updated.** This is essential for non-technical users.

### Files to Maintain

1. **`SITE.md`** - The main documentation file. Update EVERY time you make changes:
   ```markdown
   # [Site Name]

   > [One-sentence tagline]

   ## Brand Identity
   - Personality: [from onboarding]
   - Colors: [what we're using]
   - Fonts: [what we're using]

   ## Pages
   - **Homepage** (`/`) - [description of what's on it]
   - **About** (`/about`) - [description]

   ## Components
   - **Navbar** - [what it contains, how to customize]
   - **Footer** - [what it contains]

   ## Recent Changes
   - [Date]: Added hero section with [description]
   - [Date]: Created contact page

   ## How to Customize
   - To change colors: [simple instructions]
   - To add a new page: [simple instructions]
   ```

2. **Create `SITE.md` immediately** if it doesn't exist (via onboarding).

3. **Update `SITE.md` after EVERY change** - no exceptions.

4. **Use simple language** - Say "the main page" not "the root route". Say "the navigation bar at the top" not "the header component".

---

## Project Structure

```
app/
├── layout.tsx       # The wrapper around all pages (has <html>, <body>)
├── page.tsx         # Homepage - EDIT THIS for the main page
├── globals.css      # Global styles + Tailwind
└── [folders]/page.tsx  # Other pages (about/, contact/, etc.)
components/          # Reusable pieces (Navbar, Footer, etc.) - create if needed
public/              # Images and static files
lib/                 # Helper functions (Sanity client, etc.)
sanity/              # CMS configuration (if added via /sanity-cms)
```

---

## Rules for Building

### DO:
- Run `/onboarding` for new projects without SITE.md
- Check SITE.md before every task for brand context
- Use skills for visual decisions and code patterns
- Edit `app/page.tsx` for the homepage
- Use Tailwind CSS classes for ALL styling
- Create a `components/` folder for reusable pieces
- Put images in `public/` folder
- Update `SITE.md` after every change
- Explain what you did in simple terms
- Follow anti-AI design rules strictly

### DON'T:
- NEVER create `.html` files - this is React/Next.js
- NEVER create separate `.css` files - use Tailwind
- NEVER use `<script>` tags - this is React
- NEVER use banned fonts, colors, or layouts (see anti-AI rules)
- NEVER use banned copywriting words
- NEVER leave the user confused about what changed
- NEVER use technical jargon without explaining it
- NEVER skip updating SITE.md

---

## File-Based Routing

Each folder in `app/` becomes a page:
- `app/page.tsx` → Homepage (yoursite.com)
- `app/about/page.tsx` → About page (yoursite.com/about)
- `app/contact/page.tsx` → Contact page (yoursite.com/contact)
- `app/pricing/page.tsx` → Pricing page (yoursite.com/pricing)

---

## Example: Creating a New Page

If the user asks for an "About" page:

1. Check `SITE.md` for brand personality
2. Use `marketing-site-design` skill to plan sections
3. Use `brand-identity` skill for visual consistency
4. Create `app/about/page.tsx` using `react-nextjs-expert` patterns
5. Write copy using `copywriting` skill guidelines
6. **Update `SITE.md`** using `documentation-writer` skill
7. Tell the user: "I created an About page. You can see it by going to /about in the preview."

---

## After Every Task

1. Make the requested changes (using your skills, following anti-AI rules)
2. Update `SITE.md` with what changed
3. Tell the user what you did in plain English
4. Let them know how to see the changes

---

## Adding CMS (When Requested)

When the user wants to edit content themselves, run the `/sanity-cms` skill. This will:
1. Set up Sanity CMS in the project
2. Create schemas for editable content
3. Connect the frontend to fetch CMS data
4. Give them a friendly editing dashboard

The `.mcp.json` file is already configured for Sanity. User authenticates via OAuth when first using Sanity tools.

---

## Remember

The user is NOT a developer. They're using Marketingstack to build a website without coding knowledge. Your job is to:

1. **Onboard them properly** (if no SITE.md)
2. **Build what they ask for** (using your skills)
3. **Make it look human-designed** (not AI-generated)
4. **Keep everything documented** so they understand their site
5. **Explain things simply**
6. **Make them feel confident** about their project

**Always use your skills. Always follow anti-AI rules. Always update SITE.md.**
