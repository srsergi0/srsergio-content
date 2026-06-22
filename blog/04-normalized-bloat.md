---
title: "Normalized Bloat: How We Learned to Stop Questioning 150MB Text Editors"
date: "2026-06-22"
tags: ["performance", "bloat", "industry-critique"]
---

# Normalized Bloat: How We Learned to Stop Questioning 150MB Text Editors

There is a 150MB application on your computer whose sole purpose is to display text files.

You don't question this. Nobody questions this. "Desktop app" and "ships a browser engine" have become synonymous in our minds. We've been boiled slowly, feature by feature, until we accept insanity as normal.

I only noticed because I was trying to build a Markdown reader.

## The Frog in the Pot

I wanted to read Markdown files. Simple enough. I tried the existing tools. Web apps with no file association. Electron apps that ate 150MB of RAM and took 3 seconds to start.

Three seconds. To open a text file.

I measured it. 150MB bundle. 2-5 second startup. 400MB of RAM to display a 2KB file. This is normalized bloat — inefficiency accepted because it's the default.

The same pattern everywhere:

AR tracking that requires a 20MB ML framework, when binary matching works better. Chat SDKs that need database wrappers and HTTP servers, when a simple abstraction suffices. Spaced repetition apps that trap you in proprietary formats, when paper cards work.

Each became "standard" not because it's optimal, but because it's convenient. And convenience, once normalized, becomes invisible.

## Why We Accept It

Three forces normalize bloat:

**The default effect.** When everyone uses Electron, Electron becomes the default. Defaults reduce decision fatigue — but they also reduce critical thinking. You stop asking if the default is right.

**Social proof.** "If Google does it, it must be right." Big companies ship bloated software because they have infinite resources. Small developers copy them because they want to look professional. The result is a cargo cult of complexity.

**Sunk cost.** Once you've invested in learning a framework, questioning it feels like admitting a mistake. So you double down. The bloat becomes self-reinforcing.

## The True Cost

Bloat has costs we ignore because they're distributed:

**Performance.** Users on old hardware pay the price. The developer with a MacBook Pro never feels it.

**Energy.** Every wasted megabyte contributes to global energy consumption. Software has a carbon footprint.

**Maintenance.** Dependencies attract dependencies. Soon you're maintaining a tree of packages, each with breaking changes and security patches.

**Agency.** The more layers you accept, the less you understand your own system. You become a configuration manager, not a builder.

## How to Resist

Start with subtraction. Before adding anything, ask what you can remove. What's the minimum viable implementation? Can you solve this problem with what's already available?

Question every dependency. What does this library give me? What does it cost me? Is there a simpler alternative? Can I build the part I need in less code than the import statement?

Measure what matters. Not benchmark scores — user experience. Startup time. Bundle size. Memory footprint. These metrics are invisible in development but everything in production.

Build for constraints. A 432×514 watch screen forces different thinking. A 14MB bundle limit forces different dependencies. Constraints breed creativity; abundance breeds bloat.

Ship the alternative. The most effective way to challenge a default is to build something better. A 14MB Markdown reader doesn't do everything VS Code does. It does one thing, instantly.

## The Future

I believe we're entering an era where bloat becomes a competitive disadvantage. Users are increasingly sensitive to performance. Developers are increasingly frustrated with dependency hell. Platforms are increasingly restrictive.

The tools that win will do less, better. The frameworks that thrive will stay small. The developers who succeed will question defaults instead of accepting them.

The 150MB text editor is not inevitable. It's just normalized. And normalization can be unlearned.
