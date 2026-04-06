# WOW Almería 2026

## Proyecto
Sitio web estático para el evento **WOW — Woman of Wisdom** (Almería, 2026).
Evento cristiano evangélico dirigido a mujeres.

## Stack
- HTML5 + CSS3 + JavaScript vanilla
- Sin frameworks ni bundlers — sitio estático puro
- Google Fonts: Playfair Display (títulos) + Inter (cuerpo)

## Estructura
```
/
├── CLAUDE.md
├── README.md
├── .claude/
│   └── skills/
│       └── upload-site/    # Skill /upload-site con datos FTP
└── html/                   # Todo el sitio va aquí dentro
    ├── index.html          # Página principal (single-page)
    ├── css/
    │   └── styles.css      # Estilos globales
    ├── js/
    │   └── main.js         # Interactividad (menú, scroll, etc.)
    └── assets/
        └── images/         # Imágenes y recursos gráficos
```

## Comandos
- `/upload-site` — Sube `html/` al servidor FTP de producción (credenciales en `.claude/skills/upload-site/SKILL.md`)

## Servidor local
```bash
cd html && python3 -m http.server 80
```
Abre http://localhost para previsualizar.

## Despliegue
- El contenido de `html/` se sube tal cual al directorio remoto `/wow/`
- Siempre subir tras cambios con `/upload-site`

## Convenciones
- Idioma del contenido: **español**
- Diseño responsive (mobile-first)
- Paleta: dorado `#c9a84c`, púrpura `#5b2a6e`, blanco `#faf7f2`
- Secciones: Hero, Acerca de, Programa, Oradoras, Ubicación, Registro, Footer
- Accesibilidad: semántica HTML5, alt en imágenes, contraste adecuado
- Las imágenes van en `html/assets/images/`
- No usar frameworks JS/CSS — todo vanilla
