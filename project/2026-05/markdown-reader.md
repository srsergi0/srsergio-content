---
id: 14
tipo: "proyecto"
fecha: "2026-05"
titulo: "Markdown Reader"
subtitulo: "Open Source · Desktop App"
descripcion: "Native desktop Markdown reader built with Electrobun and Bun — 14MB size, 50ms startup time, without bundled Chromium."
skills:
  - "TypeScript"
  - "Bun"
  - "React"
  - "Desktop"
url: "https://github.com/srsergi0/markdown-reader"
imagen: "https://images.unsplash.com/photo-1526374965328-7f61d4dc18c5?auto=format&fit=crop&w=1200&q=80"
destacado: true
problem: "Every Markdown editor is a compromise — web apps with no file association, or Electron apps shipping 150MB just to display text."
solution: "A 14MB native desktop app using the system WebView instead of bundled Chromium, with instant file association and real-time sync."
impact: "Startup under 50ms with full GFM, live editing, folder browser, and cross-platform support from a single codebase."
statLabel: "BUNDLE SIZE"
statVal: "14MB"
---

I use Markdown for everything. Notes, docs, blog drafts, project specs. But every Markdown editor is a compromise. Web apps with no file association. Or Electron apps shipping 150MB to display text.

150MB. For a text reader. We've normalized this insanity.

I refused to accept it. So I built a Markdown reader with Electrobun — a framework that uses Bun + the system WebView instead of bundling Chromium.

The result: a 14MB native binary that starts in under 50ms. Double-click any `.md` file and it opens instantly. Edits in VS Code sync in real-time. Full GFM, syntax highlighting, Mermaid diagrams, folder browser, search, PDF export, dark mode.

```ts
import { app, BrowserWindow } from 'electrobun';

app.on('ready', async () => {
  const win = new BrowserWindow({ webview: true, fileAssociations: ['.md'] });
  await win.load('app.html');
});
```

That's the entire main process. No Chromium. No 150MB payload. The system's native WebView renders the React UI. The Bun process handles file I/O and search.

Development is where it shines: `bun run dev:hmr` starts Vite, Electrobun loads from `localhost:5173`, and React updates on save instantly. Same workflow as a web app, producing a native binary.

Cross-platform from day one. Windows, macOS, Linux. Same codebase.

The lesson isn't technical. It's about questioning defaults. A text reader doesn't need to ship a browser engine. Most apps don't need to be heavy. They're heavy because nobody asked "what's the simplest thing that could work?"

[Download the latest release](https://github.com/srsergi0/markdown-reader/releases/latest).
