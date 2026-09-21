# ADR 003 · Sprints de dos semanas con revisión de alcance en cada planning

**Fecha:** 2026-09-19  
**Decide:** Manuel Alejandro Domínguez Guerrero (Producer)  
**Estado:** Aceptada

## Contexto

Taller Umbral opera con equipo ficticio de **6 personas** a **18 meses** (MVP mes 9). El patrón 6 exige que las decisiones de alcance **sobrevivan** al día a día. Un sprint largo sin revisión empuja “acuerdos de pasillo”; uno demasiado corto fragmenta narrativa y arte 2,5D.

## Opciones consideradas

1. **Sprint de 2 semanas + planning obligatorio con checklist ADR**
   - **Gana:** Alinea con Unity/art pipeline; espacio para demo jugable; encaja con revisión quincenal del indicador del antídoto.
   - **Cuesta:** Menos “heroísmo” semanal; planning de 90 min fijo.

2. **Kanban continuo sin sprint**
   - **Gana:** Flexibilidad creativa.
   - **Cuesta:** Alcance entra por tarjetas sin corte; patrón 6 reaparece (nadie recuerda por qué entró una feature).

3. **Sprint de 1 semana**
   - **Gana:** Feedback rápido.
   - **Cuesta:** Sobrecarga de ceremonias; arte 2,5D no termina assets útiles; riesgo crunch invisible.

## Decisión

**Opción 1.** Híbrido **Scrum light**: sprint 2 semanas, **daily 15 min**, **review + retro** al cierre. **Planning:** toda tarjeta que toque tabla de alcance del GDD debe citar ADR *Aceptada* o crear ADR *Propuesta* antes de entrar al sprint.

**Criterio:** Patrón 6 + carta operativa (Definition of Done).

## Consecuencias

- Cronograma (`estudio/cronograma.md`): hitos cada 2 semanas en preproducción; cada 4 en producción.
- Tablero GitHub: columnas `Backlog | Sprint | Review | Done`.
- Riesgo asumido: fechas de feria comercial pueden exigir *exception ADR* de una sola vez.

## Desacuerdo registrado

**Manuel:** prefiere Kanban (opción 2) por variabilidad narrativa.  
**Jonnathan:** sostiene sprint 2 semanas para forzar demo y ADR en planning.  
**Revisión:** Tras vertical slice (semana 22), si velocity estable ±10% durante 3 sprints, se puede ADR para Kanban solo en fase de pulido (meses 10–18).

## Revisión del equipo

**Manuel Domínguez:** revisada y aceptada. La decisión sobre sprints de dos
semanas representa el acuerdo actual del equipo.
