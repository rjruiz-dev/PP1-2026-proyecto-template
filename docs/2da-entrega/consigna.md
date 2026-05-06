# Consigna — Entrega 2: Diseño de Interfaces

**Materia**: Práctica Profesionalizante I (PP1) — 2026  
**Fecha límite**: 25/06/2026  
**Formato de entrega**: completar la estructura del repositorio y subir el link del repo a Moodle.

| Carpeta | Contenido |
|---------|-----------|
| `docs/2da-entrega/README.md` | Inventario de las 5 pantallas + tabla de trazabilidad pantalla ↔ CU ↔ HU ↔ Actor |
| `docs/2da-entrega/wireframes/` | 5 PNGs exportados de Excalidraw (uno por pantalla) |
| `frontend/index.html` | Landing del sitio con links a las 5 pantallas |
| `frontend/login.html`, `frontend/<pantalla-N>.html`, ... | 5 archivos HTML, uno por pantalla troncal, en raíz de `frontend/` |
| `frontend/assets/css/` | CSS propio + overrides de Bootstrap |
| `frontend/assets/img/` | Logos, ilustraciones y assets visuales |

> **Convención**: `docs/` lleva los artefactos de diseño y documentación (markdown + PNGs). `frontend/` lleva el código del sitio (HTML + CSS + imágenes). Cuando llegue el Bloque 3 (JavaScript), se agrega `frontend/assets/js/` al mismo árbol — el frontend evoluciona en capas, no se reescribe.

---

## Objetivo

Traducir el análisis de la Entrega 1 a interfaces concretas. Diseñar las **5 pantallas troncales** del sistema, primero como wireframes humanos en Excalidraw, y luego codificadas progresivamente: HTML semántico → CSS propio → Bootstrap (recomendado). Cada pantalla debe responder a un caso de uso especificado en E1.

El objetivo NO es producir una interfaz pulida estéticamente, sino **demostrar el oficio del diseño de UI**: identificar componentes correctos, traducirlos a código semántico, aplicar estilos coherentes y construir un layout responsive.

---

## Actividades

### 1. Inventario de pantallas troncales

Identificar las **5 pantallas troncales** del sistema asignado y justificar la elección desde los CU de la Entrega 1.

Crear una tabla en `docs/2da-entrega/README.md` con los siguientes campos:

| Campo | Descripción |
|-------|-------------|
| **N°** | Número de pantalla (01 a 05) |
| **Nombre** | Nombre descriptivo de la pantalla (ej: "Login", "Detalle de pedido") |
| **Actor principal** | Quién la usa — debe coincidir con un actor identificado en E1 |
| **CU(s) cubierto(s)** | IDs de los casos de uso de E1 que esta pantalla materializa |
| **Función** | Una frase explicando qué permite hacer al usuario |

**Reglas**:
- Son **5 pantallas exactas** — ni más, ni menos.
- Cada pantalla debe corresponder a al menos un CU especificado en E1.
- No incluir pantallas administrativas genéricas ("Login" sí, "404 not found" no).

### 2. Wireframes en Excalidraw

Para cada pantalla, dibujar un wireframe en [excalidraw.com](https://excalidraw.com) y exportarlo como imagen PNG.

**Reglas del wireframe**:
- **Boceto a mano alzada** — Excalidraw tiene estilo "sketchy", aprovecharlo. NO buscar perfección visual.
- **Sin colores ni decoración** — el wireframe muestra ESTRUCTURA, no ESTÉTICA.
- **Componentes identificados** — cada elemento (botón, input, link, lista, tabla) debe ser reconocible.
- **Nombre de la pantalla** y **función en una frase** escritos arriba del boceto.

**Ubicación**: `docs/2da-entrega/wireframes/0X-nombre-pantalla.png`. Numerar 01 a 05 según el inventario.

### 3. HTML semántico

Para cada pantalla, crear un archivo HTML usando estructura semántica.

| Etiqueta | Cuándo usar |
|----------|-------------|
| `<header>` | Encabezado de la pantalla (logo, título principal) |
| `<nav>` | Navegación principal o secundaria |
| `<main>` | Contenido principal de la pantalla |
| `<section>` | Bloques temáticos dentro del contenido |
| `<article>` | Contenido autónomo (un pedido, una reserva, una entrada de listado) |
| `<aside>` | Información complementaria (filtros, panel lateral) |
| `<footer>` | Pie de pantalla |
| `<form>` | Formularios — siempre con `<label for>` matchando `<input id>` |

**Reglas**:
- Una pantalla = un archivo HTML en la raíz de `frontend/` (ejemplos: `frontend/login.html`, `frontend/catalogo.html`, `frontend/detalle.html`).
- Adicionalmente, mantener un `frontend/index.html` con links a las 5 pantallas (entry point del sitio).
- Inputs con `type` correcto (`email`, `password`, `number`, `date`, `tel`).
- Etiquetas `<label>` SIEMPRE asociadas a su `<input>` con `for` / `id`.
- Validación nativa HTML (`required`, `minlength`, `pattern`).
- **NO IA generativa** para escribir HTML completo. Pueden consultar dudas puntuales de sintaxis pero NO copiar páginas enteras generadas.

### 4. Estilos CSS propios

Sumar estilos a las pantallas con CSS escrito por el grupo (sin frameworks).

**Cada grupo decide la estrategia**:
- Un único `frontend/assets/css/styles.css` global, o
- Un CSS por pantalla en `frontend/assets/css/` (ej: `login.css`, `catalogo.css`), o
- Estilos en `<style>` dentro del HTML (válido pero no recomendado).

> **Recomendación**: arrancar con un `styles.css` global. Si crece demasiado, partirlo. Tener todo el CSS en `frontend/assets/css/` (no mezclado con HTMLs) facilita reusarlo entre pantallas y leer el repo.

**Lo que se evalúa**:
- **Selectores correctos** — usar clase para estilos reutilizables, `id` solo cuando es realmente único.
- **Box model entendido** — uso consciente de `padding`, `margin`, `border`, `box-sizing`.
- **Tipografía coherente** — máximo 2 familias de fuente, jerarquía visual clara entre h1/h2/h3/párrafo.
- **Responsive básico** — al menos una media query para mobile (< 768px).
- **NO copiar CSS completo de templates online** — el CSS debe poder explicarse línea por línea en la defensa oral.

### 5. Layout y responsividad (Bootstrap recomendado)

Refactorizar las pantallas a un sistema de grilla con componentes reutilizables. **Bootstrap está fuertemente recomendado** porque acelera el desarrollo, es estándar de industria, y resuelve responsividad por defecto. NO es obligatorio, pero el camino sin Bootstrap es más laburo para alcanzar el mismo resultado.

Si usan **Bootstrap**:
- Sistema de grilla (`container`, `row`, `col-*`).
- Componentes reutilizables (`navbar`, `card`, `form-control`, `btn`, `modal`).
- Responsive automático con breakpoints de Bootstrap.

Si NO usan Bootstrap (CSS puro):
- Sistema de grilla propio con CSS Grid o Flexbox.
- Componentes custom equivalentes (navbar propio, cards propias, etc.).
- Media queries para responsividad en mobile, tablet y desktop.

**Lo que se evalúa es el RESULTADO** (layout coherente, responsive en 3 breakpoints, profesionalidad visual), no la herramienta. La rúbrica aplica los mismos criterios a quien usa Bootstrap y a quien va por CSS puro.

### 6. Trazabilidad con Entrega 1

Mantener una tabla de trazabilidad en `docs/2da-entrega/README.md` (puede ser una columna agregada a la tabla de inventario) que muestre la relación pantalla ↔ CU ↔ HU ↔ Actor.

| Pantalla | CU(s) | HU(s) | Actor |
|----------|-------|-------|-------|
| 01 — Login | CU-01 | HU-01 | Empleado |
| 02 — Catálogo | CU-02, CU-03 | HU-02, HU-04 | Empleado |
| ... | ... | ... | ... |

**Verificación**: cada pantalla debe poder rastrearse a un actor y un CU de E1. Si una pantalla no corresponde a nada de E1, se discute en la defensa: o el CU faltó en E1, o la pantalla no es necesaria.

---

## Política IA del bloque

**Modo: LIMITADO.**

1. **HTML escrito a mano** — no copiar pantallas completas generadas por IA (ChatGPT, Copilot completando líneas enteras, etc.). Pueden consultar dudas puntuales de sintaxis.
2. **CSS propio** — los estilos los escriben ustedes. Pueden mirar referencias en MDN o W3Schools pero el CSS final debe poder explicarse en la defensa oral.
3. **Stitch (IA generativa de UI) llega en clase 11** — antes de eso, NO usar herramientas que generan UI a partir de prompts. La progresión "wireframe humano → HTML humano → CSS humano → Bootstrap → IA" es a propósito: la IA acelera al final, no reemplaza el oficio.

El código tiene que reflejar wireframes humanos. Si la pantalla codificada no se corresponde con un wireframe que el grupo dibujó antes, hay un problema y la defensa oral lo va a detectar.

---

## Defensa oral

La entrega incluye una **defensa oral presencial el 25/06/2026**, individual, donde cada integrante del grupo será evaluado por separado.

Durante la defensa, cada integrante responderá preguntas sobre cualquier sección del trabajo: por qué se eligieron esas 5 pantallas, qué diferencia hay entre `<section>` y `<article>` en su HTML, qué selector CSS se usó para tal efecto, cómo se logró la responsividad, etc.

La nota de defensa oral es **personal**: dos integrantes del mismo grupo pueden tener notas distintas en esta instancia.

---

## Guía de trabajo

(Pendiente — infografía a generar antes de la entrega)

![Guía de Trabajo Entrega 2 — placeholder](./guia-trabajo-entrega-2.png)
