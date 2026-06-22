---
id: 19
tipo: "proyecto"
fecha: "2026-05"
titulo: "Mindo"
subtitulo: "Open Source · Chinese Learning"
descripcion: "Plataforma interactiva para aprender chino a través de la música — letras analizadas por AI, diccionario integrado, word maps y flashcards."
skills:
  - "Astro"
  - "React"
  - "TypeScript"
  - "AI"
  - "PostgreSQL"
  - "SRS"
url: "https://mindo-app.vercel.app"
imagen: "https://images.unsplash.com/photo-1526374965328-7f61d4dc18c5?auto=format&fit=crop&w=1200&q=80"
destacado: true
---

Chinese learning apps are either gamified fluff or sterile flashcard grinders. Neither teaches you how people actually speak. Music does — but raw lyrics are useless to a learner: no pinyin, no translation, no structure. Just a wall of characters.

I wanted to learn Chinese through the songs I actually listen to. So I built the platform I wished existed.

Mindo turns Chinese songs into interactive lessons. 1500 songs processed through Google Gemini Batch API. Each lyric goes through a pipeline: AI translation, Magma Syntax parsing, character segmentation, HSK grading, embedding generation. The result is searchable, clickable, connected to a full dictionary with 15 PostgreSQL tables and semantic search via pgvector.

**[mindo-app.vercel.app](https://mindo-app.vercel.app)**

The core is Magma V3.0 — a structured lyric format I designed. Each line breaks into blocks: `[CORE]` for subjects, `@SETTING@` for context, `<ACTION>` for verbs, `{BLOCK}` for objects, `*MOD*` for adverbs, `(FLUID)` for particles. Every character is clickable. Tap it and see pinyin, meaning, component tree, usage examples, example sentences.

```
"[CORE] 你和我 @SETTING@ 在这个世界 <ACTION> 相遇 {BLOCK} 最美的时光"
```

The YouTube player syncs in real-time. Lyrics scroll with the music. Tap any character to explore. Save words to your SRS deck. Review them later. The dictionary has three-tier search: exact match, word boundary, semantic vector via 768d embeddings.

The Word Map is a force-directed graph showing character relationships — components, usage, semantic similarity. Color-coded by HSK level. Explore from any character and discover vocabulary you haven't learned.

The SRS engine is a custom SM-2 variant with 8 levels. Cards drawn from words encountered in songs. Queue management runs in a Web Worker so the UI never stutters.

Grammar articles classified by HSK level via GPT-4o. Difficulty scores computed from constituent characters. Each article links vocabulary to dictionary entries.

The whole stack: Astro 6, React 19, Tailwind 4, Drizzle ORM, Neon PostgreSQL, pgvector. Web Workers for search and SRS. OPFS for client-side cache. Deployed on Vercel.

I built it because textbooks teach you how to order food. Music teaches you how people feel. If you're going to listen to a song fifty times anyway, you should come out knowing fifty new words.
