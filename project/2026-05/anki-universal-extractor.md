---
id: 18
tipo: "proyecto"
fecha: "2026-05"
titulo: "Anki Universal Extractor"
subtitulo: "Open Source · Data Tool"
descripcion: "Extrae mazos de Anki (.apkg) a JSON limpio — libera tus flashcards de la base de datos de Anki para usarlas donde quieras."
skills:
  - "TypeScript"
  - "Bun"
  - "SQLite"
  - "Data Processing"
url: "https://github.com/srsergi0/anki-universal-extractor"
imagen: "https://images.unsplash.com/photo-1513542789411-b6a5d4f31634?auto=format&fit=crop&w=1200&q=80"
destacado: true
problem: "Anki traps your flashcards in a proprietary SQLite format with dynamic fields, hidden media maps, and aggressive database locks that prevent extraction."
solution: "A single-command Bun tool that extracts any .apkg to clean flat JSON with original media filenames automatically restored."
impact: "5000 cards extracted in under a second — your data is as easy to exit as it was to enter."
statLabel: "EXTRACTION SPEED"
statVal: "<1s"
---

Anki stores your cards in a SQLite database inside `.apkg` files. Sounds simple to extract.

It's not.

Dynamic field names that change per deck. Media files referenced by a number in a JSON map you have to reverse. A database lock that prevents reading while Anki is open — especially on Windows where the lock is aggressive. I spent an hour trying to extract my Japanese deck before I gave up and built a tool.

One command, zero config:

```bash
bun x github:srsergi0/anki-universal-extractor ./deck.apkg
```

Output is a `deck.json` with all cards in flat JSON, and a `deck_media/` folder with every image and audio using its original filename. Field mapping is automatic — detects the structure regardless of field names. Front/Back, Hanzi/Pinyin, Question/Answer. Whatever.

Under the hood: Bun.SQLite for native-speed reads. Manual media map resolution to restore readable filenames. A temporary file copy to handle Windows database locks.

```bash
bun x github:srsergi0/anki-universal-extractor jlpt-n5.apkg
# → jlpt-n5.json (5000 cards)
# → jlpt-n5_media/ (audio + images)
```

5000 cards extracted in under a second.

I built it to feed my physical flashcard system. Published it because a lot of people want to leave Anki without losing their data. Extracting your information from a closed ecosystem should be trivial. The fact that it wasn't is a failure of software design, not a technical limitation.

Your data should be as easy to exit as it was to enter. Anything less is a trap.
