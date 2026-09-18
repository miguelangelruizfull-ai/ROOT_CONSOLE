# ROOT_CONSOLE — HANDOFF

## Estado

**PROPUESTA_COMPLETA_CONSOLIDADA / NO_IMPLEMENTADO**

## Propósito

Permitir retomar ROOT_CONSOLE sin reconstruir la conversación original.

## Identidad

ROOT_CONSOLE es la interfaz operativa del ecosistema ROOT.

No es:

- una segunda fuente de verdad;
- un reemplazo de ROOT_ECOSISTEMA;
- un repositorio de datos privados;
- una base maestra paralela.

## Relación

```text
ROOT_CONSOLE
      ↓ presenta / consulta
ROOT_ECOSISTEMA
      ↓ coordina
PROYECTOS DUEÑOS
```

## Documento principal

Abrir primero:

`docs/PROPOSAL_COMPLETE.md`

Después consultar según necesidad:

1. STATUS.md
2. docs/ARCHITECTURE.md
3. docs/UI_SPEC.md
4. docs/GLOBAL_MENU.md
5. docs/WORKFLOWS.md
6. docs/DATA_MODEL.md
7. docs/STATES.md
8. docs/PRIVACY.md
9. docs/ROADMAP.md

## Principios consolidados

- navegación global por proyectos;
- módulos internos solo dentro del proyecto activo;
- una siguiente acción principal;
- decisiones humanas separadas;
- READ / PREPARE / EXECUTE;
- estados normalizados;
- auditor con riesgo + acción + propósito;
- contradicciones sin elegir valores no autorizados;
- fuentes de verdad visibles sin duplicarlas;
- mobile-first;
- PRIVATE → SANITIZED → PUBLIC;
- no inventar datos no confirmados.

## Pantallas

1. HOY
2. PROYECTOS
3. DECISIONES
4. AUDITOR
5. ACTIVIDAD
6. FUENTES DE VERDAD
7. CONSULTA
8. vistas contextuales de proyecto/entidad
9. Command Center

## Implementación

No iniciada.

La reanudación debe comenzar por V0.1 con datos mock/sanitizados.

## Restricción

Mientras el repositorio siga público, mantener todo el contenido sanitizado y libre de PII, credenciales, secretos, IDs sensibles, rutas privadas y arquitectura confidencial.
