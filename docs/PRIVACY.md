# ROOT_CONSOLE — Privacy Model

## Clasificación

ROOT_CONSOLE reconoce tres niveles:

```text
PRIVATE
SANITIZED
PUBLIC
```

## Flujo permitido

```text
PRIVATE
   ↓ sanitización
SANITIZED
   ↓ aprobación
PUBLIC
```

No se autoriza el salto directo PRIVATE → PUBLIC.

## PRIVATE

Ejemplos de categorías que deben mantenerse fuera de una superficie pública:

- datos personales;
- conversaciones identificables;
- credenciales;
- secretos;
- rutas privadas sensibles;
- IDs privados que permitan reconstruir infraestructura;
- material interno no autorizado;
- estrategia confidencial.

## SANITIZED

Puede contener:

- estados normalizados;
- métricas agregadas;
- nombres públicos ya autorizados;
- conteos;
- aprendizajes no identificables;
- referencias lógicas sin exponer ubicación privada.

## PUBLIC

Solo información explícitamente apta para publicación.

## Reglas de interfaz

- Home muestra estado, no infraestructura.
- Los conectores reales no exponen sus secretos al cliente.
- El frontend no almacena credenciales.
- No usar almacenamiento local como fuente definitiva.
- Un dato marcado NO_PUBLISH nunca aparece en una superficie pública.

## Regla para este repositorio

Mientras ROOT_CONSOLE tenga visibilidad pública, toda documentación y ejemplo debe ser sanitizado por defecto.
