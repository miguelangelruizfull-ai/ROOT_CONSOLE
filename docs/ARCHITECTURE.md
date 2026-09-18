# ROOT_CONSOLE — Architecture

## 1. Rol

ROOT_CONSOLE es capa de presentación y operación.

```text
┌────────────────────────────┐
│        ROOT_CONSOLE        │
│ UI / consulta / decisiones │
└─────────────┬──────────────┘
              │
              ▼
┌────────────────────────────┐
│       ROOT_ECOSISTEMA      │
│ coordinación / gobierno    │
└─────────────┬──────────────┘
              │
      ┌───────┼────────┐
      ▼       ▼        ▼
   PROYECTO PROYECTO PROYECTO
     DUEÑO     DUEÑO     DUEÑO
```

## 2. Regla de autoridad

ROOT_CONSOLE nunca se declara fuente de verdad de datos operativos de un proyecto.

La autoridad vive en:

1. repositorio dueño;
2. documento o base autorizada;
3. estado vigente del proyecto;
4. fuente privada cuando corresponda.

ROOT_CONSOLE guarda únicamente metadatos necesarios para operar la interfaz cuando exista autorización para ello.

## 3. Capas

### Presentación

- Home
- Proyectos
- Decisiones
- Auditor
- Actividad
- Fuentes de verdad
- Consulta

### Adaptadores

Transforman estados propios de cada proyecto a un esquema común.

Ejemplo:

```text
PENDIENTE_APROBACION_USUARIO
        ↓
WAITING_USER
```

### Dominio normalizado

Entidades comunes:

- Project
- Entity
- Decision
- Task
- AuditFinding
- Event
- SourceReference

### Fuentes externas

Los conectores reales se integrarán progresivamente. La UI no debe depender de rutas o IDs privados codificados en el frontend.

## 4. Flujo de lectura

```text
Fuente autoritativa
      ↓
Adaptador
      ↓
Estado sanitizado
      ↓
ROOT_CONSOLE
```

## 5. Flujo de escritura

```text
Acción en UI
      ↓
Validación
      ↓
Autorización requerida
      ↓
Escritura en fuente dueña
      ↓
Evento
      ↓
Refresco de estado
```

Nunca se considera completada una escritura solo por cambiar el estado visual local.

## 6. Separación de navegación

La navegación global muestra proyectos.

Los módulos aparecen únicamente dentro de su proyecto.

Esto evita colisiones entre códigos, menús y estados internos.

## 7. Seguridad

No codificar en cliente:

- credenciales;
- tokens;
- rutas privadas sensibles;
- IDs privados innecesarios;
- PII;
- secretos de infraestructura.

Todo dato mostrado debe respetar la clasificación de visibilidad.

## 8. Evolución

V0.1 puede operar con datos mock/sanitizados y contratos estables.

Las integraciones reales se agregan después sin cambiar la arquitectura visual principal.
