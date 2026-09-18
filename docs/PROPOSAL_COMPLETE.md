# ROOT_CONSOLE — Propuesta Completa Consolidada

## 0. Estado de esta propuesta

Documento canónico de diseño funcional de ROOT_CONSOLE.

Estado:

```text
PROPUESTA_COMPLETA_CONSOLIDADA
IMPLEMENTACION_NO_INICIADA
```

ROOT_CONSOLE es la interfaz del ecosistema ROOT. ROOT_ECOSISTEMA continúa siendo la capa de coordinación/gobierno y cada proyecto conserva su propia fuente de verdad.

---

# 1. Objetivo de producto

ROOT_CONSOLE debe permitir abrir el sistema y responder inmediatamente:

1. ¿Qué está pasando?
2. ¿Qué requiere atención?
3. ¿Qué espera una decisión humana?
4. ¿Qué está bloqueado?
5. ¿Qué fuente de verdad manda?
6. ¿Qué cambió recientemente?
7. ¿Cuál es la siguiente acción?

Principio central:

```text
ROOT sabe dónde estoy,
qué está pendiente,
qué fuente manda
y cuál es el siguiente paso.
```

---

# 2. Arquitectura conceptual

```text
ROOT_CONSOLE
      ↓ interfaz / consulta / decisiones
ROOT_ECOSISTEMA
      ↓ coordinación / gobierno
PROYECTOS DUEÑOS
      ↓
FUENTES DE VERDAD
```

ROOT_CONSOLE no debe convertirse en una segunda fuente de verdad.

Flujo de resolución:

```text
PROYECTO
→ REPOSITORIO DUEÑO
→ FUENTE DE VERDAD
→ ESTADO
→ SIGUIENTE ACCIÓN
```

---

# 3. Navegación global

```text
ROOT
├── HOY
├── PROYECTOS
├── DECISIONES
├── AUDITOR
├── ACTIVIDAD
├── FUENTES DE VERDAD
└── CONSULTA
```

La navegación por proyectos puede mapear los accesos ROOT definidos en GLOBAL_MENU.md.

Los módulos internos de cada proyecto solo aparecen después de abrir dicho proyecto.

---

# 4. Pantalla HOY

Objetivo: comprender el estado global en segundos.

```text
┌────────────────────────────────────────────┐
│ ROOT                         CONSULTAR     │
├────────────────────────────────────────────┤
│ HOY                                        │
│                                            │
│ ● OPERATIVOS                              │
│ ▲ REQUIEREN ATENCIÓN                      │
│ ■ BLOQUEADOS                              │
├────────────────────────────────────────────┤
│ SIGUIENTE ACCIÓN                           │
│                                            │
│ Entidad                                    │
│ Acción                                     │
│ Motivo                                     │
│                                            │
│ [ CONTINUAR ]                              │
├────────────────────────────────────────────┤
│ DECISIONES                                 │
│ elementos esperando resolución humana      │
├────────────────────────────────────────────┤
│ PROYECTOS                                  │
│ tarjetas de alto nivel                     │
├────────────────────────────────────────────┤
│ ACTIVIDAD                                  │
│ cambios relevantes recientes               │
└────────────────────────────────────────────┘
```

Home no muestra infraestructura privada innecesaria.

---

# 5. Pantalla PROYECTOS

Cada proyecto aparece como tarjeta.

```text
┌──────────────────────────┐
│ NOMBRE DEL PROYECTO      │
│ ● OPERATIVO              │
│ pendientes: N            │
│ bloqueos: N              │
│ esperando usuario: N     │
│                          │
│ [ ABRIR ]                │
└──────────────────────────┘
```

La vista global muestra proyectos, no repositorios internos.

---

# 6. Vista de proyecto

Al abrir un proyecto cambia el contexto.

```text
ROOT > PROYECTO

ESTADO
● OPERATIVO

MÓDULOS / ÁREAS
...

REQUIERE ATENCIÓN
...

SIGUIENTE ACCIÓN
...

[ CONTINUAR ]
```

La navegación contextual debe conservar claramente el nombre del proyecto activo.

---

# 7. Vista de entidad

Una entidad puede ser vehículo, documento, publicación, repositorio, tarea u otra unidad operativa.

Debe mostrar:

- identidad;
- estado;
- publicación/visibilidad cuando aplique;
- datos confirmados;
- datos pendientes;
- material relacionado;
- siguiente acción;
- historial;
- fuente de verdad.

Ejemplo abstracto:

```text
PROYECTO > ENTIDAD

ESTADO
WAITING_USER

DATOS
Campo A      CONFIRMED
Campo B      UNCONFIRMED

MATERIAL
...

SIGUIENTE ACCIÓN
...

HISTORIAL
...
```

---

# 8. Pantalla DECISIONES

Bandeja exclusiva para decisiones humanas.

```text
ROOT > DECISIONES

REQUIERE DECISIÓN

Entidad
Contexto
Pregunta

[ VER ]
[ RESOLVER ]
```

Una recomendación no se considera aprobada.

Al resolver:

1. registrar resolución;
2. escribir en la fuente dueña cuando corresponda;
3. generar evento;
4. recalcular estado;
5. recalcular siguiente acción.

---

# 9. AUDITOR ROOT

```text
ROOT > AUDITOR

✓ controles correctos
▲ advertencias
■ bloqueos

HALLAZGO

Título
RIESGO
...
ACCIÓN RECOMENDADA
...
PARA QUÉ SIRVE
...

[ CORREGIR ]
[ REVISAR ]
[ ACEPTAR RIESGO ]
```

Categorías iniciales:

- privacidad;
- contradicciones;
- información sin confirmar;
- fuentes de verdad duplicadas;
- documentación desactualizada;
- bloqueos;
- inconsistencias de estado.

---

# 10. CONSULTA ROOT

Entrada natural:

```text
> Pregunta a ROOT...
```

Ejemplos:

- qué requiere mi atención;
- qué cambió;
- abre un proyecto;
- muéstrame bloqueos;
- cuál es la siguiente acción;
- audita este proyecto;
- qué fuente manda.

Intenciones base:

```text
OPEN_PROJECT
LIST_ATTENTION
LIST_ACTIVITY
RUN_AUDIT
CONTINUE_PRIMARY_ACTION
SHOW_SOURCE_OF_TRUTH
```

---

# 11. ACTIVIDAD

No es un log técnico crudo.

Debe responder:

```text
qué cambió
→ quién o qué lo cambió
→ proyecto
→ entidad
→ resultado
→ fecha/hora
```

Vista cronológica por día/proyecto/entidad.

---

# 12. FUENTES DE VERDAD

Vista dedicada a autoridad de datos.

```text
CAMPO
valor

ESTADO
CONFIRMED / UNCONFIRMED / CONFLICT / NOT_AVAILABLE

AUTORIDAD
referencia lógica sanitizada
```

Si existe conflicto:

```text
CONFLICTO

Fuente A → valor
Fuente B → valor

AUTORIDAD
definida / no definida
```

Si no hay autoridad definida, no seleccionar ganador.

---

# 13. COMMAND CENTER

Disponible de forma persistente.

Escritorio:

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

Móvil: botón ROOT de acción rápida.

---

# 14. Navegación móvil

Barra inferior:

```text
HOY | PROYECTOS | DECISIONES | CONSULTA
```

Auditor, Actividad y Fuentes de verdad viven en menú/contexto secundario.

Diseño mobile-first:

- controles grandes;
- alta legibilidad;
- poco ruido;
- jerarquía clara;
- sin depender únicamente del color.

---

# 15. Panel contextual

Al seleccionar una entidad:

```text
PROYECTO
...

ESTADO
...

FUENTE DE VERDAD
...

ÚLTIMO CAMBIO
...

SIGUIENTE ACCIÓN
...
```

No debe exponer secretos o rutas privadas innecesarias.

---

# 16. Sistema visual

Base neutra y sobria.

Usar color solo como señal:

```text
● OPERATIVO
▲ ATENCIÓN
■ BLOQUEADO
○ INACTIVO
```

Principios:

- diseño simple;
- premium;
- funcional;
- pocos iconos;
- tipografía clara;
- baja carga visual;
- estados visibles;
- texto por encima de decoración.

---

# 17. Estados universales

Dominio:

- READY
- IN_PROGRESS
- WAITING_USER
- WAITING_EXTERNAL
- REVIEW_REQUIRED
- BLOCKED
- NO_PUBLISH
- COMPLETED
- ARCHIVED

Visuales:

- OPERATIVO
- ATENCIÓN
- BLOQUEADO
- INACTIVO

Los estados específicos de cada proyecto se conservan y se mapean, no se reemplazan.

---

# 18. Modelo de entidades

Tipos iniciales:

- PROJECT
- VEHICLE
- REPOSITORY
- DOCUMENT
- PUBLICATION
- LEAD
- DECISION
- TASK
- ASSET
- AUDIT_FINDING
- EVENT
- SOURCE_REFERENCE

Todos deben apuntar a un proyecto dueño.

---

# 19. Sistema de contradicciones

Detección:

```text
MISMO CAMPO
+ VALORES DIFERENTES
+ FUENTES DIFERENTES
= CONFLICT
```

Si una fuente es autoritativa, mostrarla.

Si ninguna lo es:

```text
VALOR VIGENTE
SIN CONFIRMAR
```

Nunca completar por inferencia un dato crítico pendiente.

---

# 20. Niveles de acción

## READ

Consulta sin modificar fuentes.

## PREPARE

Genera propuesta, borrador, auditoría o cambio preparado.

## EXECUTE

Modifica la fuente dueña cuando está autorizado.

La interfaz debe distinguir los tres niveles.

---

# 21. Privacidad

Clasificación:

```text
PRIVATE
SANITIZED
PUBLIC
```

Flujo:

```text
PRIVATE
   ↓ sanitización
SANITIZED
   ↓ aprobación
PUBLIC
```

Nunca:

```text
PRIVATE → PUBLIC
```

Mientras este repositorio sea público:

- no PII;
- no credenciales;
- no secretos;
- no rutas privadas;
- no IDs sensibles;
- no datos operativos privados;
- no arquitectura confidencial.

---

# 22. Arquitectura funcional

```text
ROOT APP
├── AppShell
│   ├── TopBar
│   ├── SideNavigation
│   ├── MainContent
│   ├── ContextPanel
│   └── CommandCenter
│
├── Home
├── Projects
├── Decisions
├── Auditor
├── Activity
├── SourcesOfTruth
└── Search / Consulta
```

Móvil:

```text
ROOT MOBILE
├── TopBar
├── MainContent
├── BottomNavigation
└── ROOT Action
```

---

# 23. Componentes clave

## RootStatusCard

- project;
- status;
- pending;
- blocked;
- waitingUser;
- nextAction.

## NextActionCard

- entidad;
- acción;
- motivo;
- propósito;
- CONTINUAR.

## DecisionCard

- decisión;
- contexto;
- estado;
- opciones;
- resolución.

## AuditFindingCard

- severidad;
- riesgo;
- acción;
- propósito;
- estado.

## SourceOfTruthCard

- campo;
- valor;
- confirmación;
- autoridad.

---

# 24. Flujo de lectura

```text
FUENTE AUTORITATIVA
      ↓
ADAPTADOR
      ↓
ESTADO SANITIZADO
      ↓
ROOT_CONSOLE
```

# 25. Flujo de escritura

```text
ACCIÓN UI
   ↓
VALIDACIÓN
   ↓
AUTORIZACIÓN
   ↓
FUENTE DUEÑA
   ↓
EVENTO
   ↓
REFRESCO
```

Un cambio visual local nunca equivale a una escritura confirmada.

---

# 26. Prioridad de construcción

| Fase | Alcance |
|---|---|
| V0.1 | Home + Proyectos + Consulta + Siguiente acción + Estado global |
| V0.2 | Decisiones |
| V0.3 | Integración contextual/adaptadores |
| V0.4 | Auditor + contradicciones |
| V0.5 | Actividad + historial |
| V0.6 | Fuentes de verdad |
| V1.0 | Consola completa |

V0.1 debe utilizar únicamente datos mock o sanitizados.

---

# 27. Criterios de aceptación V0.1

V0.1 se considera válida si:

- Home carga correctamente;
- proyectos se distinguen sin mezclar módulos;
- existe una siguiente acción;
- Consulta puede resolver navegación básica;
- estados globales son consistentes;
- interfaz móvil es usable;
- no se exponen datos privados;
- no existe duplicación de autoridad.

---

# 28. No objetivos iniciales

- publicación automática;
- almacenamiento de PII;
- sustitución de repositorios dueños;
- base maestra paralela;
- sincronización completa en tiempo real;
- inferencia de datos críticos;
- exposición de arquitectura privada.

---

# 29. Reanudación

Cuando se retome la implementación:

1. revisar STATUS.md;
2. confirmar visibilidad del repositorio;
3. seleccionar stack frontend;
4. crear scaffolding;
5. implementar V0.1 con mocks sanitizados;
6. validar móvil;
7. añadir adaptadores de forma incremental;
8. conectar fuentes reales solo después de estabilizar autoridad y privacidad.

---

# 30. Regla final

ROOT_CONSOLE debe ser una consola para operar el ecosistema, no otro ecosistema.

La interfaz debe reducir complejidad sin esconder autoridad, incertidumbre o decisiones pendientes.
