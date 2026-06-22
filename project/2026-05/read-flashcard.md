---
id: 17
tipo: "proyecto"
fecha: "2026-05"
titulo: "Sistema READ"
subtitulo: "Open Source · SRS Protocol"
descripcion: "Protocolo de repetición espaciada analógica por desbordamiento — usa el grosor físico de tus mazos de tarjetas como sensor biométrico para ajustar intervalos de repaso."
skills:
  - "JavaScript"
  - "Bun"
  - "Spaced Repetition"
  - "Cognitive Science"
  - "UX Design"
url: "https://github.com/srsergi0/flashcard-calculator"
imagen: "https://images.unsplash.com/photo-1503676260728-1c00da094a0b?auto=format&fit=crop&w=1200&q=80"
destacado: true
problem: "Time-based SRS apps punish you for being human — skip two days and face hundreds of due cards with guilt, anxiety, and an endless backlog."
solution: "An analog overflow protocol where physical deck thickness triggers reviews, using queueing theory to adapt to your cognitive load without daily compliance."
impact: "No notifications, no guilt, no backlog — just a physical box telling you, in centimeters, when your brain is ready for more."
statLabel: "DAILY COMPLIANCE"
statVal: "NONE"
---

I used Anki for years. It's mathematically elegant. And it makes me miserable.

Skip two days and you're staring at 300 due cards. The algorithm punishes you for being human. The only way to "win" is to never stop. I tried. I failed. I felt guilty.

The problem isn't the algorithm. It's the model. Time-based SRS treats forgetting as a calendar event. But memory doesn't care about calendars. It cares about cognitive load, sleep, stress, how many new cards you added yesterday.

So I threw out the calendar and built something dumber and better.

READ uses the physical thickness of your card deck as a trigger. You have a box with four compartments: N1, N2, N3, N4. When a compartment gets full, you review it. Not because an app told you to. Because the box is literally overflowing.

The math is from queueing theory — Little's Law. L = λW. The average number of items in a system equals the arrival rate times the average time in the system. Applied to flashcards: the thickness of your deck is your cognitive load.

When your error rate rises, the system shrinks your box capacity, forcing more reviews and stopping new cards. When you're performing well, a consolidation factor expands capacity. The algorithm adapts to your state without requiring daily compliance.

The web app is just a calculator. It tells you how many cards fit in each level. The actual learning happens on paper, away from screens. No notifications. No guilt. No backlog.

If you stop for a week, nothing bad happens. Your levels desaturate. You come back to a clean slate. No anxiety. Just a physical box telling you, in centimeters, when your brain is ready for more.

[flashcard-calculator.pages.dev](https://flashcard-calculator.pages.dev)

Built it because I wanted the focus of paper flashcards with the precision of algorithmic scheduling. Most SRS apps try to replace the entire process. READ gets out of your way and just tells you when to pick up your box.
