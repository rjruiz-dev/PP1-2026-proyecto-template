# Entrega 3 — Frontend Codificado

**Grupo**: [Nombre del grupo]
**Proyecto**: [Nombre del proyecto elegido]
**Fecha de entrega**: 03/09/2026

---

## 1. Tabla de capacidades

Dónde vive cada capacidad JavaScript y qué caso de uso materializa. Los CU son los de tu Entrega 1, con los IDs que les puso tu grupo.

| Capacidad | Pantalla | Archivo JS | CU(s) | Qué hace |
|-----------|----------|------------|-------|----------|
| 1 · Login validado | | | | |
| 2 · Listado desde datos | | | | |
| 3 · Acción del usuario | | | | |
| 4 · Estados de interfaz | | | | |
| 5 · Rol administrativo | | | | |

> Las capacidades 1 a 4 son fijas. La 5 la elige el grupo entre las pantallas del rol administrativo, y se justifica abajo.

## 2. Archivos de datos

Los JSON que alimentan las pantallas. **Un archivo por entidad** — cada uno equivale a un futuro endpoint del backend.

| Archivo | Entidad del modelo de datos | Cuántos ítems | Qué pantalla lo consume |
|---------|------------------------------|---------------|--------------------------|
| `data/` | | | |
| `data/` | | | |

> Los nombres de campo salen del **modelo de datos** entregado por la cátedra, en camelCase y con `id` en cada objeto. No se inventan.

## 3. Decisiones del grupo

**Organización de los archivos JS**: ¿un `.js` por pantalla o uno compartido? ¿Por qué?

> [Completar]

**Pantalla del rol administrativo elegida**: ¿cuál, qué capacidad se le dio y por qué tiene sentido para el CU que materializa?

> [Completar]

**Otras decisiones**: cualquier cosa resuelta distinto de lo pedido, con su justificación.

> [Completar]

## 4. Uso de IA

**Política del bloque: asistido.** Está permitido consultar errores de consola, pedir explicaciones y debuggear código propio. No está permitido generar una funcionalidad completa por prompt y pegarla.

**Declararlo no baja la nota. No declararlo y que la defensa lo evidencie, sí.**

| En qué se usó | Para qué | Herramienta |
|---------------|----------|-------------|
| | | |

> Recordá que la defensa individual tiene **piso**: si da menos de 4, la nota final no supera 5, por más que el trabajo del grupo esté impecable. Si hay algo de tu repo que no entendés, preguntá **antes** del 03/09.

## 5. Checklist antes de entregar

- [ ] Las capacidades funcionan **servidas con Live Server**
- [ ] La consola no tira errores al cargar ninguna pantalla
- [ ] Agregar un ítem al JSON lo hace aparecer sin tocar el HTML
- [ ] El estado vacío y el de error se pueden **provocar en vivo**
- [ ] El guardado vive en su **propia función**, no suelto en el listener
- [ ] Los nombres de campo coinciden con el modelo de datos
- [ ] Están todas las pantallas del sistema, incluidas las del receso
- [ ] Las tablas de arriba están completas
- [ ] Cada integrante puede explicar **cualquier parte** del código

> La consigna completa está en [`consigna.md`](./consigna.md) y los criterios de evaluación en [`rubrica.md`](./rubrica.md).
