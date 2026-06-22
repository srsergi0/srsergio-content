---
id: 13
tipo: "proyecto"
fecha: "2026-02"
titulo: "Locus AR"
subtitulo: "Open Source · AR Engine"
descripcion: "Motor de realidad aumentada 100% JavaScript para el navegador — sin TensorFlow.js, con tracking de imágenes ultrarrápido y compilación JIT."
skills:
  - "TypeScript"
  - "AR/VR"
  - "Computer Vision"
  - "Web Performance"
url: "https://github.com/srsergi0/taptapp-ar"
imagen: "https://images.unsplash.com/photo-1633356122102-3fe601e05bd2?auto=format&fit=crop&w=1200&q=80"
destacado: true
problem: "Everyone assumes AR needs TensorFlow.js — 20MB of dependencies, 3-second mobile initialization, and tracking worse than simple algorithms."
solution: "A zero-dependency image tracking engine built with 500 lines of JavaScript, a custom binary protocol, and hardware-accelerated matching."
impact: "14x faster compilation, 86% smaller target files, and detection under 10ms on a regular CPU."
statLabel: "DETECTION LATENCY"
statVal: "<10ms"
---

Everyone told me AR needed TensorFlow.js. "Computer vision requires machine learning," they said. So I tried it. 20MB of dependencies. 3-second initialization on mobile. And tracking that was worse than what I ended up building with 500 lines of JavaScript.

That's when I learned that the default answer is usually wrong.

Locus AR is a full image tracking engine with zero dependencies. No TensorFlow. No ML framework. Just a custom binary protocol, hardware-accelerated matching, and some geometry. It compiles targets 14x faster than the "standard" solution. Produces files 86% smaller. Detects in under 10ms on a regular CPU.

```tsx
<Locus targets={{ image: "/poster.jpg", label: "poster" }}>
  {(detections) => detections.map(d => (
    <LocusTransform key={d.targetIndex} matrix={d.worldMatrix}>
      <div className="card">AR Content</div>
    </LocusTransform>
  ))}
</Locus>
```

Under the hood it's a Nanite-style vision codec. Multi-octave features from a single keyframe. Binary matching with popcount. Fourier encoding for consistency checks. Delaunay meshes for tracking curved surfaces — t-shirts, posters on cylinders. No rigid homography.

| Metric | MindAR | Locus AR |
|--------|--------|----------|
| Compilation | ~23.5s | ~1.7s |
| Output Size | ~770 KB | ~103 KB |
| Dependencies | ~20MB | <100KB |
| Detection | ~50ms | <10ms |

I also added a visual search system that converts any image into a 16-byte fingerprint. 44 million similarity searches per second. Because once you've built a fast matcher, you realize it works for more than just AR.

The lesson: assumptions are expensive. "Everyone uses TF.js for AR" cost me three weeks of bloat before I questioned it. The right question isn't "what framework should I use?" It's "do I need a framework at all?"
