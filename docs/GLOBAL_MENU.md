# ROOT_CONSOLE — Global Menu

## Objetivo

Separar la navegación global ROOT de los módulos internos de cada proyecto.

## Menú global

| Código | Área global | Acción |
|---|---|---|
| R0 | ROOT Global | Estado y coordinación general |
| A0 | AFL AUTOS | Abrir proyecto AFL AUTOS |
| G0 | GitHub / Repositorios | Abrir capa de repositorios |
| D0 | Drive | Abrir capa documental privada autorizada |
| W0 | Portafolio | Abrir proyecto Portafolio |
| P0 | Proyectos personales | Abrir otros proyectos |
| Q0 | Consulta ROOT | Consulta transversal |
| AU0 | Auditor ROOT | Auditoría global |
| M0 | Mantenimiento / Migración | Continuidad técnica |
| L0 | Linux / Sistema | Entorno técnico |

## Controles globales

- CK — Checkpoint
- RS — Resumen de estado
- ST — Estado actual
- PA — Pendientes / acciones
- HO — Handoff / continuidad
- XX — Cerrar contexto operativo

## Regla de jerarquía

```text
MIGUEL
  ↓
ROOT
  ↓
COORDINADOR DE PROYECTO
  ↓
MÓDULO
  ↓
EJECUTOR
```

## Regla de navegación

Los códigos internos de un proyecto no se muestran como menú global.

Ejemplo:

```text
ROOT
└── A0 AFL AUTOS
    ├── módulos internos
    ├── estados propios
    └── expedientes propios
```

La UI debe mantener visualmente el contexto activo para evitar mezclar decisiones entre proyectos.

## Resolución ROOT

Toda operación debe poder responder:

```text
PROYECTO
→ REPOSITORIO DUEÑO
→ FUENTE DE VERDAD
→ ESTADO
→ SIGUIENTE ACCIÓN
```

ROOT_CONSOLE presenta esta cadena, pero no reemplaza su autoridad.
