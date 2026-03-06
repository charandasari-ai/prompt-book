---
title: Premium Website Builder Playbook
category: claude-code
tags: [website, landing-page, react, vite, design, context, screenshots, html]
added: 2026-03-05
---

## Use Case
Build a premium-looking website that doesn't scream "AI built this." The key insight: the problem is never the prompt — it's the *context* you give the AI. Feeding screenshots + inspected HTML/CSS gives Claude enough visual context to produce agency-quality results fast.

---

## The 4-Step Playbook

### Step 1 — Find Inspiration
Browse these sites for proven, converting designs:
- **dribbble.com** — design showcase
- **awwwards.com** — award-winning websites
- **godly.website** — curated web design gallery

Pick one page you love. Note what you like (animations, layout, graphics, feel).

### Step 2 — Build with Context (The Core Prompt)

Right-click the inspiration page → Inspect → copy the full CSS styles.
Take multiple screenshots of the page (hero, sections, footer).

Then use this prompt in Claude Code:

```
I want to create a React/Vite project and copy this web page as a base.

Here are screenshots of the page: [attach screenshots]
Here is the URL: [paste URL]
Here is the HTML/CSS from inspect: [paste styles]

Goal: replicate the overall design feel — layout, color palette, typography, animations.
This is a base template, not a pixel-perfect clone.
Set up a local dev server so I can preview it immediately.
```

**Pro tip:** Use the Claude in Chrome extension — it navigates the inspiration page in a live browser, grabbing even more visual context than static screenshots alone.

### Step 3 — Refine with Screenshots

Once you have the base running, iterate by screenshotting what you don't like and feeding it back:

```
Here's a screenshot of the current state: [attach screenshot]

Issues to fix:
- [section name] feels too squished — needs more breathing room
- The boxes in [section] are too large, need to be smaller and centered
- [element] animation needs to feel smoother
- The copy in [section] needs to match this product: [describe your product/brand in 2-3 sentences]

Keep everything else as-is.
```

For updating copy/language, do a "verbal drop" — describe your product out loud, transcribe it, and paste as context:

```
Update all the copy on this site for the following product:
[paste your product description]

Match the tone to the existing design style. Don't change layouts or colors.
```

For premium UI components and animations, browse **21st.dev**, copy the component prompt, and paste:

```
Replace the current [hero animation / background graphic] with this component:
[paste 21st.dev prompt]
```

### Step 4 — Deploy

```
Push this project to my GitHub repository: [paste repo URL]
```

Then in Vercel:
1. Go to Overview → Add New → Project
2. Import the repo
3. Click Deploy → live in ~60 seconds

---

## Notes
- Goal is a **good enough base**, not a one-to-one clone — get 80% there with context, then refine
- Zero design skills needed — let screenshots do the explaining
- Works best with Claude Sonnet or better
- If Claude doesn't spin up a local server automatically, prompt: `"Set up a local dev server so I can preview this"`
- Use 21st.dev for ready-made animation prompts that slot cleanly into Claude
