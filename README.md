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

1. Ir al repo template: [PP1-2026-proyecto-template](https://github.com/rjruiz-dev/PP1-2026-proyecto-template)
2. Click en **"Use this template"** → **"Create a new repository"**
3. Configurar:
   - **Owner**: tu cuenta personal de GitHub
   - **Nombre del repo**: seguir la convención `PP1-2026-grupoX` (ejemplo: `PP1-2026-grupo1`)
   - **Visibilidad**: Public
4. Click en **"Create repository"**
5. Clonar el repo en tu máquina:
   ```bash
   git clone https://github.com/TU-USUARIO/PP1-2026-grupoX.git
   ```
6. Completar los datos del grupo en este README
7. Agregar a todos los integrantes como **collaborators**: Settings → Collaborators → Add people
8. Primer commit:
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

- `main` — rama principal, siempre funcional
- Crear ramas para features: `feature/nombre-descriptivo`
