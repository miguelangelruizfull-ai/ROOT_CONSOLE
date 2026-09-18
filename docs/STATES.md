# ROOT_CONSOLE — States

## Estados universales

- READY
- IN_PROGRESS
- WAITING_USER
- WAITING_EXTERNAL
- REVIEW_REQUIRED
- BLOCKED
- NO_PUBLISH
- COMPLETED
- ARCHIVED

## Estados visuales

La UI reduce los estados de dominio a cuatro señales principales:

- OPERATIVO
- ATENCIÓN
- BLOQUEADO
- INACTIVO

## Reglas de mapeo

Un proyecto puede conservar estados internos específicos. El adaptador de ROOT_CONSOLE los transforma a un estado universal sin borrar el estado original.

Ejemplo:

```text
PENDIENTE_APROBACION_USUARIO
        ↓
WAITING_USER
        ↓
ATENCIÓN
```

## Confirmación de datos

Para campos individuales:

- CONFIRMED
- UNCONFIRMED
- CONFLICT
- NOT_AVAILABLE

## Decisiones

- OPEN
- RESOLVED
- CANCELLED
- SUPERSEDED

## Hallazgos de auditoría

- OPEN
- IN_REVIEW
- RESOLVED
- ACCEPTED_RISK
- DISMISSED

## Principio

La UI nunca debe transformar un estado ambiguo en uno más definitivo solo para simplificar la presentación.
