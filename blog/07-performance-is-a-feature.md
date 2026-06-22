---
title: "Performance Is a Feature Users Won't Thank You For (Until It's Gone)"
date: "2026-06-22"
tags: ["performance", "user-experience", "craftsmanship"]
---

# Performance Is a Feature Users Won't Thank You For (Until It's Gone)

Nobody has ever said "I love this app because it starts fast." They just use it. They don't notice the 50ms startup or instant response because it feels natural.

But when performance is bad, users notice immediately. The 5-second startup. The frozen UI. The stuttering animation. These are the things that make people close the app and never come back.

Performance is an invisible feature. It's only visible in its absence.

## The Invisibility Problem

This creates a perverse incentive. Performance is expensive to build and impossible to market. You can't put "starts in 50ms" on a landing page and expect conversions. Users don't care until they've already downloaded.

Meanwhile, features are cheap to market and expensive to build. "Now with AI!" sells. "Now with 50ms startup!" doesn't. So teams optimize for features over performance, and the result is software that does more but feels worse.

This is how we end up with 150MB text editors that take 3 seconds to open. The team added features, one by one, each justified in isolation. Nobody decided to make it slow. It just happened, feature by feature, until slowness became the default.

## The Cost of Slowness

Slow software has real costs:

**Attention fragmentation.** Every second of waiting is a second where the user might switch contexts. Check their phone. Open another app. Get distracted.

**Cognitive load.** Fast software feels effortless. Slow software feels like work. When every interaction has latency, the user starts anticipating the delay. They pause before clicking. They hesitate before typing.

**Battery and heat.** Inefficient software drains batteries and generates heat. On mobile, this is a dealbreaker.

**Context switching.** In development, slow build times break flow state. Every second waiting for compilation is a second not solving problems.

## Why Performance Matters Anyway

If performance is invisible, why invest in it?

Because performance is trust. When software responds instantly, it feels reliable. It feels like an extension of your intent rather than a separate entity.

Fast software makes users more confident. They click more freely. They explore more deeply. They take more risks.

Performance is also a competitive advantage, even if users can't name it. They'll say "this app feels better" without knowing why. The why is the 50ms response time, the instant transitions, the lack of loading spinners. It's the absence of friction.

## The 10x Rule

I use a heuristic: every layer of abstraction should be 10x faster than the layer below it, or it shouldn't exist.

This forces you to question whether an abstraction is earning its keep. If a framework adds 100ms of overhead for a 10ms operation, it's not an abstraction — it's a tax.

The same applies to dependencies. If a library makes your app 10x slower for a feature you use 10% of the time, you're paying the cost 100% of the time for a benefit 10% of the time.

## How to Build for Performance

Building for performance is not about optimization. It's about design. Performance is determined by architecture, not implementation efficiency.

**Start with constraints.** Define performance budgets before writing code. "This screen must render in 16ms." "This API must respond in 100ms." "This app must start in 50ms." Constraints force creative solutions.

**Measure everything.** You can't optimize what you don't measure. Profile early, profile often. Not just for bottlenecks, but for trends.

**Delete before optimizing.** The fastest code is the code that doesn't run. Before optimizing a slow function, ask if you can remove it entirely.

**Think in milliseconds.** Users perceive time in milliseconds. 100ms feels instant. 300ms feels noticeable. 1 second feels broken. Design for the thresholds.

**Feel it yourself.** Use your software on slow hardware, slow connections, old devices. Performance is an empathy exercise.

## The Long Game

Performance is a long game. The benefits compound. A fast codebase is easier to maintain because it's simpler. A fast product is easier to grow because users stick around. A fast development workflow is easier to iterate because feedback loops are tight.

The ROI of performance is hard to measure but impossible to ignore. It's the difference between software that people use and software that people love.

Nobody will thank you for the 50ms startup. But they will use your app every day, tell their friends, and never think about switching. That's the reward.
