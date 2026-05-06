# Entrega 2 — Diseño de Interfaces

**Grupo**: [Nombre del grupo]
**Proyecto**: [Nombre del proyecto elegido]
**Fecha de entrega**: 25/06/2026

---

## 1. Inventario de pantallas troncales

Identificar las **5 pantallas troncales** del sistema y justificar cada una desde un caso de uso de la Entrega 1.

| N° | Nombre de la pantalla | Actor principal | CU(s) cubierto(s) | Función (1 frase) |
|----|------------------------|------------------|---------------------|--------------------|
| 01 |                        |                  |                     |                    |
| 02 |                        |                  |                     |                    |
| 03 |                        |                  |                     |                    |
| 04 |                        |                  |                     |                    |
| 05 |                        |                  |                     |                    |

> Reglas: 5 pantallas exactas, cada una corresponde a al menos un CU especificado en E1, y los actores deben coincidir con la sección 1 de E1.

---

## 2. Trazabilidad pantalla ↔ E1

Verificar que cada pantalla se rastrea a un CU + HU + Actor identificados en la Entrega 1.

| Pantalla | CU(s) | HU(s) | Actor |
|----------|-------|-------|-------|
| 01 — [Nombre] |  |  |  |
| 02 — [Nombre] |  |  |  |
| 03 — [Nombre] |  |  |  |
| 04 — [Nombre] |  |  |  |
| 05 — [Nombre] |  |  |  |

---

## 3. Estructura de la entrega

| Ubicación | Contenido |
|-----------|-----------|
| `docs/2da-entrega/wireframes/0X-nombre-pantalla.png` | 5 PNGs exportados de Excalidraw, uno por pantalla |
| `frontend/index.html` (raíz del repo) | Landing del sitio con links a las 5 pantallas |
| `frontend/login.html`, `frontend/<pantalla-N>.html`, ... | 5 HTMLs, uno por pantalla, en raíz de `frontend/` |
| `frontend/assets/css/` | CSS propio (y overrides de Bootstrap si aplica) |
| `frontend/assets/img/` | Logos, ilustraciones y assets visuales |

> **Convención**: `docs/` lleva los artefactos de diseño y documentación (markdown + PNGs). `frontend/` lleva el código del sitio (HTML + CSS + imágenes). Cuando llegue el Bloque 3 (JavaScript), se agrega `frontend/assets/js/` al mismo árbol — el frontend evoluciona en capas, no se reescribe.

---

## 4. Decisiones técnicas y observaciones

> Espacio opcional para que el grupo documente decisiones de diseño no obvias: por qué eligieron Bootstrap o CSS puro, qué breakpoints definieron, qué componentes reutilizables identificaron, etc. La defensa oral va a preguntar por estas decisiones.

- Decisión 1:
- Decisión 2:
- ...

---

> Para los criterios de evaluación detallados ver [`rubrica.md`](./rubrica.md).
> Para la consigna completa ver [`consigna.md`](./consigna.md).
