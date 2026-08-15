# Rúbrica de Evaluación — Entrega 3: Frontend Codificado

**Materia**: Práctica Profesionalizante I (PP1)
**Carrera**: Técnico Superior en Desarrollo de Software — 2do año
**Entrega**: 3 — Frontend Codificado
**Fecha límite**: 03/09/2026

---

## Criterios de evaluación por actividad

### Actividad 1 — Organización del código y datos (5%)

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Estructura y carga | El JS vive en `assets/js/` y los datos en `data/`. La división en archivos es coherente y el grupo puede explicar por qué la eligió. El `<script src>` está al final del `<body>` y ninguna pantalla tira errores al cargar. | La estructura es correcta pero la división es arbitraria (un solo `.js` gigante, o archivos partidos sin criterio), o hay algún warning en consola. | Hay JavaScript embebido en `<script>` dentro del HTML, o la consola tira errores al cargar la página. |
| Modelado de los datos | Los JSON son válidos, tienen al menos 4 ítems por listado, los nombres de campo son consistentes en todo el proyecto y los datos son coherentes con la historia de E2. | Los JSON son válidos pero los datos son de relleno (`"item 1"`, `"prueba"`) o los nombres son inconsistentes entre archivos. | Los JSON son inválidos, están vacíos, o los datos siguen escritos a mano en el HTML. |

---

### Actividad 2 — Listado que se dibuja desde datos (20%)

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Render desde datos | El contenedor está vacío en el HTML y las tarjetas/filas las genera enteramente el JS recorriendo el array. Agregar un ítem al JSON lo hace aparecer en pantalla sin tocar el HTML. | El render funciona pero queda algún ítem escrito a mano en el HTML conviviendo con los generados. | Los ítems siguen escritos en el HTML — el JS no los genera, o solo modifica textos de elementos que ya existían. |
| Origen de los datos | Los datos vienen de un archivo en `data/` traído con `fetch`, y el código maneja el resultado correctamente. | El `fetch` está pero el array sigue definido también en el `.js` como respaldo, o el JSON se trae y no se usa del todo. | No hay `fetch` — el array está hardcodeado en el `.js`. |
| Uso de funciones y estructuras | Hay una función que arma el HTML de un ítem y un recorrido (`for...of`/`map`) que la aplica a todo el array. El código no se repite. | Funciona pero el armado del HTML está todo inline sin función intermedia, o el recorrido está copiado varias veces. | El código repite el mismo bloque por cada ítem, sin recorrido ni función. |

---

### Actividad 3 — Eventos, validación y acción del usuario (20%)

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Login validado | El formulario impide el envío con `preventDefault()`, valida campos vacíos y formato de email, y muestra el error **en el DOM** junto al campo o arriba del form. | Valida pero el error se muestra con `alert()`, o solo valida una de las dos cosas pedidas. | El login no valida con JS, o el formulario recarga la página. |
| La acción del usuario funciona | Se leen correctamente los valores de todos los tipos de input que usa la pantalla (`value`, checkbox, radio, select), y la acción **actualiza la pantalla sin recargar**: el pedido o la reserva aparece en la lista al confirmarlo. | Funciona pero algún tipo de input se lee mal (ej: checkbox tratado como texto), o hay que refrescar para ver el resultado. | No se leen los valores del formulario, o la acción no produce ningún cambio visible en la pantalla. |
| Coherencia con el flujo del TP | El botón respeta el flujo defendido en E2: **borrador** en Pedidos, **confirmación** en Reservas. La acción hace lo que el CU dice que hace. | El flujo es correcto en general pero algún detalle no coincide con lo modelado en E1. | La acción contradice el flujo del sistema modelado (ej: en Pedidos confirma directo sin borrador). |
| Guardado separado de la UI | El guardado vive en su propia función con nombre propio (`guardarPedido`, `crearReserva`), llamada desde el listener. El grupo puede señalar qué línea va a cambiar cuando llegue el backend. | La función existe pero mezcla guardado con manipulación del DOM adentro. | El guardado está escrito suelto dentro del `addEventListener`, mezclado con la lectura del formulario y el render. |

---

### Actividad 4 — Estados de interfaz (8%)

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Los tres estados | Cargando, vacío y error están implementados y **se pueden provocar en vivo** durante la defensa. | Hay dos de los tres estados, o los tres están en el código pero alguno no se puede provocar. | No hay manejo de estados — si el JSON falla o viene vacío, queda una pantalla en blanco. |
| Calidad del mensaje | Los mensajes explican la situación al usuario en lenguaje claro ("Todavía no hay menús publicados para esta semana"). | Los mensajes existen pero son genéricos ("Sin datos", "Error"). | El error solo aparece en la consola del navegador, no en la pantalla. |

---

### Actividad 5 — Pantalla del rol administrativo (5%)

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Capacidad implementada | La pantalla elegida tiene una capacidad JS completa y funcionando (render desde datos, o formulario con validación y actualización). | La capacidad está implementada a medias — funciona parcialmente o le falta la validación. | La pantalla del rol administrativo quedó estática. |
| Justificación | El README explica qué pantalla se eligió, qué capacidad se le dio y por qué tiene sentido para el CU que materializa. | Se declara la elección pero la justificación es genérica. | No hay justificación, o la pantalla elegida no corresponde al rol administrativo. |

---

### Actividad 6 — Frontend completo (5%)

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| El sistema completo abre y funciona | Están las 5 troncales de E2 **y** las no-troncales del receso, todas linkeadas desde `index.html` y con el mismo estilo. Todas abren y se ven bien: el JS nuevo no rompió nada. | Falta alguna del receso o alguna no está linkeada desde el índice, o alguna tiene un detalle visual roto pero sigue usable. | Faltan varias pantallas del receso, o alguna dejó de funcionar o de verse por el JS agregado. |

---

### Trazabilidad transversal (7%)

Este criterio evalúa la **coherencia** entre el código de E3 y los artefactos de E1 y E2.

**Es el criterio que más discrimina de toda la entrega.** Con la IA en modo asistido, todos los grupos van a tener el render funcionando: eso una herramienta lo escribe en minutos. **Lo que va a variar entre un grupo y otro es si los datos son de su sistema, si el flujo respeta su análisis, y si la tabla existe.** Por eso pesa 7% —igual que en E1— y no 5% como en E2: no es una progresión, responde al riesgo de cada etapa.

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Tabla de capacidades | `README.md` (de esta carpeta) tiene la tabla completa: capacidad ↔ pantalla ↔ archivo JS ↔ CU ↔ qué hace. Los CU son los de E1, con los IDs del grupo. | La tabla está pero le falta alguna columna, o algún CU referenciado es ambiguo. | No hay tabla, o los CU referenciados no existen en E1. |
| Datos fieles al modelo | Los nombres de campo de los arrays y JSON coinciden con el modelo de datos entregado, en camelCase y con `id` en cada objeto. | La mayoría coincide pero hay algún campo renombrado o alguna entidad sin `id`. | Los nombres son inventados: el frontend no va a encajar con el backend sin reescribirse. |
| Coherencia con el flujo de E2 | El comportamiento agregado respeta lo que la pantalla ya prometía en la maqueta: los mismos actores, el mismo flujo, los mismos datos de ejemplo. | Hay coherencia general pero algún dato de ejemplo o algún rol no coincide con lo defendido en E2. | El JS contradice la maqueta: otra historia, otros datos, u otro actor operando la pantalla. |

---

## Defensa oral individual (30%)

Presencial, el **03/09/2026**. Cada integrante se evalúa **por separado**.

El peso sube respecto de E1 (20%) y E2 (25%) por dos razones: el código JavaScript es lo **más fácil de generar con IA** de todo lo entregado hasta ahora, y la política del bloque pasó a **asistido**. La defensa es la salvaguarda que verifica comprensión real.

| Criterio | Excelente (10) | Bueno (7) | Insuficiente (4) |
|----------|----------------|-----------|-------------------|
| Explica el código propio | Puede recorrer cualquier archivo `.js` del grupo y explicar qué hace cada bloque, incluido código que no escribió personalmente. | Explica bien lo que escribió pero se pierde en las partes de sus compañeros. | No puede explicar el código, o lo describe en términos vagos sin poder señalar líneas concretas. |
| Entiende el modelo datos→DOM | Puede explicar de dónde salen los datos, dónde se transforman y dónde se pintan. Sabe qué archivo tocar para agregar un campo al listado. | Entiende la idea general pero duda sobre dónde intervenir para un cambio concreto. | No distingue entre el dato y su presentación — cree que el JSON "es" la pantalla. |
| Demuestra en vivo | Provoca los estados vacío y error cuando se le pide, y muestra el flujo completo sin titubear. | Logra demostrar con alguna ayuda o después de buscar un rato. | No puede demostrar el funcionamiento de lo entregado. |
| Honestidad sobre la IA | Declara con precisión qué se consultó con IA y puede explicar igual el código resultante. | Declara el uso pero la explicación del código asistido es más floja que la del resto. | Hay código que no puede explicar y que no fue declarado. |

**No alcanza con haber escrito una parte.** Cada integrante debe poder explicar las decisiones del grupo completo.

---

## Tabla resumen de pesos

| # | Actividad | Peso |
|---|-----------|------|
| 1 | Organización del código y datos | 5% |
| 2 | Listado que se dibuja desde datos | 20% |
| 3 | Eventos, validación y acción del usuario | 20% |
| 4 | Estados de interfaz | 8% |
| 5 | Pantalla del rol administrativo | 5% |
| 6 | Frontend completo | 5% |
| T | Trazabilidad transversal | 7% |
| | *Subtotal documento* | *70%* |
| D | Defensa oral individual | 30% |
| | **Total** | **100%** |

**Por qué este reparto — el criterio es cuánto discrimina cada actividad con la IA habilitada:**

- **Las capacidades 2 y 3 se llevan 40 puntos entre las dos.** Son el corazón de la entrega: el render y la validación son **lo que hay que aprender a hacer**, con o sin ayuda.
- **La trazabilidad vale 7%, igual que en E1** (en E2 valía 5%). No es una progresión: **responde al riesgo de cada etapa**. Con IA asistida, todos van a tener el render andando — lo que distingue a un grupo es si los datos son de **su** sistema. Es el criterio que más discrimina y el principal indicio documental de que el trabajo es propio.
- **La actividad 1 vale 5%** porque es **la más delegable de todas**: dónde va cada archivo lo resuelve cualquier herramienta, y la consistencia de nombres ya la garantiza el contrato de datos.
- **La actividad 4 vale 8%** — los tres estados son importantes, pero son tres `if`: no es donde está el aprendizaje.
- **La actividad 5 vale 5%** porque es **la misma capacidad aplicada a otra pantalla** — repetir algo ya aprendido.
- **La actividad 6 vale 5%** porque la completitud del frontend es un requisito de **presencia**, no de dificultad: esas pantallas ya estaban hechas desde el receso.

> **El peso fuerte contra el uso acrítico de IA no está en la tabla, está en la defensa**: 30% con **piso de nota** (ver la condición más abajo). Subir más la trazabilidad convertiría la entrega en un ejercicio de documentación, e incentivaría llenar la tabla sin entender — el mismo problema con otra cara.

**Fórmula**: NF = 0,70 × NG + 0,30 × Defensa
*(En E1 fue 80/20, en E2 75/25.)*

---

## ⚠️ Condición de la defensa — piso de nota

**Si la defensa oral de un integrante es insuficiente (menor a 4), su nota final no puede superar 5**, cualquiera sea la nota del documento.

### Por qué existe esta condición

En esta entrega la política de IA es **asistida**, y hay que decirlo sin vueltas: **la mayor parte del código que se pide se puede generar con IA en minutos**. El render, el `fetch`, la validación del formulario, los estados — una herramienta los escribe bien y rápido.

Sin esta condición, la aritmética permitiría esto:

```
Documento 9 · Defensa 4  →  NF = 0,70 × 9 + 0,30 × 4 = 7,5
```

Un integrante que no puede explicar nada de lo entregado aprobaría con 7,5. **Eso vaciaría de sentido la entrega**: no estaríamos evaluando si aprendió a programar, sino si el grupo supo pedirle el código a una herramienta.

La condición no castiga usar IA — **usarla está permitido y se declara**. Lo que hace es afirmar algo simple: **el que entrega tiene que poder explicar lo que entrega.**

> **No se confunde con el código de honestidad académica.** Ese se aplica cuando hay código **no declarado** que el integrante no puede explicar. Esta condición aplica **aunque el uso de IA esté correctamente declarado**: podés haber usado IA, haberlo declarado, y aun así tenés que entender lo que entregaste.

---

## Notas importantes

- La nota de las actividades 1 a 6 es **grupal**. La de defensa oral es **individual**. Dos integrantes del mismo grupo pueden tener notas finales distintas.
- **La defensa tiene piso** (ver la condición arriba): con defensa menor a 4, la nota final no supera 5.
- **Se evalúa servido, no abierto como archivo.** `fetch` no funciona sobre `file://`. Si la entrega solo funciona abriendo el HTML con doble clic, las actividades 2 y 4 se evalúan como no implementadas. Verificar con Live Server antes de entregar.
- **Si una pantalla no abre o la consola tira errores que rompen el flujo**, la actividad correspondiente se evalúa con la nota mínima.
- **No se pide persistencia.** Los datos viven en memoria y al refrescar se vuelve al estado inicial del JSON. Eso es lo esperado — no se penaliza, y tampoco suma implementar `localStorage`.
- **No se pide JavaScript en todas las pantallas —** *en esta entrega*. Las que quedan estáticas no bajan la nota de E3, siempre que estén presentes y linkeadas (Actividad 6). **Esto es un recorte de etapa, no el alcance final**: en la Exposición Final (19/11) se defiende el sistema terminado y ahí **todas las pantallas, troncales y no troncales, tienen que tener su JS funcionando y conectado al backend**. La fecha límite real es el **05/11** (conexión FE-BE): una pantalla sin JavaScript no se puede conectar a nada. Ver la sección "Horizonte" de la consigna — hay que decirlo en clase, no solo dejarlo escrito.
- **Política IA: asistido.** Consultar errores, pedir explicaciones y debuggear está permitido y se declara. Generar funcionalidad completa con un prompt y pegarla, no. Si la defensa muestra código que el integrante no puede explicar y que no fue declarado, se aplica el código de honestidad académica.
- Las entregas fuera de la fecha límite se evalúan con estos criterios pero con penalización según el reglamento de la materia.
