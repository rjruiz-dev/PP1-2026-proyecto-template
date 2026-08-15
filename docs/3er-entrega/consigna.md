# Consigna — Entrega 3: Frontend Codificado

**Materia**: Práctica Profesionalizante I (PP1) — 2026
**Fecha límite**: 03/09/2026
**Formato de entrega**: completar la estructura del repositorio y subir el link del repo a Moodle.
**Defensa oral individual**: presencial, el 03/09/2026.

| Carpeta | Contenido |
|---------|-----------|
| `README.md` (de esta carpeta) | Tabla de capacidades JS + trazabilidad pantalla ↔ CU ↔ qué hace el JS |
| `../../frontend/assets/js/` | El código JavaScript del grupo |
| `../../frontend/data/` | Los archivos JSON con los datos mock |
| `frontend/*.html` | Las pantallas de E2 + las del receso, ya existentes |

> **El frontend evoluciona en capas, no se reescribe.** No se crean pantallas nuevas para esta entrega ni se rehace el HTML/CSS de E2. Se le agrega comportamiento al frontend que ya existe.

---

## Objetivo

Darle **comportamiento** al frontend maquetado en la Entrega 2. Hasta ahora las pantallas son estáticas: los datos están escritos a mano en el HTML y los botones no hacen nada. En esta entrega los datos pasan a vivir en archivos JSON, las pantallas se dibujan solas a partir de esos datos, los formularios validan, y la interfaz responde a lo que hace el usuario.

El objetivo NO es escribir mucho JavaScript, sino **demostrar que se entiende el modelo**: datos por un lado, presentación por el otro, y código que los conecta.

---

## Alcance — 4 capacidades obligatorias

No se pide JavaScript en las 9-10 pantallas del sistema. Se piden **4 capacidades**, y el resto de las pantallas queda estático **por ahora** (leé "Horizonte" más abajo — *por ahora* no significa *nunca*).

> **Ojo**: son 4 **capacidades**, no necesariamente 4 archivos. Según el TP, dos capacidades pueden caer en la misma pantalla.

### Capacidad 1 — Login validado

**Dónde**: la pantalla de Login (pantalla 01, los dos TP).

El formulario valida con JavaScript **antes** de dejar continuar, y muestra el error **en el DOM** — no con `alert()`.

- Se impide el envío del formulario con `preventDefault()`
- Se valida al menos: campos vacíos y formato de email
- El mensaje de error aparece en la pantalla, junto al campo o arriba del formulario
- Si los datos son válidos, se redirige a la pantalla principal del sistema

### Capacidad 2 — Listado que se dibuja desde datos

**Dónde**:
- **Pedidos** → el menú del día (pantalla 03)
- **Reservas** → el catálogo de alojamientos (pantalla 02)

Los ítems del listado **no están escritos en el HTML**. Están en un archivo JSON dentro de `../../frontend/data/`, se traen con `fetch` y se dibujan desde JavaScript.

- El HTML tiene el contenedor vacío; las tarjetas/filas las genera el JS
- Los datos salen de `frontend/data/*.json`
- Se manejan los **tres estados** (ver Capacidad 4)

### Capacidad 3 — Acción del usuario sobre los datos

**Dónde**:
- **Pedidos** → registrar el pedido (pantalla 03) y verlo reflejado en Mis pedidos (pantalla 04)
- **Reservas** → realizar la reserva (pantalla 03) y verla reflejada en Mis reservas (pantalla 04)

El usuario completa el formulario, y la pantalla **se actualiza sin recargar**.

- Se leen los valores de los inputs (`value`, checkbox, radio, select)
- Se valida antes de aceptar la acción
- El resultado se agrega a la lista en pantalla
- El botón respeta el flujo del TP: en **Pedidos** el pedido se guarda como **borrador**, en **Reservas** la reserva se **confirma** (lo mismo que se defendió en E2)

#### El guardado va en su propia función *(obligatorio)*

La acción de guardar **no se escribe suelta dentro del `addEventListener`**. Va en una función aparte, con nombre propio:

```js
// ❌ el guardado mezclado con el manejo del evento
form.addEventListener('submit', (e) => {
  e.preventDefault();
  pedidos.push(nuevoPedido);
  renderPedidos();
});

// ✅ el guardado tiene su lugar
async function guardarPedido(pedido) {
  pedidos.push(pedido);   // hoy: en memoria
}

form.addEventListener('submit', async (e) => {
  e.preventDefault();
  await guardarPedido(nuevoPedido);
  renderPedidos();
});
```

**Por qué se pide esto**: en el Bloque 5 el frontend se conecta al backend real. Cuando llegue ese momento, lo único que cambia es **el cuerpo de esa función** — pasa de escribir en un array a hacer un `fetch` con `POST`. La pantalla, el formulario y el render no se tocan.

Es la misma idea que van a ver del otro lado en Spring Boot: **el lugar donde se guarda está separado de la interfaz**.

> **Los datos viven en memoria.** Al refrescar la página se vuelve al estado inicial del JSON. **Es lo esperado** — la persistencia real llega con el backend. No se pide `localStorage`: no se parece a cómo persiste un backend y sería código para tirar.

> **¿Y no es al pedo el JSON, si después lo reemplaza el backend?** No. **El JSON se tira; el código que lo consume, no.** El día de la conexión, `fetch('data/platos.json')` pasa a `fetch('/api/platos')` — **una línea**. El render, la función de la tarjeta y los estados quedan intactos. El JSON es un andamio: se saca cuando la pared está parada, pero sin él no se puede construir.

### Capacidad 4 — Estados de interfaz

**Dónde**: en la pantalla de la Capacidad 2, como mínimo.

Una lista que se alimenta de datos externos puede estar en tres situaciones, y las tres se ven en pantalla:

| Estado | Cuándo | Qué se muestra |
|--------|--------|----------------|
| **Cargando** | mientras se espera el `fetch` | un mensaje o indicador temporal |
| **Vacío** | el JSON vino bien pero sin ítems | un mensaje que explique la situación, no una pantalla en blanco |
| **Error** | el `fetch` falló | un mensaje de error legible, no la consola |

Tiene que poder **demostrarse en la defensa**: se pide provocar el estado vacío y el de error en vivo (por ejemplo, vaciando el JSON o rompiendo la ruta).

### Capacidad 5 — Una pantalla del rol administrativo *(a elección)*

**Dónde**: una pantalla del **Administrador** (Pedidos) o del **Anfitrión** (Reservas), elegida por el grupo y justificada contra su CU de E1.

Candidatas según el TP:
- **Pedidos** → generar consolidado, administrar/publicar menús, calendario de feriados
- **Reservas** → publicar alojamiento, mis propiedades, calendario de disponibilidad, reservas recibidas

Alcanza con que tenga **una** de las capacidades anteriores (render desde datos, o formulario con validación y actualización de la pantalla). El grupo elige cuál tiene más sentido para esa pantalla y lo justifica.

> Son 4 capacidades obligatorias: 1, 2, 3 y 4 son fijas; la 5 es la aplicación de una de ellas a la otra mitad del sistema.

---

## Requisitos del frontend completo

Además de las capacidades JS, el repo tiene que tener el **sistema completo maquetado**:

- Las **5 pantallas troncales** de E2
- Las **pantallas no-troncales** de la tarea de receso (Administrador/Anfitrión, Registro, Mi perfil)
- El `index.html` con los links a todas
- El mismo estilo y navbar en todas

Las pantallas del receso que no reciban JavaScript se entregan **estáticas** — pero tienen que estar.

---

## ⚠️ Horizonte: esto es un recorte de ETAPA, no el alcance final del proyecto

Leé esto con atención, porque define trabajo que arranca ahora y no termina el 03/09.

**En esta entrega (03/09)** se piden 4 capacidades. Las demás pantallas pueden quedar estáticas y **eso no baja la nota de E3**.

**En la Exposición Final (19/11) NO.** Ahí se defiende el **sistema terminado**: para ese momento **TODAS las pantallas —troncales y no troncales— tienen que tener su JavaScript funcionando** y conectado al backend. No se defiende un sistema mitad aplicación y mitad maqueta.

### Por qué el recorte de E3 existe

El Bloque 3 tiene 4 clases. En 8 horas se aprende a hacer bien **cuatro cosas**, no diez. El recorte es para que aprendan el mecanismo con profundidad, no para que la mitad del sistema quede sin terminar.

### Cuándo se completa el resto

**Trabajo progresivo, en paralelo al Bloque 4.** No hay clases dedicadas a esto: una vez que sepan hacer las 4 capacidades, aplicarlas al resto de las pantallas es **repetir un mecanismo que ya conocen**, no aprender algo nuevo. Es exactamente el mismo `crearTarjeta` + render, el mismo formulario validado, con otros datos.

**La fecha límite real es el 05/11, no el 19/11.** Y no es una fecha arbitraria: el 05/11 se conecta el frontend al backend. **Una pantalla sin JavaScript no se puede conectar a nada** — no tiene dónde recibir los datos. Si llegan a esa clase con pantallas estáticas, no las van a poder integrar, y eso sí se ve en la Exposición Final.

| Momento | Qué tiene que tener JS |
|---------|------------------------|
| **03/09 — Entrega 3** | Las 4 capacidades. El resto puede quedar estático |
| Sep–Oct (durante el Bloque 4) | Se va completando el resto, de a poco, en paralelo al backend |
| **05/11 — Conexión FE-BE** | **Todas.** Lo que no tenga JS no se puede conectar |
| **19/11 — Exposición Final** | Todas, funcionando y conectadas al backend |

> **En una frase**: el 03/09 se evalúa que **sepan hacerlo**. El 19/11 se evalúa que **esté hecho**.

---

## Actividades

### 1. Organizar el código

```
frontend/
├── assets/
│   ├── css/          ← de E2
│   ├── img/          ← de E2
│   └── js/           ← nuevo
├── data/             ← nuevo
├── index.html
└── *.html
```

**Reglas**:
- El JavaScript va en archivos `.js` dentro de `../../frontend/assets/js/`. **No** en `<script>` embebido en el HTML
- El `<script src="...">` va al final del `<body>`, no en el `<head>`
- Cada grupo decide si usa un `.js` por pantalla o uno compartido. Lo que se evalúa es que se entienda la organización elegida y que sea consistente

### 2. Modelar los datos en JSON

#### Cuántos archivos: uno. Dos como mucho

**No hace falta un JSON por pantalla.** Es la confusión más común y hace perder horas al pedo.

| Capacidad | ¿Necesita archivo JSON? |
|---|---|
| 1 · Login validado | **No.** Valida formato, no consulta datos |
| 2 · Listado que se dibuja solo | **Sí — obligatorio.** Uno: `platos.json` / `alojamientos.json` |
| 3 · Acción del usuario | **No.** Escribe, no lee: lo que se crea nace en memoria |
| 4 · Los tres estados | **No.** Se demuestran sobre el archivo de la capacidad 2 |
| 5 · Pantalla del rol administrativo | **Solo si necesita datos propios** distintos de los de arriba |

**Un archivo por entidad, no uno gigante con todo.** Cada archivo JSON equivale a un futuro endpoint del backend: `data/platos.json` va a ser `/api/platos`. Si metés todo en un solo archivo, ese paralelo se rompe.

#### Contenido

Datos de ejemplo **coherentes con la historia que ya cuentan las pantallas de E2** (el mismo menú, el mismo usuario, los mismos alojamientos).

- Mínimo **4 ítems** por listado, para que se note el render
- JSON válido — se verifica que abra sin errores
- Los nombres de campo en inglés o español, pero **consistentes** en todo el proyecto

### 3. Implementar las capacidades

Las 4 capacidades descritas arriba. Cada una tiene que **funcionar en el navegador** — no alcanza con que el código exista.

> **Gotcha operativo**: `fetch` no funciona abriendo el HTML con doble clic (`file://`). Hay que usar **Live Server** de VS Code o equivalente. Verificar la entrega servida, no abierta como archivo.

### 4. Documentar en `README.md` (de esta carpeta)

Una tabla que declare qué hace el JavaScript y dónde:

| Capacidad | Pantalla | Archivo JS | CU de E1 | Qué hace |
|-----------|----------|-----------|----------|----------|
| Login validado | `login.html` | `assets/js/login.js` | CU-XX | Valida email y campos vacíos, muestra el error en el DOM |
| Listado desde datos | ... | ... | ... | ... |

Más una sección breve de **decisiones del grupo**: por qué organizaron los `.js` así, qué pantalla eligieron para la Capacidad 5 y por qué, y cualquier cosa que hayan resuelto distinto de lo pedido (con su justificación).

### 5. Declarar el uso de IA

Una sección en el mismo README: **qué se consultó con IA y para qué**. Ver política abajo.

---

## Política IA del bloque

**Modo: ASISTIDO.** Es más permisivo que en E2, pero tiene límites y se declara.

**Permitido**:
- Consultar errores y mensajes de la consola ("qué significa este `TypeError`")
- Pedir explicación de un método o de sintaxis que no se entiende
- Pedir ayuda para **debuggear** código propio que no funciona

**No permitido**:
- Generar una funcionalidad completa con un prompt y pegarla
- Entregar código que el grupo no pueda explicar línea por línea

**Se declara**: el README lleva la sección de uso de IA. Declararlo no baja la nota; **no declararlo y que la defensa lo evidencie, sí**.

> El código tiene que poder explicarse. La defensa oral pregunta por líneas concretas del JS entregado: por qué ahí un `const` y no un `let`, qué devuelve esa función, qué pasa si el array viene vacío. Si un integrante no puede explicar el código de su grupo, la defensa lo refleja.

---

## Defensa oral

Individual y presencial, el **03/09/2026**. Peso: **30%** de la nota final (en E1 fue 20%, en E2 25%).

Sube el peso porque el código JavaScript es lo **más fácil de generar con IA** de todo lo entregado hasta ahora, y porque la política del bloque pasó a *asistido*. La defensa es la salvaguarda.

Se pregunta sobre **cualquier parte del código del grupo**, no solo lo que cada uno escribió. Ejemplos del tipo de pregunta:

- Mostrame dónde se dibuja esta lista. ¿De dónde salen estos datos?
- ¿Qué pasa si el JSON viene vacío? Mostralo.
- ¿Por qué el formulario no recarga la página?
- ¿Qué hace `await` en esa línea?
- Si quisiera agregar un campo al listado, ¿qué archivos tocarías?

### ⚠️ La defensa tiene piso

**Si tu defensa es insuficiente (menor a 4), tu nota final no puede superar 5**, por más que el trabajo del grupo esté impecable.

Te explicamos por qué, sin vueltas: **buena parte del código que se pide en esta entrega se puede generar con IA en minutos.** Usarla está permitido y se declara — eso no es el problema. El problema sería aprobar la materia sin poder explicar lo que entregaste.

Sin esta condición, alguien con un trabajo grupal de 9 y una defensa de 4 aprobaría con 7,5 sin entender el código. **La regla es simple: el que entrega tiene que poder explicar lo que entrega.**

Y esto no es una amenaza, es un aviso con un mes de anticipación: **si en algún momento no entendés lo que hay en tu repo, preguntá antes del 03/09.** En clase, por el canal del grupo, o en la consulta. Ese es el momento de resolverlo.

---

## Checklist antes de entregar

- [ ] Las 4 capacidades funcionan **servidas con Live Server**, no abiertas como archivo
- [ ] Los JSON son válidos y tienen al menos 4 ítems por listado
- [ ] Los tres estados (cargando, vacío, error) se pueden provocar y mostrar
- [ ] El JS está en `assets/js/`, no embebido en el HTML
- [ ] Las pantallas del receso están en el repo y linkeadas desde `index.html`
- [ ] Ninguna pantalla quedó rota por el JS nuevo (todas siguen abriendo y viéndose)
- [ ] La consola del navegador no tira errores al cargar
- [ ] `README.md` (de esta carpeta) con la tabla de capacidades y la declaración de IA
- [ ] Todo commiteado y pusheado

---

## Guía de trabajo

![Entrega 3 — Guía de trabajo: qué se pide, dónde está la nota y qué hace perder puntos](./guia-trabajo-entrega-3.png)

> Una hoja con lo esencial: las cinco capacidades, el reparto de la nota, y **los seis errores evitables que más puntos cuestan**. No reemplaza a esta consigna — sirve para revisar antes de entregar.
