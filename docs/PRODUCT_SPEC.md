# ROOT_CONSOLE — Product Specification

## 1. Objetivo

ROOT_CONSOLE es la interfaz operativa del ecosistema ROOT. Su función es reducir complejidad y responder con rapidez:

1. ¿Qué está pasando?
2. ¿Qué requiere atención?
3. ¿Qué espera decisión humana?
4. ¿Cuál es la siguiente acción?
5. ¿Qué fuente de verdad manda?

No reemplaza las fuentes de verdad de cada proyecto.

## 2. Principios

- Una sola acción primaria visible cuando sea posible.
- Separación clara entre información, recomendación y decisión.
- Ninguna decisión humana se considera aprobada hasta registrarse explícitamente.
- Los datos críticos no confirmados se muestran como pendientes, nunca se inventan.
- La interfaz muestra contexto útil sin exponer arquitectura privada innecesaria.
- Los módulos internos de un proyecto no se mezclan con la navegación global.
- Toda acción recomendada explica para qué sirve.
- La interfaz debe funcionar primero en móvil.

## 3. Navegación principal

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

## 4. Home / Hoy

Debe mostrar:

- estado global;
- número de proyectos operativos;
- elementos que requieren atención;
- bloqueos;
- siguiente acción;
- decisiones pendientes;
- cambios recientes.

Home no debe mostrar rutas privadas, IDs sensibles, credenciales ni detalles de infraestructura que no sean necesarios para operar.

## 5. Proyectos

La vista global muestra proyectos, no repositorios internos.

Cada tarjeta debe incluir:

- nombre;
- estado normalizado;
- pendientes;
- bloqueos;
- elementos esperando decisión;
- siguiente acción.

Al abrir un proyecto, ROOT_CONSOLE carga su navegación contextual.

## 6. Decisiones

Bandeja exclusiva de decisiones humanas.

Cada decisión debe incluir:

- entidad;
- pregunta;
- contexto;
- estado;
- opciones permitidas;
- fecha de creación;
- resolución;
- fecha de resolución.

Resolver una decisión debe generar un evento de historial.

## 7. Consulta ROOT

Entrada en lenguaje natural para comandos como:

- qué requiere mi atención;
- qué cambió;
- abre un proyecto;
- muestra bloqueos;
- audita un proyecto;
- cuál es la siguiente acción.

La consulta no debe atribuir autoridad a un dato que no la tenga.

## 8. Auditor

El auditor identifica:

- contradicciones;
- información sin confirmar;
- exposición de privacidad;
- documentación desactualizada;
- bloqueos;
- duplicación de fuentes de verdad.

Cada hallazgo debe mostrar:

- riesgo;
- acción recomendada;
- para qué sirve;
- estado del hallazgo.

## 9. Fuentes de verdad

ROOT_CONSOLE presenta la autoridad de cada dato o módulo sin duplicarla.

Estados mínimos de un campo:

- CONFIRMED
- UNCONFIRMED
- CONFLICT
- NOT_AVAILABLE

## 10. Command Center

Entrada persistente para órdenes ROOT.

Debe convertir lenguaje natural a una intención interna, por ejemplo:

```text
"abre proyecto" → OPEN_PROJECT
"qué necesita atención" → LIST_ATTENTION
"audita" → RUN_AUDIT
```

## 11. Móvil

Navegación inferior recomendada:

```text
HOY | PROYECTOS | DECISIONES | CONSULTA
```

Auditor, actividad y fuentes de verdad se acceden desde contexto o menú secundario.

## 12. No objetivos iniciales

- no publicar automáticamente;
- no almacenar PII;
- no reemplazar expedientes;
- no convertirse en base maestra;
- no replicar repositorios privados;
- no resolver por inferencia datos que requieren confirmación.

## 13. Criterio de éxito

ROOT_CONSOLE funciona cuando una persona puede abrir la interfaz y saber, sin reconstruir conversaciones anteriores:

- dónde está;
- qué está pendiente;
- qué fuente manda;
- qué requiere decisión;
- cuál es el siguiente paso.
