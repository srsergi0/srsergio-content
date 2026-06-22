---
id: 10
tipo: "proyecto"
fecha: "2024-06"
titulo: "AI-Powered Customer Service Platform"
subtitulo: "Giant Media · E-commerce"
descripcion: "Diseñé e implementé una plataforma de atención al cliente potenciada por AI para una empresa de e-commerce con 50K+ pedidos mensuales. El sistema reduce tiempos de respuesta un 70% y mejora la satisfacción del cliente un 45%."
skills:
  - "AI"
  - "Customer Experience"
  - "Cloud"
  - "Python"
  - "UX"
url: 
institucion: "Giant Media"
imagen: https://images.unsplash.com/photo-1531747118685-ca8fa6e08806?auto=format&fit=crop&w=1200&q=80
video: "https://www.youtube.com/watch?v=dQw4w9WgXcQ"
destacado: true
---

## El reto

Una empresa de e-commerce con 50K+ pedidos mensuales tenía un problema grave: su equipo de soporte estaba saturado. Los tiempos de respuesta promediaban 48 horas, la satisfacción del cliente estaba en 62%, y el churn estaba aumentando.

El CEO me pidió una solución que no fuera "solo un chatbot" — quería algo que realmente mejorara la experiencia del cliente sin reemplazar el toque humano.

## Mi enfoque

No empecé por la tecnología. Empecé por los datos.

### Fase 1: Análisis (2 semanas)
- Analicé 6 meses de tickets de soporte (12,000+ tickets)
- Identifiqué que el 68% de las consultas eran repetitivas (estado de pedido, devoluciones, guías de talla)
- Mapeé el customer journey completo y los puntos de dolor
- Entrevisté a 8 agentes de soporte y 15 clientes

### Fase 2: Diseño (3 semanas)
- Diseñé una arquitectura híbrida: AI para consultas repetitivas, humanos para casos complejos
- Creé un sistema de escalamiento inteligente que clasificaba la complejidad de cada consulta
- Definí los flujos de conversación para los 15 escenarios más comunes

### Fase 3: Implementación (6 semanas)
- Construí un RAG pipeline usando **OpenAI embeddings** + **Pinecone** para buscar respuestas relevantes en la base de conocimiento
- Implementé un **fine-tuned GPT model** entrenado con los mejores responses de los agentes humanos
- Creé una interfaz web con **Next.js** que se integró al chat existente del sitio
- Configuré **AWS Lambda** para el procesamiento serverless y **DynamoDB** para el historial

## Stack técnico

- **AI**: OpenAI API (GPT-4 + embeddings), Pinecone (vector DB), LangChain
- **Backend**: Python (FastAPI), AWS Lambda, DynamoDB
- **Frontend**: Next.js, Tailwind CSS, Socket.io para real-time
- **Infra**: Docker, AWS (Lambda, API Gateway, DynamoDB, S3)
- **Monitoring**: Datadog, custom dashboards con métricas de satisfacción

## Resultados

| Métrica | Antes | Después |
|---------|-------|--------|
| Tiempo de respuesta promedio | 48h | 4h |
| Satisfacción del cliente | 62% | 87% |
| Tickets resueltos sin humano | 0% | 68% |
| Costo por ticket | $12.50 | $3.20 |
| Churn mensual | 8.2% | 3.1% |

## Lo que aprendí

> *"El mejor chatbot es el que el cliente no nota. No se trata de AI vs humano — se trata de usar AI para que los humanos enfocen en lo que realmente importa."*

- **Los datos mandan**: Sin entender los datos, cualquier solución es un tiro a ciegas
- **El toque humano importa**: El 32% de consultas que requerían humano se manejaron mejor que nunca
- **Métricas = verdad**: Sin Datadog y los custom dashboards, no habría podido probar el ROI al CEO

Este proyecto me confirmó que la AI no reemplaza a las personas — las potencia.
