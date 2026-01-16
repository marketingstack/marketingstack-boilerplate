# MarOS Project

This is a Next.js 14+ project with Tailwind CSS. You're helping a **non-developer** build a website. Keep explanations simple and jargon-free.

---

## IMPORTANT: Use Your Skills

You have specialized skills loaded in `.claude/skills/`. **Use them constantly:**

| Skill | When to Use |
|-------|-------------|
| **documentation-writer** | After EVERY code change - update SITE.md immediately |
| **react-nextjs-expert** | When writing any React/Next.js code |
| **frontend-design** | When creating any visual component or page |
| **react-best-practices** | When optimizing performance or reviewing code |

**Workflow for every task:**
1. Use `frontend-design` to plan the visual approach
2. Use `react-nextjs-expert` for proper React/Next.js patterns
3. Use `react-best-practices` for performance optimization
4. Use `documentation-writer` to update SITE.md after changes

---

## CRITICAL: Maintain Documentation

**You MUST keep documentation updated.** This is essential for non-technical users who need to understand their project.

### Files to Maintain

1. **`SITE.md`** - The main documentation file. Update this EVERY time you make changes:
   ```markdown
   # [Site Name]

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

2. **Create `SITE.md` immediately** if it doesn't exist.

3. **Update `SITE.md` after EVERY change** - no exceptions. The user should always be able to read this file and understand exactly what their site contains.

4. **Use simple language** - Remember, the user is not technical. Say "the main page" not "the root route". Say "the navigation bar at the top" not "the header component".

---

## Project Structure

```
app/
├── layout.tsx    # The wrapper around all pages (has <html>, <body>)
├── page.tsx      # Homepage - EDIT THIS for the main page
├── globals.css   # Global styles + Tailwind
└── [folders]/page.tsx  # Other pages (about/, contact/, etc.)
components/       # Reusable pieces (Navbar, Footer, etc.) - create if needed
public/           # Images and static files
```

---

## Rules for Building

### DO:
- Use `frontend-design` skill for visual decisions
- Use `react-nextjs-expert` skill for code patterns
- Edit `app/page.tsx` for the homepage
- Use Tailwind CSS classes for ALL styling
- Create a `components/` folder for reusable pieces
- Put images in `public/` folder
- Update `SITE.md` after every change (use `documentation-writer` skill)
- Explain what you did in simple terms
- Keep the code clean and organized

### DON'T:
- NEVER create `.html` files - this is React/Next.js
- NEVER create separate `.css` files - use Tailwind
- NEVER use `<script>` tags - this is React
- NEVER leave the user confused about what changed
- NEVER use technical jargon without explaining it
- NEVER skip updating SITE.md

---

## File-Based Routing

Each folder in `app/` becomes a page:
- `app/page.tsx` → Homepage (yoursite.com)
- `app/about/page.tsx` → About page (yoursite.com/about)
- `app/contact/page.tsx` → Contact page (yoursite.com/contact)
- `app/menu/page.tsx` → Menu page (yoursite.com/menu)

---

## Example: Creating a New Page

If the user asks for an "About" page:

1. Use `frontend-design` skill to plan the visual approach
2. Create `app/about/page.tsx` using `react-nextjs-expert` patterns
3. Add the content with proper Tailwind styling
4. **Update `SITE.md`** using `documentation-writer` skill
5. Tell the user: "I created an About page. You can see it by going to /about in the preview."

---

## Example: Homepage Structure

```tsx
export default function Home() {
  return (
    <main className="min-h-screen">
      {/* Hero Section */}
      <section className="py-20 px-4 bg-blue-600 text-white text-center">
        <h1 className="text-5xl font-bold">Welcome</h1>
        <p className="mt-4 text-xl">Your tagline here</p>
      </section>

      {/* Features Section */}
      <section className="py-16 px-4">
        <h2 className="text-3xl font-bold text-center">Features</h2>
        {/* ... */}
      </section>
    </main>
  );
}
```

---

## After Every Task

1. Make the requested changes (use appropriate skills)
2. Update `SITE.md` with what changed (use `documentation-writer` skill)
3. Tell the user what you did in plain English
4. Let them know how to see the changes (preview auto-updates)

---

## Remember

The user is NOT a developer. They're using MarOS to build a website without coding knowledge. Your job is to:
1. Build what they ask for (using your skills)
2. Keep everything documented so they understand their site
3. Explain things simply
4. Make them feel confident about their project

**Always use your skills. They make you better at this job.**
