---
title: "Why I Build Everything From Scratch (Even When Libraries Exist)"
date: "2026-06-22"
tags: ["engineering", "learning", "craftsmanship"]
---

# Why I Build Everything From Scratch (Even When Libraries Exist)

"Why are you writing an AR tracker from scratch?"

"MindAR exists."

"Why build a PDF tool? There are dozens."

"Why write your own SRS algorithm? Anki is free."

I get this constantly. And the answer is not NIH syndrome. It's not ego. It's that building from scratch is the fastest way to understand something deeply. And understanding deeply is the prerequisite for building well.

## The Library Paradox

Libraries promise to save time. And they do — short term. You import, configure, and ship. The feature works. You move on.

But six months later, something breaks. Or you need a feature the library doesn't support. Or it's abandoned. Or a security vulnerability drops. Now you're debugging through layers of abstraction you didn't write, trying to understand decisions made by strangers.

The time you "saved" is being paid back with interest. And because you never understood the underlying problem, you're debugging from ignorance.

## What Building Teaches You

When you build from scratch, you don't just get working code. You get:

**A mental model.** You understand the problem space because you've mapped every corner. You know where complexity lives, where edge cases hide, and where elegant simplifications are possible.

**Transferable knowledge.** Binary matching for AR teaches you about database indexing. Queueing models for flashcards teach you about load balancing. The knowledge compounds.

**Better judgment.** Once you've built something hard, you can evaluate libraries accurately. You know which are well-designed and which are bloated because you've wrestled with the same problems.

**Confidence.** There's a specific confidence that comes from knowing you could build it yourself. It changes how you approach problems. You're not afraid of new domains because you know the process: start simple, iterate, refactor.

## The Efficiency Fallacy

People think building from scratch is inefficient. But efficiency depends on what you're optimizing for.

If you're optimizing for "time to first commit," libraries win. If you're optimizing for "time to deep understanding," building wins. If you're optimizing for "time to a solution that exactly fits my problem," building almost always wins.

A library solves the author's problem, not yours. Their assumptions are not your assumptions. Their constraints are not your constraints. Their abstractions leak in ways that don't matter to them but matter to you.

When you build from scratch, every line exists because you needed it. No unused features. No unnecessary abstractions. No compatibility layers for use cases you'll never encounter.

## The Scope Question

The key is scope. Building from scratch doesn't mean building everything. It means building the *core* and importing the *periphery*.

For an AR engine, the core is feature detection and matching. The periphery is image decoding and matrix math. Build the core, import the periphery.

For a chat SDK, the core is the message abstraction and session lifecycle. The periphery is WebSocket handling. Build the core, import the periphery.

For a learning platform, the core is the content model and algorithm. The periphery is the database and UI framework. Build the core, import the periphery.

The boundary between core and periphery is judgment. It depends on what makes your project unique. But the principle is always the same: own what differentiates you, outsource what doesn't.

## The Satisfaction of Craftsmanship

There's something else people don't talk about enough: the satisfaction of craftsmanship.

When you build something yourself, you feel a connection to it that imported code doesn't provide. You know why every decision was made. You remember the iterations, dead ends, breakthroughs. The code is a record of your thinking.

This isn't ego. It's engagement. Building things yourself keeps you curious, creative, continuously learning.

## The Balance

I'm not arguing against libraries. I'm arguing for *intentionality*. Every dependency should be a conscious choice, not a default. Every import should justify its existence.

The next time you reach for a library, ask: do I understand what this does? Could I build the part I need in a reasonable time? What am I trading away?

Sometimes the answer is "use the library." But more often than people think, the answer is "I'll build it myself." And those are the projects you remember.
