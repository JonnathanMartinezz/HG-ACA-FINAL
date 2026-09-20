# ADR 005 · Cámara 2,5D ortográfica (no perspectiva libre 3D)

**Fecha:** 2026-09-19  
**Decide:** Jonnathan Martínez  
**Estado:** Aceptada

## Contexto

*Umbral* necesita legibilidad de cambios de estado del mundo (pilar 1) y presencia constante de **Thai** sin costura de animación 3D compleja. El vertical slice debe producirse con equipo pequeño al inicio (2 personas reales en el ACA; 2 devs ficticios meses 1–3).

## Opciones consideradas

1. **2,5D ortográfica + parallax por capas**
   - **Gana:** Arte escalable; flags de mundo visibles; C# en Unity maneja sorting y triggers con bajo riesgo.
   - **Cuesta:** Menos “wow” de cámara cinematográfica 3D.

2. **3D third-person con cámara libre**
   - **Gana:** Tráiler más espectacular.
   - **Cuesta:** +animación locomotion; desvía foco del dilema; incoherente con presupuesto inicial.

3. **2D lateral puro**
   - **Gana:** Mínimo costo.
   - **Cuesta:** Limita lectura espacial de “mundo mutante”; Thai pierde profundidad escénica.

## Decisión

**Opción 1.** Escena referencia: `BosqueUmbral_VSlice.unity` (ver `CONTRIBUTING.md` §3).

**Criterio:** Pilar 1 + ADR 001 (fortaleza C# / Unity 2,5D) + cronograma vertical slice semana 22.

## Consecuencias

- GDD § Look and feel alineado.
- Art pipeline: capas en `Art/Sprites/` + parallax en `Scenes/`.
- Riesgo asumido: comparación con referentes 3D; moodboard enfatiza iluminación y color.

## Desacuerdo registrado

**Manuel:** vota opción 2 para pitch al inversionista (segmento A video).  
**Jonnathan:** acepta **tráiler con cámara dramática pre-render** solo para marketing, pero **gameplay** permanece 2,5D — debe etiquetarse en materiales para no contradecir segmento B (misma verdad, distinto encuadre).
