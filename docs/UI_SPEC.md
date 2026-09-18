# ROOT_CONSOLE — UI Specification

## 1. App Shell

Escritorio:

```text
TopBar
├── navegación lateral
├── contenido principal
├── panel contextual
└── command center
```

Móvil:

```text
TopBar
Contenido
BottomNavigation
ROOT Action
```

## 2. Home

Secciones:

### Estado global

- operativos;
- atención;
- bloqueados.

### Siguiente acción

Una acción primaria con:

- entidad;
- acción;
- motivo;
- botón CONTINUAR.

### Decisiones

Resumen de decisiones pendientes.

### Proyectos

Tarjetas de alto nivel.

### Actividad

Cambios recientes relevantes.

## 3. Project Card

Campos visibles:

- nombre;
- estado;
- pendientes;
- bloqueos;
- esperando usuario;
- siguiente acción.

## 4. Decision Card

```text
REQUIERE DECISIÓN

Entidad
Contexto breve
Estado

[ VER ] [ RESOLVER ]
```

Las opciones concretas dependen del dominio.

## 5. Auditor Card

```text
HALLAZGO

Título
RIESGO
ACCIÓN
PARA QUÉ SIRVE

[ CORREGIR ] [ REVISAR ]
```

## 6. Source of Truth View

Debe poder mostrar:

```text
CAMPO
valor

ESTADO
CONFIRMED / UNCONFIRMED / CONFLICT

AUTORIDAD
referencia lógica sanitizada
```

## 7. Conflictos

Si hay fuentes contradictorias:

```text
CONFLICTO

Fuente A → valor
Fuente B → valor

AUTORIDAD
definida / no definida
```

Si no existe autoridad definida, no seleccionar un valor ganador.

## 8. Estados visuales

Conservar pocos estados visuales:

- OPERATIVO
- ATENCIÓN
- BLOQUEADO
- INACTIVO

Los estados de dominio se muestran como etiquetas secundarias.

## 9. Sistema visual

- base neutra;
- pocos colores;
- color reservado para estados y alertas;
- tipografía clara;
- mínima decoración;
- iconografía solo cuando mejora reconocimiento;
- alta legibilidad móvil.

## 10. Command Center

Campo persistente:

```text
> Escribe una orden ROOT...
```

Acciones rápidas:

- CONSULTAR
- CONTINUAR
- ABRIR
- AUDITAR
- REGISTRAR
- BUSCAR

## 11. Panel contextual

Al abrir una entidad debe mostrar:

- proyecto;
- estado;
- fuente de verdad;
- último cambio;
- siguiente acción.

No debe exponer información privada que la interfaz no necesita.

## 12. Accesibilidad

- controles táctiles amplios;
- no depender solo del color;
- contraste suficiente;
- navegación por teclado en escritorio;
- etiquetas textuales para estados.
