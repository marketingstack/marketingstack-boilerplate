---
name: brand-identity
description: Enforces distinctive brand colors, typography, and visual rules. Contains anti-AI design rules to ensure sites look human-crafted, not AI-generated.
---

# Brand Identity Skill

This skill ensures every site has a distinctive, human-crafted visual identity. It contains strict rules to avoid "AI slop" aesthetics.

## The 60-30-10 Color Rule

Every site needs exactly three color roles:

- **60% - Dominant/Background**: The main canvas (usually neutral)
- **30% - Secondary**: Supporting color for sections, cards, accents
- **10% - Accent**: CTAs, highlights, interactive elements (the "pop")

### Implementation

```css
:root {
  /* 60% - Dominant */
  --color-bg: #FAFAF9;
  --color-text: #1C1917;

  /* 30% - Secondary */
  --color-secondary: #E7E5E4;
  --color-secondary-text: #44403C;

  /* 10% - Accent */
  --color-accent: #DC2626;
  --color-accent-hover: #B91C1C;
}
```

### Color Selection by Industry

Use these as STARTING POINTS - always customize:

| Industry | Dominant | Secondary | Accent |
|----------|----------|-----------|--------|
| Finance/Legal | Slate, Stone | Cool gray | Navy or Forest |
| Health/Wellness | Warm white, Cream | Sage, Soft green | Terracotta, Coral |
| Tech/SaaS | True white, Cool gray | Slate | Electric blue, Violet |
| Food/Restaurant | Cream, Warm white | Terracotta, Olive | Deep red, Orange |
| Creative/Agency | Off-black, Charcoal | Warm gray | Unexpected pop (yellow, magenta) |
| Luxury/Fashion | Pure white, Black | Gold, Champagne | Black or Gold |
| Education | Light cream | Warm gray, Blue-gray | Warm blue, Green |

---

## Typography Rules

### BANNED Fonts (Never Use as Primary)

These fonts scream "AI-generated":
- Inter
- Roboto
- Arial
- Helvetica (for body text)
- Open Sans
- System fonts stack as primary

### Approved Font Pairings

Always pair a **display font** (headings) with a **body font**:

**Modern & Clean:**
- Display: Space Grotesk / Body: DM Sans
- Display: Outfit / Body: Source Sans 3
- Display: Sora / Body: Nunito

**Elegant & Refined:**
- Display: Playfair Display / Body: Lato
- Display: Cormorant Garamond / Body: Montserrat
- Display: Fraunces / Body: Work Sans

**Bold & Energetic:**
- Display: Bebas Neue / Body: Public Sans
- Display: Oswald / Body: Karla
- Display: Anton / Body: Rubik

**Warm & Approachable:**
- Display: Poppins / Body: Nunito Sans
- Display: Quicksand / Body: Open Sans (acceptable as body only)
- Display: Comfortaa / Body: Mulish

**Creative & Artistic:**
- Display: Righteous / Body: Lexend
- Display: Archivo Black / Body: Albert Sans
- Display: Unbounded / Body: Figtree

### Implementation with next/font

```tsx
// app/layout.tsx
import { Space_Grotesk, DM_Sans } from 'next/font/google'

const spaceGrotesk = Space_Grotesk({
  subsets: ['latin'],
  variable: '--font-display',
  display: 'swap',
})

const dmSans = DM_Sans({
  subsets: ['latin'],
  variable: '--font-body',
  display: 'swap',
})

export default function RootLayout({ children }) {
  return (
    <html lang="en" className={`${spaceGrotesk.variable} ${dmSans.variable}`}>
      <body className="font-body">
        {children}
      </body>
    </html>
  )
}
```

```css
/* globals.css */
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  h1, h2, h3, h4, h5, h6 {
    font-family: var(--font-display);
  }

  body {
    font-family: var(--font-body);
  }
}
```

---

## ANTI-AI DESIGN RULES

### Colors - NEVER Use

| Banned | Why | Alternative |
|--------|-----|-------------|
| `#3B82F6` (Tailwind blue-500) | Default AI choice | Pick a unique blue: `#2563EB`, `#1D4ED8`, or non-blue accent |
| Purple-to-blue gradient | AI aesthetic cliche | Single color, or unexpected gradient (orange→pink, green→teal) |
| Teal + Coral combo | Overused "modern" palette | Pick ONE and find a neutral complement |
| Rainbow gradients | Screams "AI made this" | Two-color max, subtle angle |
| Pure `#000000` on `#FFFFFF` | Harsh, lazy | Off-black (`#1C1917`) on off-white (`#FAFAF9`) |

### Layouts - NEVER Use

| Banned | Why | Alternative |
|--------|-----|-------------|
| 3-column feature grid with icons | The #1 AI layout | 2-column, asymmetric, or bento grid |
| Centered everything | Boring, predictable | Left-align body, vary section alignment |
| Equal spacing throughout | Robotic feel | Vary spacing: tight headers, generous between sections |
| Generic icon set (Heroicons default) | Instantly recognizable as template | Phosphor Icons, Lucide with custom stroke, or no icons |

### Backgrounds - NEVER Use

| Banned | Why | Alternative |
|--------|-----|-------------|
| Abstract blob SVGs | AI calling card | Geometric shapes, grain texture, or solid color |
| Wave dividers | 2020 template look | Hard edges, diagonal slices, or no dividers |
| Gradient mesh backgrounds | Overplayed | Subtle radial gradient, solid color, or photography |
| Grid of dots | Too common | Lines, noise texture, or nothing |

### Images - NEVER Use

| Banned | Why | Alternative |
|--------|-----|-------------|
| Handshake stock photos | Meaningless corporate | Real team photos or none |
| Diverse group pointing at laptop | Cliche | Action shots or illustrations |
| Abstract 3D shapes | AI art indicator | Real photos, custom illustration, or typography-focused |
| Floating UI mockups | Template aesthetic | Screenshots in context or no mockups |

---

## Applying Brand to Site

When building, CHECK every component against:

1. **Does it use banned elements?** (fonts, colors, layouts)
2. **Does it follow 60-30-10?** (check color distribution)
3. **Is typography properly loaded?** (next/font, CSS variables)
4. **Would a human designer make this choice?** (if generic, differentiate)

### Quick Fixes for AI-Looking Sites

| Problem | Fix |
|---------|-----|
| Looks too "template" | Add asymmetry, vary section layouts |
| Colors feel generic | Commit to ONE bold accent, desaturate the rest |
| Typography is boring | Increase heading size contrast, add letter-spacing |
| Too much whitespace | Add subtle background texture or tint |
| Too busy | Remove one element from every section |
| Feels corporate | Add one unexpected color or playful element |

---

## Checklist Before Shipping

- [ ] No banned fonts in primary use
- [ ] No `#3B82F6` as primary accent
- [ ] No purple-to-blue gradients
- [ ] No 3-column feature grids with generic icons
- [ ] 60-30-10 color rule followed
- [ ] Fonts loaded with next/font
- [ ] At least ONE distinctive design choice per page
- [ ] Would pass the "human designer" test
