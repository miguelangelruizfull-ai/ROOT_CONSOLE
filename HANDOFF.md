# ROOT_CONSOLE — HANDOFF

## Estado

**V0.1_IMPLEMENTADA / MOBILE_FIRST**

## Entrada

Abrir `index.html`.

## Propósito

ROOT_CONSOLE es la interfaz operativa del ecosistema ROOT.

No es:

- una segunda fuente de verdad;
- un reemplazo de ROOT_ECOSISTEMA;
- un repositorio de datos privados;
- una base maestra paralela.

## Implementado

- HOY;
- estado global;
- siguiente acción;
- PROYECTOS;
- DECISIONES;
- CONSULTA;
- vista contextual;
- navegación móvil;
- estado sanitizado local.

## Fuentes

Documento funcional:

`docs/PROPOSAL_COMPLETE.md`

Estado ejecutable:

`data/state.json`

El JSON contiene únicamente información pública/sanitizada y no debe convertirse en autoridad.

## Regla de ejecución

```text
UI
→ prepara/navega
→ ROOT valida autorización
→ proyecto dueño recibe escritura
→ UI se refresca
```

## Privacidad

Mantener fuera de este repositorio:

- PII;
- credenciales;
- RAW;
- VIN;
- enlaces privados;
- rutas internas sensibles;
- secretos;
- datos operativos privados.

## Siguiente

1. verificar despliegue;
2. validar en teléfono real;
3. después avanzar a V0.2 Decisiones con integración autorizada.
