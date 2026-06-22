---
title: "The Most Interesting Problems Are at the Boundaries"
date: "2026-06-22"
tags: ["interdisciplinary", "innovation", "problem-solving"]
---

# The Most Interesting Problems Are at the Boundaries

I was building a flashcard system and everyone told me to look at Anki.

"Anki is the gold standard," they said. "It has an algorithm. It has community decks. It has plugins."

So I tried it. And I hated it. Not because it was bad, but because it was solving the wrong problem.

Anki optimizes for retention. It uses a sophisticated algorithm to schedule reviews at optimal intervals. It's mathematically elegant. And it creates anxiety. Miss two days and you're staring at 300 due cards. The system punishes you for being human.

I didn't need a better algorithm. I needed a different model entirely.

## The Queueing Theory of Memory

I started thinking about my flashcards not as a scheduling problem, but as an inventory problem. A box of cards is a queue. When the queue gets too long, you process it. The length of the queue is your cognitive load.

This is Little's Law — a principle from operations research. L = λW. The average number of items in a system equals the arrival rate times the average time in the system.

I applied it to flashcards. The "arrival rate" is how many new cards I add. The "time in system" is how long they stay in each review level. The "average number of items" is the thickness of my deck.

The insight was stupidly simple: I don't need a calendar to tell me when to review. I need a ruler.

## Crossing Domains

This pattern repeats in everything I build. The most interesting solutions don't come from optimizing within a domain. They come from importing ideas from somewhere else.

When I built an AR engine, I didn't look at computer vision papers. I looked at game engine architecture. Feature matching is a database problem, not a machine learning problem. A binary index with hardware popcount outperforms a neural network for this specific task.

When I built a desktop Markdown reader, I didn't look at Electron apps. I looked at native application frameworks. The question wasn't "how do I bundle a browser?" It was "how do I render HTML without shipping 150MB of Chromium?"

When I built a Chinese learning platform, I didn't look at language apps. I looked at music information retrieval. Songs are already structured — verse, chorus, bridge — and that structure maps directly to grammatical concepts.

## The Default is Wrong

Every field has assumptions that are so deeply embedded that nobody questions them:

AR requires machine learning. Desktop apps require Electron. Learning requires screens. Flashcards require digital interfaces. WhatsApp bots require complex configuration.

These aren't truths. They're defaults. And defaults are dangerous because they feel like truths.

The best opportunities exist where two defaults collide. Where the assumption from one field meets the assumption from another, and both turn out to be wrong.

## How to See the Boundary

You don't find boundaries by being an expert. Experts are trapped by their expertise. They see the world through the lens of their field, and that lens filters out everything that doesn't fit.

You find boundaries by being bored. By learning enough to solve your immediate problem, then moving on. By accumulating a mental map of how different fields relate to each other.

I know just enough about queueing theory to map it to flashcards. Just enough about game engines to build an AR tracker. Just enough about music theory to structure language learning. I'm not an expert in any of these fields. I'm a tourist.

But tourists see things that locals don't. The local knows the default path. The tourist asks why the path exists.

## The Risk of Superficiality

Boundary-crossing has a failure mode: you read one blog post about a field and think you understand it. The Dunning-Kruger effect is strongest at boundaries because you don't know enough to know what you don't know.

The antidote is implementation. Ideas are cheap. If you can't build it, you don't understand it.

I didn't just think about Little's Law. I built a system around it. I tested it. I found the edge cases. I iterated. The theory was the starting point, but the implementation was where the real understanding happened.

## The Magic of Category Errors

When it works, the result feels like magic. Not because it's complex — often it's simpler than the conventional solution — but because it reframes the problem entirely.

Users don't see the boundary-crossing. They just see a tool that works better than it should. A flashcard system that doesn't create anxiety. An AR engine that doesn't need a GPU. A desktop app that starts in 50ms.

The compliment I love most is: "This shouldn't work, but it does."

That's the sound of a boundary being crossed.
