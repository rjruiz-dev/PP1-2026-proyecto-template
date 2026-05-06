# Rúbrica de Evaluación — Entrega 2: Diseño de Interfaces

**Materia**: Práctica Profesionalizante I (PP1)  
**Carrera**: Técnico Superior en Desarrollo de Software — 2do año  
**Entrega**: 2 — Diseño de Interfaces  
**Fecha límite**: 25/06/2026

---

## Criterios de evaluación por actividad

### Actividad 1 — Inventario de pantallas troncales (8%)

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Cantidad correcta | Hay exactamente 5 pantallas listadas, ni más ni menos. | Hay 5 pantallas pero alguna incluye sub-pantallas confundidas como pantallas distintas. | Hay menos de 5 o más de 5 pantallas, sin justificación clara. |
| Justificación desde CU | Cada pantalla referencia uno o más CU especificados en E1, y la relación es directa (la pantalla materializa el flujo del CU). | La mayoría de las pantallas referencian CU pero alguna referencia es débil o forzada. | Las pantallas no referencian CU, o las referencias son a CU inexistentes en E1. |
| Coherencia con actores | Cada pantalla identifica un actor principal que existe en la sección 1 de E1. | Hay coherencia general pero algún actor aparece con nombre distinto al usado en E1. | Los actores de las pantallas no coinciden con los actores de E1. |

---

### Actividad 2 — Wireframes en Excalidraw (15%)

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Cantidad y completitud | Hay 5 wireframes, uno por pantalla, todos exportados a PNG en `wireframes/`. | Hay 5 wireframes pero alguno está incompleto (sin nombre, sin función, faltan componentes obvios). | Hay menos de 5 wireframes, o varios están vacíos o ilegibles. |
| Identificación de componentes | Cada wireframe muestra los componentes correctos para su CU (inputs, botones, listas, etc.) y son reconocibles aunque sean sketchy. | La mayoría de los componentes están identificados pero algún wireframe omite un componente esperable (ej: Login sin link "olvidé contraseña"). | Los wireframes no muestran componentes claros, o los componentes presentes no corresponden al CU. |
| Estilo wireframe (no mockup) | Los bocetos son a mano alzada, sin colores, sin fondos, sin imágenes decorativas. Estructura por sobre estética. | La mayoría son bocetos sketchy pero alguno intenta ser un mockup pulido (con colores, sombras, imágenes). | Los wireframes son mockups detallados (con colores, imágenes, estilos) y no muestran la estructura como herramienta de pensamiento. |
| Nombre y función declarada | Cada wireframe tiene escrito arriba: nombre de la pantalla + 1 frase que describe la función. | La mayoría tiene nombre pero la frase de función es vaga, genérica, o falta en algún wireframe. | Los wireframes no tienen nombre claro ni descripción de la función. |

---

### Actividad 3 — HTML semántico (17%)

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Etiquetas semánticas | Las pantallas usan correctamente `<header>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`, `<nav>`, `<form>` según corresponda. No hay `<div>` donde aplica una etiqueta semántica. | La mayoría usa semántica correcta pero algún bloque debería ser semántico y se modela con `<div>`. | Las pantallas son `<div>` soup — todo encapsulado en divs sin etiquetas semánticas. |
| Formularios bien estructurados | Todos los inputs tienen `<label for>` matchando `id`, los `type` son correctos (`email`, `password`, `number`, etc.) y se usa validación nativa (`required`, `minlength`, `pattern`). | La mayoría de los formularios están bien pero algún input no tiene label asociada o tiene `type` incorrecto (ej: `text` para email). | Los formularios no tienen labels asociadas, o todos los inputs son `type="text"` sin importar su contenido. |
| HTML válido | Las pantallas pasan validación del W3C Validator sin errores críticos. La estructura del documento (DOCTYPE, html, head, body) es correcta. | Hay errores menores de validación (ej: atributos deprecados, anidamiento permitido pero feo) pero la estructura general es correcta. | Hay errores críticos: tags mal cerrados, anidamiento inválido, falta DOCTYPE, etc. |
| Coherencia con wireframe | Cada pantalla codificada se corresponde con su wireframe (mismos componentes, mismo orden general). | La mayoría coincide pero alguna pantalla agregó o sacó componentes que no estaban en el wireframe sin justificación. | Las pantallas codificadas no se corresponden con los wireframes — el HTML cuenta una historia distinta. |

---

### Actividad 4 — Estilos CSS propios (15%)

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Selectores | Se usan clases para estilos reutilizables y `id` solo cuando es realmente único. Selectores específicos sin abuso de `!important`. | El uso de selectores es mayormente correcto pero hay casos donde se usa `id` para estilos que deberían ser clase. | Se abusa de `id` para estilos, hay múltiples `!important`, o selectores con sobre-especificación (ej: `body div ul li a`). |
| Box model | El uso de `padding`, `margin`, `border` y `box-sizing` es consciente y produce el espaciado deseado. Los elementos no tienen overflow inesperado ni se rompen al cambiar el contenido. | El box model está entendido en general pero hay algunos lugares donde el padding/margin produce gaps incorrectos o elementos demasiado pegados. | El box model no se entiende: elementos rompen el layout, padding/margin se mezclan, los elementos se desbordan. |
| Tipografía y jerarquía visual | Se usan máximo 2 familias de fuentes, los tamaños de h1/h2/h3/p tienen jerarquía clara, line-height y letter-spacing son legibles. | La tipografía es funcional pero la jerarquía entre niveles no está marcada (todo se ve similar) o hay 3 o más familias de fuente. | No hay jerarquía tipográfica, o se usan fuentes ilegibles, o el texto se ve apretado/disperso. |
| Responsive básico | Hay al menos una media query que adapta el layout a mobile (< 768px) y se verifica que las pantallas se ven correctamente en mobile. | Hay alguna media query pero el responsive es incompleto (algunas pantallas se ven mal en mobile). | No hay media queries, o el sitio no es usable en mobile (overflow horizontal, texto cortado, botones inalcanzables). |

---

### Actividad 5 — Layout y responsividad (Bootstrap recomendado) (15%)

Esta actividad evalúa el **resultado** (grilla coherente, componentes reutilizables, responsividad completa, profesionalidad visual). Los criterios aplican igual a quien usa Bootstrap y a quien va por CSS puro.

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Sistema de grilla | Las pantallas usan un sistema de grilla coherente (Bootstrap grid, CSS Grid o Flexbox bien aplicado) y los elementos están alineados con respecto a esa grilla. | Hay sistema de grilla en la mayoría de pantallas pero alguna usa floats antiguos o posicionamiento absoluto innecesario. | No hay sistema de grilla — los elementos están posicionados arbitrariamente, sin alineación entre pantallas. |
| Componentes reutilizables | Las pantallas usan componentes consistentes (mismo navbar, mismas cards, mismos botones) ya sea con Bootstrap o con CSS custom. Ningún componente está duplicado con código distinto. | La mayoría de los componentes son consistentes pero alguno está repetido con estilos ligeramente distintos en otra pantalla. | Cada pantalla tiene sus propios estilos sin reutilizar componentes — el navbar de la pantalla 1 no se parece al de la pantalla 3. |
| Responsividad completa | Las 5 pantallas funcionan correctamente en mobile (< 768px), tablet (768–1024px) y desktop (≥ 1024px). El contenido se reorganiza, no se rompe. | Mobile y desktop funcionan bien pero tablet tiene algún layout intermedio raro, o alguna pantalla rompe en algún breakpoint. | El responsive solo funciona en una resolución — al cambiar de tamaño la pantalla se rompe o el contenido se desborda. |
| Profesionalidad visual | El layout tiene alineación limpia, espaciado proporcionado, jerarquía visual clara. Se ve como un sitio real, no como un ejercicio. | Es funcional y ordenado pero algún detalle (espaciado entre secciones, alineación de columnas) se siente inconsistente. | El layout se ve desprolijo: elementos desalineados, espaciados arbitrarios, jerarquía rota. |

---

### Trazabilidad transversal (5%)

Este criterio evalúa la **coherencia** entre las pantallas de E2 y los artefactos de E1.

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Pantalla a CU | La tabla de trazabilidad mapea cada pantalla a uno o más CU de E1, y la relación es directa (la pantalla muestra la UI del CU). | La mayoría de las pantallas mapean a CU pero hay 1 o 2 mappings forzados o ambiguos. | No hay tabla de trazabilidad, o las pantallas mapean a CU que no existen en E1. |
| Actores consistentes | Los actores de las pantallas coinciden con los actores de E1 (mismo nombre, mismo rol). | Hay coherencia general pero algún actor aparece con nombre distinto al de E1 (ej: "Cliente" en E1, "Usuario" en E2). | Los actores de las pantallas no se corresponden con los de E1, o hay actores nuevos sin justificación. |
| Pantallas a wireframes | Cada pantalla codificada se corresponde con un wireframe en `wireframes/`. Los componentes mostrados son los mismos. | La mayoría coincide pero alguna pantalla agregó o quitó componentes que no estaban en el wireframe sin justificarlo. | Las pantallas codificadas y los wireframes parecen sistemas distintos. |

---

## Defensa oral individual (25%)

La entrega incluye una **defensa oral presencial el 25/06/2026** donde cada integrante del grupo será evaluado de forma **individual**. El objetivo es verificar que cada persona entiende y puede explicar el diseño entregado, no solo que participó en su confección.

Durante la defensa, cada integrante responderá preguntas sobre cualquier aspecto del trabajo: por qué se eligieron esas 5 pantallas, por qué un componente se modeló así y no de otra forma, qué selectores CSS se usaron, cómo se logró la responsividad, qué diferencia hay entre `<section>` y `<article>` en su pantalla, etc. La nota de defensa oral es **personal**: dos integrantes del mismo grupo pueden tener notas distintas en esta instancia.

El peso de la defensa en E2 es **mayor que en E1 (25% vs 20%)** porque el diseño de interfaces es **más fácil de copiar o generar con IA** que el análisis. La defensa oral es la salvaguarda que asegura que el alumno entiende lo que entregó.

**No alcanza con haber escrito una parte del código.** Cada integrante debe poder explicar las decisiones del grupo completo: por qué se usó esa estructura semántica, qué efecto produce un `padding` sobre un elemento con `display: flex`, por qué tal media query y no otra, qué hace `flex-wrap` aplicado a una grilla, etc.

Si un integrante no puede explicar partes que no escribió personalmente, la nota de defensa refleja esa falta de comprensión.

---

## Tabla resumen de pesos

| # | Actividad | Peso |
|---|-----------|------|
| 1 | Inventario de pantallas troncales | 8% |
| 2 | Wireframes en Excalidraw | 15% |
| 3 | HTML semántico | 17% |
| 4 | Estilos CSS propios | 15% |
| 5 | Layout y responsividad (Bootstrap recomendado) | 15% |
| T | Trazabilidad transversal | 5% |
| D | Defensa oral individual | 25% |
| | **Total** | **100%** |

---

## Notas importantes

- La nota del documento (actividades 1 a 5 + trazabilidad) es **grupal**. La nota de defensa oral es **individual**. La nota final de cada alumno combina ambas.
- Un trabajo puede tener buena nota en cada actividad por separado pero baja nota en trazabilidad si las pantallas no se hablan con E1. Verifiquen la coherencia con E1 antes de entregar.
- **Bootstrap es fuertemente recomendado pero no obligatorio.** Si eligen CSS puro, asuman que van a invertir más tiempo para alcanzar el mismo resultado. La rúbrica evalúa el RESULTADO (layout, responsive, profesionalidad), no la herramienta.
- **Política IA: limitado.** Stitch desde clase 11. Antes, escritura humana — el código debe reflejar wireframes humanos. Si la defensa oral muestra que un integrante no puede explicar HTML/CSS de su pantalla, se evaluará como copia con IA y se aplicarán las consecuencias del código de honestidad académica.
- Si las pantallas no se ven en el navegador (errores que rompen la página), se evalúan con la nota mínima en la actividad correspondiente. Verifiquen que cada HTML abre y se ve antes de entregar.
- Las entregas fuera de la fecha límite se evalúan con los criterios de esta rúbrica pero con penalización según el reglamento de la materia.
