# ROOT_CONSOLE — Data Model

## Project

```json
{
  "id": "project-id",
  "name": "Project Name",
  "status": "READY",
  "pending": 0,
  "blocked": 0,
  "waiting_user": 0,
  "next_action": null
}
```

## Entity

Representa una unidad operativa dentro de un proyecto.

Tipos iniciales:

- PROJECT
- VEHICLE
- REPOSITORY
- DOCUMENT
- PUBLICATION
- DECISION
- TASK
- ASSET
- AUDIT_FINDING

Campos mínimos:

```json
{
  "type": "ENTITY_TYPE",
  "id": "entity-id",
  "project": "project-id",
  "display_name": "Entity",
  "status": "READY",
  "visibility": "SANITIZED"
}
```

## Decision

```json
{
  "id": "decision-id",
  "project": "project-id",
  "entity": "entity-id",
  "question": "Decision required",
  "status": "OPEN",
  "created_at": null,
  "resolved_at": null,
  "resolution": null
}
```

## Task

```json
{
  "id": "task-id",
  "project": "project-id",
  "entity": "entity-id",
  "status": "READY",
  "purpose": "Why this task matters",
  "is_primary": true
}
```

## AuditFinding

```json
{
  "id": "finding-id",
  "project": "project-id",
  "category": "PRIVACY",
  "severity": "WARNING",
  "title": "Finding title",
  "risk": "Risk",
  "recommended_action": "Action",
  "purpose": "Purpose",
  "status": "OPEN"
}
```

## Event

```json
{
  "id": "event-id",
  "project": "project-id",
  "entity": "entity-id",
  "event": "STATE_CHANGED",
  "previous_status": null,
  "new_status": "READY",
  "timestamp": null,
  "actor_type": "USER"
}
```

## SourceReference

No contiene secretos ni rutas sensibles en una superficie pública.

```json
{
  "field": "example",
  "status": "CONFIRMED",
  "authority": "PROJECT_SOURCE_OF_TRUTH",
  "visibility": "SANITIZED"
}
```

## Restricción

Un objeto de ROOT_CONSOLE no debe convertirse en copia autoritativa de datos que pertenecen a otro proyecto.
