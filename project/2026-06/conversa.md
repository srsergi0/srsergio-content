---
id: 11
tipo: "proyecto"
fecha: "2026-06"
titulo: "Conversa SDK"
subtitulo: "Open Source · Chat SDK"
descripcion: "Zero-boilerplate WhatsApp SDK en TypeScript que automatiza autenticación, reconexión y almacenamiento de credenciales para construir bots en 3 líneas de código."
skills:
  - "TypeScript"
  - "WebSockets"
  - "API Design"
  - "Bun"
url: "https://github.com/srsergi0/conversa"
imagen: "https://images.unsplash.com/photo-1614064641938-3bbee52942c7?auto=format&fit=crop&w=1200&q=80"
destacado: true
---

I wanted to build a WhatsApp bot. Should be easy, right? There's Baileys — the gold standard for WhatsApp automation. It's powerful. It's battle-tested. And it's a nightmare to work with.

Messages are buried in objects nested five levels deep. Authentication is manual. Reconnection logic? You write it yourself. Credential storage? Figure it out. I spent two weeks on boilerplate before writing a single line of business logic.

The existing wrappers weren't better. They assumed Node.js. They tied you to databases. They added HTTP servers you didn't need. Every option was either too low-level or too opinionated.

So I built what I actually wanted: a library where `Session()` takes a phone number and a callback, and you're done. Authentication, reconnection, credential storage — it just works. File, SQLite, Postgres, MySQL. Pick one, or don't and use the default.

```ts
const bot = await Session('51900000000', { onCode });
const user = bot.to('51987654321@s.whatsapp.net');

user.onMessage(async (ctx) => {
  const reply = await ai.generate(ctx.text);
  await user.send(Text(reply));
});
```

That's the whole thing. No socket management. No event routing. No session lifecycle. The mental model is `bot.to(someone).send()`. Each conversation is its own object with its own handlers. The abstraction disappears completely.

I made it Bun-only. Lost the Node.js users. Gained cleaner code, native SQL, and no compatibility hacks. Sometimes the best decision is the restrictive one.

The interesting part wasn't solving the technical problems — it was making them invisible. The best API is the one users forget exists. Conversa is the most invisible thing I've built.
