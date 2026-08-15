# frontend/

El código del sitio. **Evoluciona en capas: no se reescribe.**

```
frontend/
├── index.html            → landing con links a todas las pantallas
├── login.html            → una pantalla = un archivo, en la raíz
├── ...
├── assets/
│   ├── css/              → tu CSS propio           (Bloque 2)
│   ├── img/              → logos e ilustraciones   (Bloque 2)
│   └── js/               → tu JavaScript           (Bloque 3)
└── data/                 → los JSON mock           (Bloque 3)
```

| Cuándo | Qué se agrega |
|--------|---------------|
| Bloque 2 | Los HTML en la raíz, `assets/css/` y `assets/img/` |
| Bloque 3 | `assets/js/` y `data/` |
| Bloque 5 | Nada nuevo: los `fetch` a `data/` pasan a apuntar al backend |

**Los HTML van en la raíz de `frontend/`**, como en cualquier sitio estático. Los wireframes son artefactos de diseño y viven en `docs/2da-entrega/wireframes/`.
