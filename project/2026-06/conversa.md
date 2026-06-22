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

Every time I wanted to build a WhatsApp bot, I ended up in the same place: Baileys is incredible, but working with it directly is a pain. Messages buried in deeply nested objects, manual authentication, reconnection logic you have to write yourself, credentials stored however you can manage. Weeks of boilerplate before writing a single line of business logic.

The existing wrappers all assumed Node.js. Many tied you to a database or an HTTP server. Nothing that just worked and felt clean.

So I built Conversa. `Session()` takes a phone number and an `onCode` callback — that's it. The library handles authentication, backoff reconnection, and credential storage across file, SQLite, Postgres, or MySQL. Three lines and you have a connected bot, with no idea what happened behind the scenes.

What makes it special isn't the code savings — it's that the mental model shifts. You don't think about sockets, or Baileys events, or lifecycle. You think `bot.to(someone).send(Text)`. Each conversation is its own object with its own handlers (`onMessage`, `onReaction`, `onReadReceipt`), automatically filtered by contact. Perfect for AI agents — no manual routing, each thread is its own context.

```ts
const bot = await Session('51900000000', { onCode });
const user = bot.to('51987654321@s.whatsapp.net');

user.onMessage(async (ctx) => {
  const reply = await ai.generate(ctx.text);
  await user.send(Text(reply));
});
```

The abstraction disappears. You don't need to understand how it works internally to make it work. Those are the best APIs — the ones you forget exist while using them.

On the technical side, I chose to make it Bun-only to use `Bun.SQL` and `Bun.Image` without fighting Node.js. A deliberate trade-off: lost Node users, gained simpler and faster code. I also kept it decoupled from web frameworks or servers — it runs in serverless, containers, anywhere.

Designing an API that feels obvious was harder than solving the technical problem. But watching how `bot.to(jid)` simplifies the mental model for everyone using it made it worth it. Sometimes the most powerful move is to restrict the runtime and focus entirely on making the experience seamless.
