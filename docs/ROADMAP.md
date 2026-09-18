# ROOT_CONSOLE — Roadmap

## V0.1 — Base operativa

Objetivo: validar navegación y jerarquía sin integrar todavía todas las fuentes reales.

Incluye:

- Home / Hoy
- Proyectos
- Consulta ROOT
- Siguiente acción
- Estado global
- datos mock/sanitizados
- diseño mobile-first

Criterio de salida:

Una persona puede abrir ROOT_CONSOLE y entender estado, proyecto activo y siguiente acción.

## V0.2 — Decisiones

- bandeja de decisiones;
- estados OPEN / RESOLVED;
- registro de resolución;
- historial de decisión;
- separación entre sugerencia y aprobación.

## V0.3 — Integración contextual

- adaptadores por proyecto;
- navegación interna por contexto;
- integración inicial de estados sanitizados;
- primeras entidades especializadas.

## V0.4 — Auditor

- hallazgos;
- contradicciones;
- privacidad;
- datos sin confirmar;
- documentación desactualizada;
- explicación “para qué sirve” en cada acción recomendada.

## V0.5 — Actividad e historial

- Event Log;
- vista cronológica;
- cambios por proyecto;
- respuesta a “qué cambió”.

## V0.6 — Fuentes de verdad

- autoridad por campo;
- estados CONFIRMED / UNCONFIRMED / CONFLICT;
- resolución de referencias;
- detección de contradicciones.

## V1.0 — Consola completa

- navegación estable;
- modelo normalizado;
- adaptadores productivos;
- auditor;
- decisiones;
- actividad;
- fuentes de verdad;
- seguridad y privacidad verificadas.

## Orden de implementación

No avanzar a integraciones profundas mientras el modelo de navegación y autoridad no esté estable.

ROOT_CONSOLE debe crecer como consumidor del ecosistema, no como duplicado de éste.
