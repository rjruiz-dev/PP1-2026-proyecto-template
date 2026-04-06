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
├── docs/        → Entregas y documentación del proyecto
├── frontend/    → Código del frontend (HTML, CSS, JS)
└── backend/     → Código del backend (Spring Boot)
```

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

### Paso 4 — Agregar a los integrantes como collaborators

En GitHub: **Settings** → **Collaborators** → **Add people** → agregar a cada integrante por su usuario de GitHub.

### Paso 5 — Primer commit

```bash
git add .
git commit -m "docs: completar datos del grupo"
git push
```

## Entregas

Todas las entregas de documentación se encuentran en la carpeta `docs/`.

| Entrega | Archivo | Fecha límite |
|---------|---------|-------------|
| Entrega 1 — Análisis del sistema | [`docs/entrega-1-analisis.md`](docs/entrega-1-analisis.md) | 30/04/2026 |
| Entrega 2 — Diseño de interfaces | `docs/entrega-2-diseno.md` | 25/06/2026 |
| Entrega 3 — Frontend codificado | Carpeta `frontend/` | 03/09/2026 |
| Entrega 4 — Backend funcional | Carpeta `backend/` | 15/10/2026 |

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
| 1 y 2 (documentación) | Trabajar directo en `main` | Son archivos `.md`, no hay riesgo de romper nada |
| 3 y 4 (código) | Crear ramas `feature/nombre-descriptivo` y mergear a `main` | El código requiere revisión antes de integrar |

- `main` es siempre la versión estable y entregable del proyecto

## Herramientas recomendadas

### Editor

Usar **Visual Studio Code** (VSCode) para editar los archivos `.md` del proyecto.

Extensiones sugeridas (instalar desde el panel de extensiones de VSCode):

| Extensión | Para qué sirve |
|-----------|---------------|
| **Markdown Preview Enhanced** | Vista previa en tiempo real: ven las tablas y el formato renderizado al lado del código |
| **Markdown Table** | Formatea tablas automáticamente con Tab y las mantiene alineadas |

**Cómo usarlas**: abrir el archivo `.md` en VSCode → `Ctrl + Shift + V` para abrir la vista previa → editar a la izquierda, ver el resultado a la derecha.

## Trabajo en equipo — Entrega 1

La Entrega 1 es un único archivo (`docs/entrega-1-analisis.md`). Para evitar conflictos de Git cuando trabajan en equipo, sigan esta organización:

### Paso 1 — Reunión inicial (todos juntos)

Antes de escribir nada, el grupo se reúne y define en conjunto:
- Los **actores** del sistema
- Los **flujos principales** (qué hace el sistema, para quién)
- Boceto de las **historias de usuario** principales

Esta discusión es grupal porque todos necesitan entender el dominio completo. Puede ser presencial o por llamada.

### Paso 2 — Dividir las actividades

Cada integrante se encarga de una o más secciones. Ejemplo para un grupo de 4:

| Integrante | Sección asignada |
|-----------|-----------------|
| Integrante 1 | Actores + Historias de Usuario |
| Integrante 2 | Requisitos Funcionales + Requisitos No Funcionales |
| Integrante 3 | Diagrama de Casos de Uso |
| Integrante 4 | Especificaciones de Casos de Uso |

> Esta división es una sugerencia. Lo importante es que **cada persona sea responsable de una parte concreta** y que **todos participen**.

### Paso 3 — Editar sin conflictos

Como todos editan el mismo archivo, sigan esta regla simple:

```
SIEMPRE antes de editar:    git pull
SIEMPRE después de editar:  git add, commit, push
```

**No editen al mismo tiempo.** Coordinen por grupo de WhatsApp o similar: "voy a editar la sección de RF" → edita → pushea → "listo, ya pueden editar".

### Paso 4 — Revisión cruzada

Antes de entregar, cada integrante revisa la sección de **otro** compañero (no la propia). Verificar:
- ¿Los RF referencian HU que existen? (trazabilidad RF → HU)
- ¿Los casos de uso coinciden con el diagrama?
- ¿Las historias de usuario cubren a todos los actores?
