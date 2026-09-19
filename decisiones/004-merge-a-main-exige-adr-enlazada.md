# ADR 004 · Merge a main que altere alcance exige ADR aceptada enlazada

**Fecha:** 2026-09-19  
**Decide:** Jonnathan Martínez (Tech Lead) + Manuel Domínguez (Producer)  
**Estado:** Aceptada

## Contexto

Patrón **6** (ver `diagnostico/patron-de-fallo.md`): en ACA 1 las decisiones de método y reparto **no quedaron escritas**, lo que produjo contradicciones entre documentos. El antídoto de Taller Umbral debe **operar sin depender de la memoria** del martes difícil.

## Opciones consideradas

1. **Regla de merge:** cualquier cambio a `gdd/GDD.md` (sección alcance), `gdd/GDD.pdf` o nuevo ADR que recorte/añada MVP/vertical slice lleva en el PR descripción con enlace `decisiones/NNN-*.md` en estado *Aceptada*.
   - **Gana:** Verificable por tercero en GitHub; alinea repo ACA con operación ficticia del estudio.
   - **Cuesta:** Fricción inicial; 20 min por decisión (Anexo A patrón 6).

2. **Acta de reunión semanal en Drive**
   - **Gana:** Familiar para equipos no técnicos.
   - **Cuesta:** No versionada; no enlaza a código/GDD; patrón 6 persiste.

3. **Confianza + retro oral**
   - **Gana:** Cero overhead.
   - **Cuesta:** Repite ACA 1; inaceptable para C2.

## Decisión

**Opción 1.** **Dueño del mecanismo:** Producer (Manuel en operación del repo ACA; rol ficticio en carta). **Tech Lead** revisa en cada PR que toque rutas sensibles: `gdd/GDD.md`, `gdd/GDD.pdf`, `decisiones/`.

**Criterio:** Prueba del mecanismo (consigna): ¿funciona cuando nadie “se acuerda”? Sí: el historial git muestra ausencia/presencia del enlace ADR.

## Consecuencias

- `CONTRIBUTING.md` §9 actualizado como DoD obligatorio.
- Plantilla PR (`.github/pull_request_template.md`) con checkbox ADR.
- Indicador trimestral documentado en carta operativa § El antídoto.

## Desacuerdo registrado

**Manuel:** teme burocracia en meses 10–18 (pulido). Propone whitelist de rutas solo hasta MVP.  
**Jonnathan:** insiste en mantener regla hasta MVP mes 9 mínimo.  
**Acuerdo:** Regla estricta hasta tag `mvp-lock`; después ADR 003 condiciona relajación tras playtest.
