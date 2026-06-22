# Agent Guidelines for srsergi0's Content

## Writing Style — The "Bible" Voice

All portfolio entries, blog posts, and project descriptions must follow this exact writing style. This is non-negotiable.

### Core Philosophy

Write like Paul Graham, Peter Thiel, Ben Horowitz, Naval Ravikant, and Andrew Chen. Not like documentation. Not like marketing. Like a founder telling war stories to another founder over drinks.

**The voice is:**
- **Brutally honest** — say what everyone thinks but no one writes
- **Personal** — first person, always. "I was building..." not "This project solves..."
- **Opinionated** — strong takes, no hedging, no "I think maybe"
- **Concise** — short sentences, short paragraphs, no filler
- **Story-driven** — start with the problem you felt, not the solution you built
- **Anti-hype** — never use buzzwords, never oversell, never write like a landing page

### The Opening

**ALWAYS** start with the personal problem. Not the market opportunity. Not the tech stack. Not the features.

**BAD:**
```
Conversa is a zero-boilerplate WhatsApp SDK built with TypeScript and Bun...
```

**GOOD:**
```
I wanted to build a WhatsApp bot. Should be easy, right? There's Baileys — the gold standard. It's powerful. And it's a nightmare.
```

The first paragraph must make the reader feel the pain. If they don't feel it, they won't care about the solution.

### The Body

**Tell the story of discovery.** Not the architecture diagram.

- What assumption did everyone accept that turned out to be wrong?
- What did you try first that failed?
- What was the moment of insight?
- What trade-off did you make that others wouldn't dare?

**Use code ONLY when it illustrates the point.** Not as documentation. A single beautiful snippet beats ten pages of API reference.

**BAD:**
```
The SDK supports the following storage backends: File, SQLite, PostgreSQL, MySQL.
```

**GOOD:**
```
Session() takes a phone number and a callback. That's it. File, SQLite, Postgres, MySQL — pick one, or don't and use the default.
```

### The "Wow"

**Never explain why something is impressive.** Make the reader feel it.

**BAD:**
```
This project is impressive because it uses advanced computer vision algorithms...
```

**GOOD:**
```
Everyone told me AR needed TensorFlow.js. I tried it. 20MB of dependencies. 3-second initialization. And the tracking was worse than what I built with 500 lines of JavaScript.
```

The wow is in the contrast. In the defiance of expectations. In the simplicity that shouldn't work but does.

### The Ending

**End with a lesson, not a summary.** Something the reader can take away. A principle. A mindset shift. A question.

**BAD:**
```
In conclusion, this project demonstrates the importance of...
```

**GOOD:**
```
The lesson isn't technical. It's about questioning defaults. A text reader doesn't need to ship a browser engine. Most apps don't need to be heavy. They're heavy because nobody asked "what's the simplest thing that could work?"
```

### What to AVOID

- ❌ Lists of features
- ❌ Tables of specifications
- ❌ "Key Features" sections
- ❌ "Architecture Overview" sections
- ❌ Buzzwords ("scalable", "robust", "enterprise-grade", "AI-powered")
- ❌ Explaining what the project does — show what it lets you do
- ❌ Section titles like "Technical Stack", "Getting Started", "Installation"
- ❌ Writing for investors. Write for builders.
- ❌ Excessive adjectives. Let the facts be impressive.

### What to INCLUDE

- ✅ The moment you got angry enough to build it
- ✅ The assumption everyone accepted that you questioned
- ✅ The trade-off that looked crazy but worked
- ✅ The single line of code that captures the whole idea
- ✅ The thing that shouldn't work but does
- ✅ The realization that changed how you think

### Language

**Portfolio entries:** English. Always.

**Blog posts:** English. Always.

**Code comments:** English.

**Frontmatter/descriptions:** Spanish is acceptable for SEO/metadata, but the body must be English.

### Length

**Portfolio entries:** 300-600 words. No more. Get in, tell the story, get out.

**Blog posts:** 1000-2000 words. Long enough to develop an idea, short enough to not waste the reader's time.

### Formatting

- Use `##` for the first heading after frontmatter (not `#`)
- No Table of Contents. Ever.
- No badges, shields, or status indicators.
- Code blocks only when they serve the narrative.
- One-line quotes for emphasis are fine.
- Bold for the key insight, not for marketing.

### The Test

Before publishing, ask: **Would Paul Graham retweet this?**

If the answer is no, rewrite it.

### Examples of Perfect Entries

Reference these files as the gold standard:
- `project/2026-06/conversa.md`
- `project/2026-02/locus-ar.md`
- `project/2026-05/read-flashcard.md`
- `blog/01-the-case-for-deleting-dependencies.md`
- `blog/04-normalized-bloat.md`

### Summary

**Don't write about the project. Write about what the project taught you. The project is just the excuse to tell the story.**
