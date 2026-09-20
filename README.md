# ROOT_CONSOLE

Interfaz operativa mobile-first para visualizar y coordinar el ecosistema ROOT sin convertirse en fuente de verdad.

## Estado

**V0.1 IMPLEMENTADA**

Incluye:

- HOY;
- estado global;
- siguiente acción;
- PROYECTOS;
- DECISIONES;
- CONSULTA ROOT;
- vista contextual de proyecto;
- navegación móvil;
- datos públicos sanitizados.

## Ejecutar

La entrada es:

`index.html`

Archivos principales:

- `index.html`
- `styles.css`
- `app.js`
- `data/state.json`

## Arquitectura

```text
ROOT_CONSOLE
    ↓ presenta / consulta
ROOT_ECOSISTEMA
    ↓ coordina
PROYECTOS DUEÑOS
```

Cada proyecto conserva su propia fuente de verdad. ROOT_CONSOLE no duplica expedientes, PII ni estados autoritativos.

## Documento canónico

- [Propuesta completa](docs/PROPOSAL_COMPLETE.md)
- [Estado](STATUS.md)
- [Handoff](HANDOFF.md)
- [Privacidad](docs/PRIVACY.md)
- [Roadmap](docs/ROADMAP.md)

## Seguridad

Este repositorio es público.

No incluir:

- PII;
- credenciales;
- secretos;
- VIN;
- RAW;
- rutas privadas;
- IDs sensibles;
- datos operativos privados;
- arquitectura confidencial.

Regla:

```text
PRIVATE → SANITIZED → PUBLIC
```

## Alcance V0.1

La consola permite operar navegación y contexto desde móvil. Las modificaciones reales siguen requiriendo una ejecución autorizada sobre la fuente dueña; un cambio visual local no equivale a una escritura confirmada.
