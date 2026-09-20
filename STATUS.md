# ROOT_CONSOLE — STATUS

## Estado actual

**V0.1_IMPLEMENTADA / MOBILE_FIRST / DATOS_PUBLICOS_SANITIZADOS**

## Fecha de corte

2026-09-20

## Terminado

- propuesta completa consolidada;
- arquitectura y privacidad definidas;
- Home / Hoy implementado;
- Proyectos implementado;
- Decisiones implementado;
- Consulta ROOT implementada;
- vista contextual de proyecto implementada;
- navegación móvil inferior implementada;
- siguiente acción principal implementada;
- estado global implementado;
- estado sanitizado en `data/state.json`;
- acceso público a AFL AUTOS y Portafolio únicamente mediante URLs públicas;
- frontend sin PII, credenciales, RAW, VIN, rutas privadas ni secretos.

## Archivos ejecutables

- `index.html`
- `styles.css`
- `app.js`
- `data/state.json`

## Autoridad

ROOT_CONSOLE sigue siendo una capa de presentación.

```text
ROOT_CONSOLE
→ presenta estado sanitizado
→ no sustituye ROOT_ECOSISTEMA
→ no sustituye la fuente dueña de cada proyecto
```

## Privacidad

El repositorio es público.

Regla vigente:

```text
PRIVATE → SANITIZED → PUBLIC
```

No almacenar aquí datos operativos privados ni convertir `data/state.json` en base maestra.

## Pendiente para V0.2+

- resolver publicación/despliegue si GitHub Pages no está habilitado;
- validación visual final en teléfono real;
- bandeja de decisiones con integración autorizada;
- adaptadores incrementales;
- Auditor;
- Actividad avanzada;
- Fuentes de verdad;
- conectores reales.

## Siguiente acción

Usar V0.1 en campo como consola de navegación y lectura. Las escrituras reales siguen ocurriendo mediante ROOT y el proyecto dueño correspondiente.
