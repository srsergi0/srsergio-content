---
id: 12
tipo: "proyecto"
fecha: "2026-06"
titulo: "booklet-impose"
subtitulo: "Open Source · PDF Tool"
descripcion: "Script en Python que transforma PDFs en formato booklet para impresión dúplex y plegado — ideal para fanzines, cuadernillos y autoedición."
skills:
  - "Python"
  - "PDF"
  - "Automation"
  - "Print"
url: "https://github.com/srsergi0/booklet-impose"
imagen: "https://images.unsplash.com/photo-1585829365295-ab7cd400c167?auto=format&fit=crop&w=1200&q=80"
destacado: true
---

I needed to print a zine. That's it. Take a PDF, turn it into a booklet, fold it in the middle.

The print shop wanted $40 and three days. The software options were either overpriced, required a GUI, or produced garbage. The ones that worked assumed I was a commercial print shop.

So I wrote a Python script. Two hours later I had my booklet. Then I kept going because the problem was more interesting than I thought.

Signatures for saddle stitching. Page ranges. Merging multiple PDFs. Gutter margins. Crop marks. Sheet numbering. HTML preview to see the layout before printing. Even de-imposition — reversing the process to extract original pages from a booklet.

```bash
python3 booklet-impose.py document.pdf booklet.pdf
```

One command. Zero config. Works with A5, A4, A3, Letter, Legal. Auto-detects page size.

Three years ago I would've downloaded some shareware with a watermark and called it a day. Now I build the tool I need in an afternoon. The difference isn't skill — it's the realization that most tools are just scripts that someone else wrote and decided to charge for.

What started as a quick hack became the most polished PDF imposition tool I could find. Not because I planned it. Because I kept hitting edge cases and fixing them. The best software comes from scratching your own itch until the itch is completely gone.
