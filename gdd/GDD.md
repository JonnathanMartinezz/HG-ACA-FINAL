# Game Design Document — *Umbral*

**Estudio:** Taller Umbral · **Motor:** Unity (C#) · **Versión doc:** 0.1 (2026-09-19)

> Exportar a PDF (máx. 15 páginas) como `gdd/GDD.pdf` antes de entrega C Digital.

---

## Elevator pitch

**Aventura narrativa 2,5D donde cada dilema muta el mundo — y tu gato vinculado Thai te devuelve caminos que ya no existen para otros.**

---

## Pilares de diseño (máx. 3)

| Pilar | Criterio de “no” | Ejemplo descartado |
|-------|------------------|-------------------|
| **1. El dilema deja huella en el mundo** | Rechazamos puzzles cuya única recompensa es diálogo | Una “elección moral” que solo cambia una línea de voz sin alterar puertas, facciones o recursos |
| **2. Cada sesión cabe en 15 minutos** | Rechazamos capítulos que exigen >15 min sin punto de guardado natural | Un acto continuo de 40 min sin metas intermedias |
| **3. Una mecánica nueva por hora (MVP)** | Rechazamos introducir sistemas paralelos no vinculados al dilema | Minijuego de pesca completo en acto 1 |

---

## Concepto y experiencia buscada

El jugador siente **peso** en decisiones menores: el mundo “recuerda” mediante estados (facade, clima emocional del pueblo, objetos reubicados). **Thai** no es decoración: traduce estados ocultos (rastros, ecos) en pistas jugables.

**Interés frente a referentes:** Menos volumen episódico Telltale-like; más densidad sistémica en espacios pequeños + vínculo con un compañero.

---

## Audiencia y público objetivo

Jugadores **15–40** que consumen narrativa interactiva (Disco Elysium, Pentiment, Gris) con sesiones cortas en PC/consola y que disfruten la exploración en mundos con perspectivas 2.5D. Buscan **consecuencia tangible**, no solo árbol de diálogo. Cambiarían si el juego promete mascotas pero solo son cosméticos → por eso Thai tiene progresión mecánica (ADR 002).

---

## Géneros

- **Principal:** Aventura narrativa  
- **Secundarios:** Exploración 2,5D, gestión ligera de vínculo (compañero)

Expectativa: explorar, leer el entorno, decidir, volver a zonas alteradas.

---

## Core loop

```
Explorar ubicación → Detectar tensión (NPC / entorno)
→ Dilema con 2–3 resoluciones → Cambio de estado del mundo
→ Thai revela ruta/eco alternativo → Meta: desbloquear capas del Umbral
```

- **Loop de sesión:** una tensión + resolución + guardado (~15 min).  
- **Metajuego (MVP):** progresión de afinidad de Thai (rasgo + habilidad pasiva).

*(Diagrama: exportar a `gdd/assets/core-loop.png`.)*

---

## Sistemas del juego

| Sistema | Estados que conserva |
|---------|----------------------|
| **Estado del mundo** | Flags por dilema, variantes de escena |
| **Progresión de vínculos** | Afinidad Thai, rasgos, cooldown habilidad |
| **Economía de atención** | Tiempo-día limitado por sesión (opcional MVP acto 2) |
| **Guardado** | Checkpoints + snapshot de flags |

---

## Mecánicas del juego

| Mecánica | Regla |
|----------|--------|
| **Explorar / interactuar** | Cursor contextual 2,5D |
| **Elegir en dilema** | UI no pausable en combate; pausable en exploración |
| **Invocar eco de Thai** | 1 carga por sesión; revela variante de mapa o pista |
| **Mejorar vínculo** | Objetos + decisiones alineadas al temperamento de Thai |
| **Adoptar vinculado** | MVP: solo Thai (rescate en prologue); visión: otros tipos |

---

## Referentes

| Referente | Qué tomamos | Qué NO tomamos |
|-----------|-------------|----------------|
| *Gris* (2018) | Metáfora visual del estado emocional | Plataformeo exigente |
| *Night in the Woods* | Tono íntimo, humor seco | Estructura open town completa en MVP |
| *Oxenfree* | Ecos / voces del entorno | Chat multijugador |
| *La casa de las hojas* (novela) | Espacio imposible | Prosa no interactiva |

---

## Look and feel · cámara · audio

- **Moodboard:** `gdd/assets/moodboard.png` — paleta fría en “Umbral”, cálida cuando Thai está en pantalla.  
- **Cámara:** 2,5D ortográfica con parallax; limita combate → refuerza pilar 1 narrativo.  
- **Audio:** Thai ancla identidad sonora (ronroneo = feedback de afinidad); diseño sonoro prioriza legibilidad de cambios de estado.

---

## Objetivos del jugador

| Plazo | Objetivo |
|-------|----------|
| Corto | Resolver tensión local |
| Medio | Elevar afinidad de Thai y desbloquear eco |
| Largo (visión) | Cerrar el arco del Umbral y decidir destino de los vinculados |

---

## Alcance en tres capas

| Elemento | Visión completa | Vertical slice | MVP |
|----------|-----------------|----------------|-----|
| Actos / ubicaciones | 4 actos, 4 biomas | 1 ubicación (Bosque del Umbral) | 2 actos, 2 biomas |
| Dilemas mayores | 12+ | 1 | 5 |
| Vinculados | 6 tipos | **Thai** (progresión completa) | **Thai** (+ 2.º tipo post-MVP) |
| Duración | ~12 h | 8–10 min | ~3 h |
| Multijugador | No | No | No |

**Criterio de recorte (vertical slice):** Solo entra lo que prueba el **pilar 1** ante playtest e inversionista. El bioma más “vistoso” pero sin ramas de dilema queda fuera.

**Criterio de recorte (MVP):** ADR 002 — un vinculado con profundidad (Thai); segunda especie pospuesta salvo fallo de comprensión en playtest.

---

## Riesgos de diseño (diseño, no producción)

| Riesgo | Validación temprana |
|--------|---------------------|
| Dilemas percibidos como cosméticos | Telemetría de playtest: % jugadores que notan cambio físico post-decisión |
| Thai percibido como mascota irrelevante | Prototype semana 6: nivel sin eco vs con eco |
| Sobrecarga de flags | Vertical slice: máximo 8 flags activos |

---

## Historia (opcional breve)

Protagonista llega al **Umbral**, limbo entre decisiones no resueltas. Thai es el primer vinculado que “ancla” al personaje a la realidad mutable. Tono: melancolía ligera, no horror.

---

*Referencias de diseño en carta operativa y ADR en `/decisiones/`.*
