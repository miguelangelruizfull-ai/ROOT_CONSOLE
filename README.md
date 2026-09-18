# ROOT_CONSOLE

Interfaz operativa para visualizar, consultar y coordinar el ecosistema ROOT sin convertirse en fuente de verdad de los proyectos.

## Propósito

ROOT_CONSOLE presenta una vista sanitizada del estado del ecosistema: proyectos, decisiones, siguiente acción, auditoría, actividad y fuentes de verdad.

## Principio de arquitectura

```text
ROOT_CONSOLE
    ↓ consulta / presenta
ROOT_ECOSISTEMA
    ↓ coordina
PROYECTOS DUEÑOS
```

Cada proyecto conserva su propia fuente de verdad. ROOT_CONSOLE no duplica expedientes, datos privados ni estados autoritativos.

## Estado

**PROPUESTA_COMPLETA_CONSOLIDADA / NO_IMPLEMENTADO**

La especificación funcional completa está en:

- [PROPOSAL_COMPLETE.md](docs/PROPOSAL_COMPLETE.md)

Documentación de apoyo:

- [PRODUCT_SPEC.md](docs/PRODUCT_SPEC.md)
- [ARCHITECTURE.md](docs/ARCHITECTURE.md)
- [UI_SPEC.md](docs/UI_SPEC.md)
- [GLOBAL_MENU.md](docs/GLOBAL_MENU.md)
- [WORKFLOWS.md](docs/WORKFLOWS.md)
- [DATA_MODEL.md](docs/DATA_MODEL.md)
- [STATES.md](docs/STATES.md)
- [PRIVACY.md](docs/PRIVACY.md)
- [ROADMAP.md](docs/ROADMAP.md)
- [STATUS.md](STATUS.md)
- [HANDOFF.md](HANDOFF.md)

## Alcance de la propuesta

Incluye:

- Home / Hoy
- Proyectos
- Decisiones
- Auditor
- Actividad
- Fuentes de verdad
- Consulta ROOT
- Command Center
- navegación móvil
- menú global ROOT
- modelo de estados
- modelo de datos
- contradicciones
- niveles READ / PREPARE / EXECUTE
- privacidad PRIVATE / SANITIZED / PUBLIC
- roadmap V0.1 → V1.0

## Seguridad

Este repositorio es actualmente público. Toda documentación y ejemplo debe permanecer sanitizado.

No incluir:

- PII;
- credenciales;
- secretos;
- rutas privadas sensibles;
- IDs sensibles;
- datos operativos privados;
- arquitectura confidencial.

Regla:

```text
PRIVATE → SANITIZED → PUBLIC
```

No se permite copiar directamente información privada a superficies públicas.

## Implementación

No existe frontend implementado todavía.

La primera fase futura será V0.1 con datos mock/sanitizados y validación mobile-first.
