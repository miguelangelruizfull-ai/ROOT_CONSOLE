# ROOT_CONSOLE — HANDOFF

## Propósito del handoff

Permitir retomar ROOT_CONSOLE sin reconstruir la conversación que originó el proyecto.

## Identidad

ROOT_CONSOLE es la interfaz del ecosistema ROOT.

No es:

- una segunda fuente de verdad;
- un reemplazo de ROOT_ECOSISTEMA;
- un repositorio de datos privados;
- una base maestra de proyectos.

## Relación

```text
ROOT_CONSOLE
      ↓ presenta / consulta
ROOT_ECOSISTEMA
      ↓ coordina
PROYECTOS DUEÑOS
```

## Principios ya aprobados para la especificación

- navegación global por proyectos;
- módulos internos solo dentro de su proyecto;
- una siguiente acción principal;
- bandeja separada de decisiones;
- estados normalizados;
- auditor con riesgo + acción + propósito;
- fuentes de verdad visibles sin duplicarlas;
- mobile-first;
- PRIVATE → SANITIZED → PUBLIC;
- no inventar datos no confirmados.

## Pantallas previstas

1. HOY
2. PROYECTOS
3. DECISIONES
4. AUDITOR
5. ACTIVIDAD
6. FUENTES DE VERDAD
7. CONSULTA

## Estado al pausar

La propuesta documental está consolidada.

No existe implementación de frontend.

## Reanudación recomendada

Abrir primero:

1. README.md
2. STATUS.md
3. docs/PRODUCT_SPEC.md
4. docs/ARCHITECTURE.md
5. docs/UI_SPEC.md
6. docs/ROADMAP.md

Después iniciar V0.1.

## Restricción importante

Si el repositorio continúa siendo público, no agregar:

- datos identificables;
- secretos;
- credenciales;
- rutas privadas;
- IDs sensibles;
- datos operativos privados;
- arquitectura confidencial de otros proyectos.
