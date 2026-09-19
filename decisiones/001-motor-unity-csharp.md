# ADR 001 · Usamos Unity con C# como motor de *Umbral*

**Fecha:** 2026-09-19  
**Decide:** Jonnathan Martínez y Manuel Alejandro Domínguez Guerrero (consenso)  
**Estado:** Aceptada

## Contexto

Taller Umbral debe entregar un GDD creíble, un vertical slice demostrable y un MVP acotado en **2,5D narrativo** con sistemas de vínculos (Thai y progresión de compañeros).

El **equipo real del ACA** (dos integrantes) construye la propuesta y debe poder **sustentarla oralmente** (Sesión 8). Ambos acumulan experiencia en **C#** dentro de la Especialización en Diseño y Desarrollo de Videojuegos (proyectos académicos, lógica de gameplay, UI y tooling). Ese es el activo principal: reducir riesgo de prototipo y de coherencia entre diseño y implementación en el vertical slice.

## Opciones consideradas

1. **Unity + C#**
   - **Gana:** Alineación directa con la **fortaleza compartida del duo** en C#; iteración rápida de UI narrativa, flags de mundo y progresión de vínculos; pipeline 2D/2,5D maduro.
   - **Cuesta:** Nomenclatura de assets: referencia Unreal en consigna, convenciones **nativas** Unity en `CONTRIBUTING.md`.

2. **Unreal Engine 5 + Blueprint/C++**
   - **Gana:** Proximidad literal a la guía de nomenclatura Epic; percepción AAA en pitch visual.
   - **Cuesta:** **C++ y Blueprint** no son el fuerte del equipo; mayor fricción para prototipar el sistema de Thai y el core loop en el tiempo del ACA; desalineación entre lo que el GDD promete y lo que el duo puede demostrar.

3. **Godot + GDScript / C#**
   - **Gana:** Ligereza para equipos mínimos.
   - **Cuesta:** Menor continuidad con el stack ya practicado en el programa en **Unity**; el equipo prefiere no dividir energía entre otro editor y otro pipeline de export en plazo de entrega.

## Decisión

**Opción 1 — Unity + C#.**

**Criterio (orden de peso):**

1. **Capacidad demostrable del equipo:** Jonnathan y Manuel pueden diseñar y explicar sistemas en C# (vínculos, estado del mundo, guardado) sin depender de un stack que no dominan.
2. **Encaje del producto:** 2,5D narrativo + compañero no exige el costo fijo de un pipeline UE para este alcance.
3. **Soporte de planeación (secundario):** licencia Unity coherente con presupuesto hipotético y roles C# en mercado local — argumento para inversionista, no sustituto del punto 1.

## Consecuencias

- GDD y vertical slice se diseñan para cámara 2,5D y prefab `Assets/_Project/Prefabs/Companions/Thai.prefab`.
- Scripts bajo namespaces `TallerUmbral.*` y reglas §5 de `CONTRIBUTING.md`.
- Carta operativa: perfiles de contratación priorizan **Gameplay Programmer (C#)** alineados al stack ya usado por los fundadores del ejercicio.
- Riesgo asumido: comparación visual con referentes UE; se mitiga con identidad 2,5D acotada (moodboard) y profundidad de Thai (ADR 002).

## Desacuerdo registrado

*(Ninguno en esta decisión; consenso inicial. Desacuerdos previstos en ADR 002 — alcance de vínculos en MVP.)*
