# PP1 2026 — Proyecto Integrador

**Grupo**: [Nombre del grupo]  
**Proyecto**: [Nombre del proyecto elegido]  
**Integrantes**:
- [Nombre y Apellido 1]
- [Nombre y Apellido 2]
- [Nombre y Apellido 3]
- [Nombre y Apellido 4]

---

## Estructura del repositorio

```
├── docs/                        → Documentación de entregas (consignas, rúbricas, diseño)
│   ├── 1er-entrega/             → Análisis del sistema (Bloque 1, entrega 30/04)
│   │   ├── consigna.md
│   │   ├── analisis.md          → Plantilla a completar por el grupo
│   │   ├── rubrica.md
│   │   └── guia-trabajo.png
│   ├── 2da-entrega/             → Diseño de interfaces (Bloque 2, entrega 25/06)
│   │   ├── consigna.md
│   │   ├── rubrica.md
│   │   ├── README.md            → Inventario de pantallas + trazabilidad
│   │   └── wireframes/          → PNGs de Excalidraw (uno por pantalla)
│   ├── 3er-entrega/             → Frontend codificado (Bloque 3, entrega 03/09)
│   └── 4ta-entrega/             → Backend funcional (Bloque 4, entrega 15/10)
├── frontend/                    → Código del sitio (HTML + CSS + JS desde Bloque 2)
└── backend/                     → Código del backend (Spring Boot + JPA + MySQL desde Bloque 4)
```

**Convención**: `docs/` lleva los artefactos de **diseño y documentación** (markdown, PNGs). `frontend/` lleva el **código del sitio web** (HTML, CSS, JavaScript). `backend/` lleva el **código del servidor** (Java + Spring Boot). Los wireframes son artefactos de diseño → viven en `docs/2da-entrega/wireframes/`. Los HTMLs son código → viven en raíz de `frontend/`.

## Cómo usar este template

> **"Use this template" no es un fork.** Crea un repo nuevo con esta estructura pero sin historial de commits. Tu repo arranca limpio.

> **Un solo integrante del grupo** realiza los pasos 1 a 5. Los demás integrantes clonan el repo después (paso 2) una vez que los datos del grupo ya estén subidos. Esto evita conflictos.

### Paso 1 — Crear tu repo a partir del template

1. Entrá a [PP1-2026-proyecto-template](https://github.com/rjruiz-dev/PP1-2026-proyecto-template)
2. Hacé click en el botón verde **"Use this template"** → **"Create a new repository"**
3. Completá:
   - **Owner**: tu cuenta personal de GitHub
   - **Repository name**: `PP1-2026-grupoX` (reemplazá X por tu número de grupo, ejemplo: `PP1-2026-grupo1`)
   - **Visibilidad**: **Public**
4. Click en **"Create repository"**

### Paso 2 — Clonar e inicializar

```bash
git clone https://github.com/TU-USUARIO/PP1-2026-grupoX.git
cd PP1-2026-grupoX
```

### Paso 3 — Completar datos del grupo

Editá este `README.md`: reemplazá los campos entre corchetes `[...]` de arriba con los datos reales de tu grupo (nombre, proyecto elegido, integrantes).

### Paso 4 — Agregar collaborators

En GitHub: **Settings** → **Collaborators** → **Add people**:
- Agregar a **cada integrante** del grupo por su usuario de GitHub
- Agregar al **docente**: `rjruiz-dev` (con rol **Write** — necesario para subir rúbricas, consignas y revisar avances)

### Paso 5 — Primer commit

```bash
git add .
git commit -m "docs: completar datos del grupo"
git push
```

## Entregas

| Entrega | Ubicación | Fecha límite |
|---------|-----------|-------------|
| Entrega 1 — Análisis del sistema | [`docs/1er-entrega/`](docs/1er-entrega/) | 30/04/2026 |
| Entrega 2 — Diseño de interfaces | [`docs/2da-entrega/`](docs/2da-entrega/) (consigna, rúbrica, wireframes) + [`frontend/`](frontend/) (HTMLs + CSS) | 25/06/2026 |
| Entrega 3 — Frontend codificado | [`frontend/`](frontend/) (con JavaScript) + [`docs/3er-entrega/`](docs/3er-entrega/) | 03/09/2026 |
| Entrega 4 — Backend funcional | [`backend/`](backend/) + [`docs/4ta-entrega/`](docs/4ta-entrega/) | 15/10/2026 |

Cada entrega se sube a **Moodle** como link al repositorio.

## Convenciones

### Commits

Usar [Conventional Commits](https://www.conventionalcommits.org/):

| Prefijo | Uso |
|---------|-----|
| `docs:` | Documentación y entregas |
| `feat:` | Nueva funcionalidad |
| `fix:` | Corrección de errores |
| `style:` | Cambios de estilo / CSS |
| `refactor:` | Refactorización sin cambio de funcionalidad |

### Ramas

La estrategia de ramas evoluciona con las entregas:

| Entregas | Estrategia | ¿Por qué? |
|----------|-----------|-----------|
| 1 y 2 (análisis + diseño) | Trabajar directo en `main` | Documentación + HTML/CSS estático, bajo riesgo de romper |
| 3 y 4 (código JS y backend) | Crear ramas `feature/nombre-descriptivo` y mergear a `main` | El código con lógica requiere revisión antes de integrar |

- `main` es siempre la versión estable y entregable del proyecto
