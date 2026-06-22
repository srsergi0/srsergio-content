---
title: "The Case for Deleting Dependencies"
date: "2026-06-22"
tags: ["engineering", "minimalism", "dependencies"]
---

# The Case for Deleting Dependencies

I was building an AR engine and everyone told me I needed TensorFlow.js.

"Computer vision requires ML," they said. "You can't do feature detection without a neural network."

So I tried it. 20MB of dependencies. 3-second initialization on mobile. And the tracking was worse than what I ended up building with 500 lines of JavaScript and a binary protocol.

That's when I learned the most important lesson in software engineering: the default answer is usually wrong.

## The Tax Nobody Talks About

Dependencies are not free. Every `npm install` is a loan you're taking out against your future self, and the interest rate is brutal.

I imported a "lightweight" PDF library once. It was 800KB. Then I checked my bundle: 4MB. Transitive dependencies. Three libraries I didn't know I was using. One of them hadn't been updated in two years.

This is the tax nobody talks about. Not the initial cost — that's zero. The cost comes later. When something breaks at 2 AM and you're reading someone else's source code, trying to understand assumptions made by a developer who left the company three years ago.

When a security vulnerability drops and you have to update, but the update breaks your build, and now you're reading CHANGELOGs for six packages trying to figure out which one changed its API.

When you want to optimize startup time and you realize that 60% of your bundle is code you never execute.

## The Confidence Trap

Here's why we do it: confidence.

Importing a library feels safe. Thousands of people use it. It has tests. It has documentation. If something goes wrong, it's not your fault — it's the library's fault.

Building it yourself feels dangerous. What if you get it wrong? What if there's an edge case you missed? What if someone reviews your code and sees you reinvented the wheel?

But I've found the opposite is true. The more dependencies you have, the less confident you can be. Because you don't understand your own system. It's a black box inside a black box inside a black box.

When I built my own AR tracking engine, I knew exactly how it worked. Every algorithm. Every edge case. Every failure mode. When a user reported a bug, I could trace it in my head. No debugging through abstraction layers. No reading minified source code. Just my code, doing exactly what I told it to do.

That's real confidence. Not the borrowed confidence of a popular GitHub repo, but the earned confidence of understanding your own system.

## The Questions That Matter

Before I import anything now, I ask four questions:

**Do I need this, or do I just think I need it because everyone else uses it?**

Most dependencies are social proof, not technical necessity. We import React because everyone imports React. We use Express because everyone uses Express. But "everyone does it" is not a reason. It's an excuse for not thinking.

**What's the smallest version of this feature that solves my problem?**

Often I need 5% of a library's functionality. The other 95% is baggage I'm carrying for no reason. A few hundred lines of custom code beats thousands of lines of imported complexity.

**What am I giving up?**

Every dependency is a trade. You trade understanding for convenience. You trade control for features. You trade simplicity for "best practices." Make sure you're getting the better end of the deal.

**Can I build it in less time than it takes to learn the API?**

Sometimes the answer is yes. Learning a complex library can take days. Building the part you need might take hours. We overestimate the difficulty of building and underestimate the difficulty of learning someone else's abstraction.

## When to Say Yes

I'm not a purist. There are good reasons to use libraries:

Cryptography. Don't roll your own. The cost of getting it wrong is catastrophic and the expertise required is deep.

Database drivers. The wire protocol is not where you add value. Use the official driver.

Image codecs. Parsing JPEG is not a learning experience. It's a bug farm.

But everything else is negotiable. Everything else is a choice, not a requirement.

## The Real Optimization

The industry talks about performance optimization: faster algorithms, better caching, smaller bundles. But the biggest optimization is not doing the work in the first place.

The fastest code is the code you don't write. The smallest bundle is the one with fewer imports. The most maintainable system is the one you fully understand.

Start with subtraction. Delete before you add. Question every import. Build what you need, not what the ecosystem tells you to need.

Your future self will thank you at 2 AM when the system breaks and you know exactly why.
