# ROOT_CONSOLE — Workflows

## 1. Modos de acción

ROOT_CONSOLE distingue tres niveles:

### READ

Consultar estado, documentos sanitizados, actividad y fuentes de verdad.

### PREPARE

Preparar cambios, propuestas, auditorías, borradores o acciones sin ejecutarlas sobre la fuente autoritativa.

### EXECUTE

Aplicar una modificación sobre la fuente dueña cuando la acción esté autorizada y el conector correspondiente lo permita.

La UI debe mostrar claramente en qué nivel se encuentra una acción.

## 2. Siguiente acción

ROOT debe intentar mostrar una sola acción primaria.

Estructura:

```text
SIGUIENTE ACCIÓN
Entidad
Acción
Motivo
Para qué sirve
[ CONTINUAR ]
```

Las acciones secundarias permanecen disponibles, pero no compiten visualmente con la principal.

## 3. Flujo de decisión

```text
WAITING_USER
    ↓
abrir decisión
    ↓
ver contexto
    ↓
resolver explícitamente
    ↓
escribir en fuente dueña
    ↓
registrar evento
    ↓
recalcular siguiente acción
```

Una recomendación no equivale a una decisión aprobada.

## 4. Flujo de auditoría

```text
AUDITAR
  ↓
detectar hallazgo
  ↓
clasificar riesgo
  ↓
proponer acción
  ↓
explicar para qué sirve
  ↓
resolver / revisar / aceptar riesgo
```

## 5. Flujo de contradicción

```text
mismo campo
+ valores diferentes
+ fuentes diferentes
        ↓
CONFLICT
```

Si existe una fuente autoritativa, la UI la identifica.

Si no existe autoridad definida:

```text
VALOR VIGENTE
SIN CONFIRMAR
```

No elegir automáticamente un valor ganador.

## 6. Flujo de privacidad

```text
PRIVATE
  ↓ sanitizar
SANITIZED
  ↓ aprobación
PUBLIC
```

Nunca:

```text
PRIVATE → PUBLIC
```

## 7. Flujo de proyecto

```text
ROOT HOME
  ↓
abrir proyecto
  ↓
cargar contexto
  ↓
mostrar estado
  ↓
mostrar bloqueos
  ↓
mostrar decisiones
  ↓
mostrar siguiente acción
```

## 8. Actividad

Cada evento debe responder:

- qué cambió;
- proyecto;
- entidad;
- actor o tipo de actor;
- estado anterior;
- estado nuevo;
- fecha/hora;
- razón cuando aplique.

## 9. Consulta

Ejemplos de intención:

```text
"abre proyecto" → OPEN_PROJECT
"qué necesita atención" → LIST_ATTENTION
"qué cambió" → LIST_ACTIVITY
"audita" → RUN_AUDIT
"continúa" → CONTINUE_PRIMARY_ACTION
```

La consulta debe respetar contexto y autoridad.
