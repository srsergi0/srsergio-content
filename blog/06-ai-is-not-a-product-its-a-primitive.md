---
title: "AI Is Not a Product, It's a Primitive"
date: "2026-06-22"
tags: ["ai", "engineering", "philosophy"]
---

# AI Is Not a Product, It's a Primitive

There's a category error happening in software right now. People are building "AI apps" — standalone products where AI is the value proposition. Ask the AI a question. Generate an image. Summarize a document.

I think this is backwards. AI is not a product. It's a primitive — a building block, like a database or a network socket. The products that matter are the ones that use AI as infrastructure, not as output.

## The Wrapper Trap

The current wave of AI startups is mostly wrappers. They take an API call to GPT-4, add a pretty UI, and sell it as a product. Some are genuinely useful. But they're not defensible. The moment the underlying model improves or a competitor copies the interface, the value evaporates.

Wrappers are not products. They're demos. They show what AI can do, but they don't solve a problem that couldn't be solved more cheaply with a direct API call.

The real value is not in calling the AI. It's in what you do with the result.

## AI as Infrastructure

Look at how I use AI in my projects:

In a language learning platform, AI doesn't teach Chinese. It parses 1500 song lyrics into structured format, generates embeddings for semantic search, classifies grammar articles by difficulty. The product is the platform. AI is the pipeline.

In an MCP server for Spotify, AI doesn't play music. It translates natural language into API calls. The product is the integration. AI is the translation layer.

In an AR engine, AI doesn't do AR. But it generates embeddings for visual search, feeding into a vector database. The product is the search. AI is the encoder.

In every case, AI is invisible. It's not what the user sees. It's what makes what they see possible.

## The Primitive Mindset

Treating AI as a primitive changes how you design:

**You don't optimize for the AI call.** You optimize for what happens after. Latency matters less than integration. Accuracy matters less than usefulness.

**You design for failure.** AI is probabilistic. It hallucinates, misunderstands, varies in quality. If your product depends on AI being perfect, it's broken. If your product treats AI as one input among many, it fails gracefully.

**You compose, don't wrap.** The power of AI is in combination. AI + database + search + UI + workflow. Each piece does what it does best.

**You think in pipelines, not prompts.** A single prompt is a wrapper. A pipeline of AI calls, data transformations, validation steps, and feedback loops is a product.

## The Shift

We're in a transition period. Right now, "powered by AI" is a selling point. But novelty wears off. Soon, AI will be as unremarkable as "uses TCP/IP." The products that survive will be ones where removing AI would require redesigning the entire product.

The test is simple: if you can replace your AI with a cheaper alternative and the product still works, you're building a wrapper. If replacing the AI would require redesigning everything, you're building something real.

## The Future

The future of AI is not chatbots. It's not image generators. It's not "ask me anything" interfaces.

The future is AI as a sensor — reading the world and feeding structured data into systems that know what to do with it. AI that parses documents into databases. AI that translates speech into API calls. AI that generates embeddings for search. AI that classifies content, routes requests, adapts interfaces.

The future is AI as a compiler — transforming human intent into machine action. Not through prompts, but through integration. The user doesn't ask the AI to do something. They do something, and the AI makes it work.

The future is AI as invisible infrastructure — so woven into the product that you can't tell where the AI ends and the software begins.

That's the future I'm building for.
