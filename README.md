# Sergio Content Manager

Este repositorio contiene todo el contenido en formato Markdown que alimenta el portafolio. El sitio web descarga y procesa este contenido automáticamente en cada compilación.

## Guía de Configuración de Frontmatter

Cada archivo Markdown en las carpetas `project`, `study`, `research` y `work` debe iniciar con un bloque de metadatos (Frontmatter) en formato YAML. A continuación se detalla cómo configurar cada propiedad, con énfasis en el soporte multimedia:

### 1. `destacado` (Booleano)
Determina la importancia visual de la tarjeta en el diseño Bento Grid en pantallas grandes:
- `true`: La tarjeta será **destacada**. Ocupará el **doble de ancho** (2 columnas) en la cuadrícula de escritorio y mostrará un diseño extendido.
- `false` (por defecto): La tarjeta se mostrará en tamaño estándar (1 columna).

### 2. `imagen` (Texto, opcional)
URL absoluta de la imagen de portada o vista previa (por ejemplo, desde Unsplash o tu propio hosting).
- Sirve como poster o portada estática del video si se ha configurado la propiedad `video`.
- Si no hay un video configurado, se mostrará como una imagen estática con filtro grayscale que cambia a color completo al pasar el cursor.
- Ejemplo: `imagen: https://images.unsplash.com/photo-1531747118685-ca8fa6e08806?auto=format&fit=crop&w=1200&q=80`

### 3. `video` (Texto, opcional)
Habilita la reproducción multimedia dentro de la tarjeta usando nuestro **reproductor custom minimalista**. Soporta dos formatos:
- **YouTube**: Puedes pasar una URL completa de YouTube (ej. `https://www.youtube.com/watch?v=dQw4w9WgXcQ` o `https://youtu.be/dQw4w9WgXcQ`) o directamente el ID del video de 11 caracteres (`dQw4w9WgXcQ`). El reproductor cargará automáticamente el video usando la API oficial y ocultará los controles nativos.
- **MP4 Directo**: Cualquier enlace directo a un archivo de video que termine en `.mp4`. El reproductor creará un elemento HTML5 optimizado.
- *Nota*: La interacción con los controles del reproductor (play, pausa, volumen, pantalla completa) está protegida para evitar que se dispare accidentalmente el enlace de navegación de la tarjeta.

---

## Esquema Completo de Propiedades

| Campo | Tipo | Requerido | Descripción |
|---|---|---|---|
| `id` | Número | Sí | ID numérico único. |
| `tipo` | String (Enum) | Sí | Tipo de hito: `proyecto`, `estudio`, `investigacion` o `trabajo`. |
| `fecha` | String | Sí | Fecha en formato `YYYY-MM` (ej. `2024-06`) o simplemente `YYYY`. |
| `titulo` | String | Sí | Título principal de la tarjeta. |
| `subtitulo` | String | Sí | Subtítulo descriptivo. |
| `descripcion` | String | Sí | Resumen corto del hito. |
| `skills` | Lista (Strings) | Sí | Habilidades y tecnologías clave asociadas (se muestran como chips). |
| `destacado` | Booleano | No | Si es `true`, expande la tarjeta en el grid. |
| `imagen` | String | No | URL de la imagen de portada. |
| `video` | String | No | URL de YouTube, ID de YouTube, o URL MP4 directa. |
| `url` | String | No | URL del proyecto en producción o repositorio. |
| `institucion` | String | No | Nombre de la institución/empresa (habitual en estudios y trabajos). |

---

## Plantillas de Ejemplo

### Ejemplo 1: Proyecto Destacado con Video de YouTube

```yaml
---
id: 10
tipo: "proyecto"
fecha: "2024-06"
titulo: "AI-Powered Customer Service Platform"
subtitulo: "Giant Media · E-commerce"
descripcion: "Implementación de una plataforma de atención al cliente potenciada por modelos de lenguaje artificiales (RAG + GPT-4) para reducir tiempos de espera."
skills:
  - "AI"
  - "Python"
  - "Next.js"
imagen: https://images.unsplash.com/photo-1531747118685-ca8fa6e08806?auto=format&fit=crop&w=1200&q=80
video: "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
destacado: true
url: "https://github.com/srsergi0/customer-service-ai"
---

Escribe el contenido extendido de tu proyecto aquí en formato Markdown estándar...
```

### Ejemplo 2: Hito de Estudio Estándar con Video MP4

```yaml
---
id: 4
tipo: "estudio"
fecha: "2017-12"
titulo: "Master en Information Systems"
subtitulo: "Technology Management · Estados Unidos"
descripcion: "Estrategia tecnológica, gestión de proyectos IT y liderazgo de innovación."
skills:
  - "IT Strategy"
  - "Leadership"
  - "Gestión"
imagen: https://images.unsplash.com/photo-1523240795612-9a054b0db644?auto=format&fit=crop&w=1200&q=80
video: "https://assets.mixkit.co/videos/preview/mixkit-forest-stream-in-the-sunlight-529-large.mp4"
destacado: false
---

Detalles sobre las asignaturas cursadas o aprendizajes clave aquí...
```
