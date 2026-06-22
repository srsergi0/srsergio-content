---
title: "Designing APIs That Users Can't See"
date: "2026-06-22"
tags: ["api-design", "developer-experience", "abstraction"]
---

# Designing APIs That Users Can't See

I was debugging a WhatsApp bot at 3 AM. The connection dropped. The reconnection logic failed. The credential storage threw an error. And I was reading through six layers of abstraction trying to figure out which layer had leaked its internal state into my code.

The library I was using was "powerful." It exposed every knob. Every flag. Every configuration option. You could tune the WebSocket frame size, the reconnection backoff strategy, the credential encryption algorithm. It was a masterpiece of flexibility.

It was also unusable.

## The Invisible Standard

The best API I've ever built is the one users forget exists. That's not a bug — it's the whole point.

Think about the tools you use every day that you don't think about. The file system. The network stack. The browser's rendering engine. These are incredibly complex systems, but they present such clean interfaces that you use them without conscious effort.

That's the standard: can the user accomplish their goal without knowing how it works?

Not "can they figure it out with documentation." Not "is it well-documented." The question is: do they need to understand it at all?

When the answer is no, you've built something that disappears. And disappearing is the highest compliment an API can receive.

## The Thread Model

I built a chat SDK where the entire interface is this:

```typescript
const user = bot.to('someone@service.net');
user.onMessage((msg) => {
  // Only fires for this user
});
await user.send('Hello');
```

That's it. No connection management. No event routing. No session state. The user has a conversation, and they can send and receive messages in it.

Behind the scenes? Authentication, backoff reconnection, credential storage across SQLite/Postgres/MySQL, message parsing, JID filtering, event deduplication. Hundreds of lines of code that the user will never see.

And they shouldn't see it. They didn't sign up to learn about WebSocket frames. They signed up to build a chatbot.

## The Leakage Trap

There's a temptation to expose internals because it feels honest. "Users should know how this works," you tell yourself. "They might need to debug it."

So you add a `sock` property. A `raw` event. A `debug` mode that dumps internal state. You rationalize it as "power user features."

But every leak is a permanent commitment. Once users depend on internals, you can never change them. The API ossifies around its implementation, and the implementation can never improve.

I've made this mistake. I added a `raw` event to an early version of my SDK. Within a month, users were building features around the raw event structure. When I wanted to change the internal protocol, I couldn't. I had broken my own API by being too generous.

If users need to debug, build proper observability. Structured logs. Metrics. Tracing. Don't expose your guts and call it a feature.

## How to Disappear

Start with the user's goal, not your implementation. What do they want to do? Send a message. Track an image. Print a booklet. Learn a song. Your API should map directly to that goal, with nothing in between.

Then ask: what's the minimum information they need to provide? For sending a message, it's the recipient and the content. Everything else is your problem.

Test it by explaining it to someone who's never used it. If you find yourself saying "first you need to understand how X works," your abstraction is leaking. Start over.

The best APIs don't teach you how they work. They teach you what you can build with them. And then they get out of the way.

## The Confidence of Invisibility

There's a strange confidence that comes from building something invisible. You can't show it off. You can't demo the abstraction layer. Users won't thank you for it — they'll only notice if it's bad.

But when it works, it feels like magic. Not because it's complex, but because it's so simple that it shouldn't work. The user does the obvious thing, and the obvious thing works. That's the goal.

Build APIs that disappear. It's the hardest thing to do and the easiest thing to use.
