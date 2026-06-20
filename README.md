# SrSergio Content

Contenido markdown para el portfolio srsergio.vercel.app. Cada push despliega automáticamente.

## Estructura

```
blog/
  └── YYYY-MM/
        └── post-slug.md
timeline/
  └── YYYY-MM/
        └── milestone-slug.md
```

Las carpetas `YYYY-MM` organizan el contenido por fecha. Ejemplo:

```
blog/
  ├── 2022-12/
  │     ├── no-code-tools.md
  │     └── why-must-a-company-grow.md
  └── 2024-06/
        └── ai-trends.md
timeline/
  ├── 2014-06/
  │     └── ingeniera-empresarial.md
  └── 2024-06/
        └── ai-customer-service.md
```

---

## Blog Posts

Ubicación: `blog/YYYY-MM/post-slug.md`

```markdown
---
title: "Mi artículo"
date: 2024-06-15
tags: ["AI", "Strategy"]
excerpt: "Descripción corta para la preview"
readingTime: "5 min"
published: true
---

## Introducción

Escribe aquí el contenido del artículo...

## Desarrollo

Más contenido...

## Conclusión

Ideas finales...
```

### Campos del frontmatter

| Campo        | Tipo     | Requerido | Descripción                         |
| ------------ | -------- | --------- | ----------------------------------- |
| `title`      | string   | Sí        | Título del artículo                 |
| `date`       | date     | Sí        | Fecha de publicación (YYYY-MM-DD)   |
| `tags`       | array    | Sí        | Etiquetas para filtrar              |
| `excerpt`    | string   | Sí        | Descripción corta (para previews)   |
| `readingTime`| string   | Sí        | Tiempo estimado de lectura          |
| `published`  | boolean  | No        | `false` para ocultar (default: true)|

---

## Timeline

Ubicación: `timeline/YYYY-MM/milestone-slug.md`

### Entrada con contenido detallado (página propia)

```markdown
---
id: 10
tipo: trabajo
fecha: "2024-06"
titulo: "Senior Consultant"
subtitulo: "Consultora X · Enterprise"
descripcion: "Breve descripción para la tarjeta"
skills:
  - "Strategy"
  - "AI"
  - "Leadership"
institucion: "Consultora X"
imagen:
url:
---

## El reto

Contexto del proyecto o rol...

## Mi enfoque

Cómo lo abordaste...

## Resultados

Logros y métricas...
```

### Entrada sin contenido (solo tarjeta en el timeline)

```markdown
---
id: 11
tipo: estudio
fecha: "2023-09"
titulo: "Machine Learning Course"
subtitulo: "Coursera"
descripcion: "Curso de ML aplicado a negocios"
skills:
  - "Machine Learning"
  - "Python"
institucion: "Coursera"
---
```

Sin contenido después del `---` final = sin link "Read full story".

### Campos del frontmatter

| Campo         | Tipo                  | Requerido | Descripción                              |
| ------------- | --------------------- | --------- | ---------------------------------------- |
| `id`          | number                | Sí        | ID único del hito                        |
| `tipo`        | enum                  | Sí        | `trabajo`, `estudio`, `investigacion`, `proyecto` |
| `fecha`       | string                | Sí        | Formato `YYYY-MM`                        |
| `titulo`      | string                | Sí        | Título del hito                          |
| `subtitulo`   | string                | Sí        | Subtítulo o contexto                     |
| `descripcion` | string                | Sí        | Descripción corta (para la tarjeta)      |
| `skills`      | array                 | Sí        | Habilidades relacionadas                 |
| `institucion` | string \\| null       | No        | Empresa o institución                    |
| `imagen`      | string \\| null       | No        | URL de imagen (reservado para futuro)    |
| `url`         | string \\| null       | No        | URL externa relacionada                  |

### Tipos de hito (`tipo`)

| Valor            | Categoría  |
| ---------------- | ---------- |
| `trabajo`        | Work       |
| `estudio`        | Study      |
| `investigacion`  | Research   |
| `proyecto`       | Project    |

---

## Cómo actualizar

### Nuevo artículo de blog

1. Crear carpeta si no existe: `blog/YYYY-MM/`
2. Crear archivo `slug-del-articulo.md`
3. Copiar la plantilla de Blog Posts
4. Push a `main` → se despliega automáticamente

### Editar contenido existente

1. Editar el `.md` correspondiente
2. Push a `main` → se despliega automáticamente

### Nuevo hito del timeline

1. Crear carpeta si no existe: `timeline/YYYY-MM/`
2. Crear archivo `slug-del-hito.md`
3. Copiar la plantilla de Timeline
4. Asignar un `id` único (mirar los existentes para evitar duplicados)
5. Push a `main` → se despliega automáticamente

### Ocultar un artículo

Cambiar `published: false` en el frontmatter. No se elimina, solo se oculta.

---

## Deploy

Cada push a `main` dispara un deploy automático a **srsergio.vercel.app** via GitHub Action.
