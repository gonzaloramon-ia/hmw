# HWM — Protocolo de agentes

Este archivo es el contrato operativo persistente para cualquier agente que trabaje en HWM.

## Fuente de verdad

Antes de tocar código, leer SIEMPRE:

1. `AGENTS.md`
2. HEAD de `main`
3. `CAMPAIGN_V1.md`
4. Los comentarios más recientes de GitHub Issue #2

La Issue #2 es el tablero compartido entre agentes.

## Roles

### Agente A — chat principal / líder técnico

Responsabilidades:

- arquitectura e integración;
- gameplay y comportamiento sistémico;
- QA lógico;
- decidir qué entra a `main`;
- resolver conflictos entre tareas;
- mantener coherencia con las decisiones de producto de Gonzalo.

A puede integrar directamente cuando el cambio fue aislado, validado y coherente con el producto.

### Agente B — Work / ejecutor autónomo

Responsabilidades:

- tareas largas o paralelizables;
- arte, assets, variantes, investigación técnica, QA extendido y experimentos;
- trabajar en rama propia;
- dejar resultados listos para integración de A;
- no usar a Gonzalo como supervisor de microdecisiones.

B NO debe detenerse por dudas triviales. Si faltan detalles menores, elige la opción más coherente, reversible y compatible con el estado actual.

## Regla principal de autonomía

El recurso escaso es el tiempo de Gonzalo.

Por lo tanto:

- no pedir confirmación por decisiones triviales;
- no frenar una tarea por ambigüedades resolubles;
- preferir cambios reversibles;
- documentar supuestos;
- acumular preguntas no bloqueantes;
- sólo escalar un bloqueo real, una decisión irreversible o una renuncia importante de producto;
- si hay varias consultas, agruparlas en una sola intervención;
- el desarrollo debe seguir avanzando mientras esas consultas no bloqueen técnicamente.

## Modelo de producto

HWM prioriza:

- identidad de cada ejército y batalla antes que cantidad;
- diferencias mecánicas reales antes que cosmética;
- jugabilidad y claridad táctica antes que simulación rígida;
- formaciones, terreno, moral y cohesión como núcleo;
- batallas distintas entre sí, no reskins;
- máximo aproximado de 10 minutos por batalla;
- experimentos en rama antes de tocar estable;
- cerrar producto antes de expandir indefinidamente.

Una unidad o sistema que no cambia cómo se juega tiene poco valor.

## Flujo Git

Antes de empezar una tarea, comentar en Issue #2:

AGENTE:
ESTADO: EN CURSO
TAREA:
BASE COMMIT:
ARCHIVOS/ZONAS:
OBJETIVO:
NO TOCÓ:
PENDIENTE:

Usar rama propia:

- `agent-a/<tarea>`
- `work/<tarea>`

Al terminar:

AGENTE:
ESTADO: HECHO / BLOQUEADO
TAREA:
BASE COMMIT:
COMMIT RESULTANTE:
CAMBIÓ:
QA:
NO TOCÓ:
PENDIENTE:

No trabajar simultáneamente sobre la misma zona sin coordinarlo primero en Issue #2.

## Política de integración

- B no debe fusionar experimentos grandes directamente a `main` salvo que Issue #2 indique expresamente lo contrario.
- A revisa e integra el trabajo de B.
- Si `main` cambió desde la base de B, B debe actualizar/rebasar su rama o informar el conflicto; no sobreescribir trabajo reciente.
- No borrar versiones/branches de rollback por comodidad.

## Estado actual

Versión visible: **HWM 0.9.1 RC1**.

Campaña válida: 10 batallas:

1. Maratón
2. Termópilas
3. Platea
4. Mantinea
5. Gaugamela
6. Cannas
7. Hastings
8. Agincourt
9. Bosque de Teutoburgo
10. Borodinó

Maratón 2 es archivo/prueba y no cuenta como campaña.

Sistemas ya integrados:

- progreso persistente;
- puntaje, medallas, XP y rangos;
- reservas/refuerzos;
- terreno procedural;
- bosque/barro;
- objetivo de escape y emboscadas;
- artillería y redutos;
- disciplina de falange;
- diferenciación mecánica de ejércitos.

Último bloque funcional integrado por A:

- hoplitas/falanges/muro de escudos en línea no persiguen automáticamente;
- ataques múltiples de falanges avanzan como frente;
- roster ampliado a 30 tipos;
- Cannas, Gaugamela, Hastings y Agincourt usan tropas propias;
- diferenciación visual provisoria mediante paletas/estandartes.

## Prioridad inmediata para Agente B / Work

**Sprites propios por ejército.**

Objetivo: reemplazar gradualmente el atlas visual compartido por familias de sprites reconocibles para cada ejército SIN modificar el comportamiento del gameplay.

Prioridad de producción:

1. Romanos vs germánicos — Teutoburgo
2. Cartago vs Roma — Cannas
3. Macedonia vs Persia — Gaugamela
4. Normandos vs sajones — Hastings
5. Ingleses vs franceses — Agincourt
6. Francia vs Rusia — Borodinó

Requisitos:

- lectura clara en vista top-down;
- escala y anclaje compatibles con el motor actual;
- varias orientaciones;
- siluetas diferenciables a zoom normal;
- estandartes/colores coherentes;
- no depender sólo de recolor;
- conservar fallback al atlas actual;
- no reescribir lógica de combate para adaptar el arte.

B debe inspeccionar cómo consume `assets/units-atlas.webp` el motor actual y proponer/integrar una vía compatible en su rama.

## Pendiente para v1.0

- QA real de las 10 batallas en navegador;
- balance fino;
- revisar lectura visual/HUD;
- completar identidad gráfica de ejércitos.

No declarar v1.0 sólo por pasar validación estática.
