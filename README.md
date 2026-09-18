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

## Alcance inicial

La primera etapa es de especificación y diseño. No hay automatización productiva ni publicación automática.

### V0.1

- Home / Hoy
- Proyectos
- Consulta ROOT
- Siguiente acción
- Estado global

### Evolución prevista

- V0.2 — Decisiones
- V0.3 — Integración de módulos sanitizados
- V0.4 — Auditor y contradicciones
- V0.5 — Actividad e historial
- V0.6 — Fuentes de verdad
- V1.0 — Consola ROOT completa

## Seguridad

Este repositorio puede contener únicamente información apta para su nivel de visibilidad.

Regla de flujo:

```text
PRIVATE → SANITIZED → PUBLIC
```

No se permite copiar directamente información privada a superficies públicas.

## Estado

**ESPECIFICACION_INICIAL / NO_IMPLEMENTADO**

Ver:

- [PRODUCT_SPEC.md](docs/PRODUCT_SPEC.md)
- [ARCHITECTURE.md](docs/ARCHITECTURE.md)
- [UI_SPEC.md](docs/UI_SPEC.md)
- [DATA_MODEL.md](docs/DATA_MODEL.md)
- [STATES.md](docs/STATES.md)
- [PRIVACY.md](docs/PRIVACY.md)
- [ROADMAP.md](docs/ROADMAP.md)
- [STATUS.md](STATUS.md)
- [HANDOFF.md](HANDOFF.md)
