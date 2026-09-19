# Diagnóstico — Patrón de fallo (Anexo A · ACA 2)

## Patrón elegido: **6 · La decisión que nadie recuerda**

| Campo (Anexo A) | Descripción aplicada a Taller Umbral |
|-----------------|----------------------------------------|
| Cómo se ve | Se acuerda en conversación quién hace qué y con qué criterio; se avanza el entregable; semanas después **no hay registro** del criterio ni de las opciones descartadas, y el equipo **reconstruye** o **mezcla** material propio con evidencia externa. |
| Qué produce | Se paga dos veces la misma conversación; aumenta el riesgo de contradicciones entre documentos; quien llega tarde no sabe qué fue decisión deliberada. |
| Por qué cuesta verlo | Mientras hay entrega a tiempo, parece eficiencia; escribir un ADR cuesta ~20 minutos; el costo es futuro y difuso. |

**Por qué este patrón y no otro:** Es el que mejor explica **nuestro** proceso en el curso (evidencia abajo), no un escenario hipotético. No elegimos el patrón por gravedad abstracta en la industria, sino porque tenemos hechos observables de cómo trabajamos en ACA 1 y al retomar ACA 2.

---

## 1. Evidencia hacia adentro (proceso del equipo en el curso)

Hechos observables. Un tercero puede contrastarlos con entregas en C Digital, retroalimentación del docente y este repositorio.

### 1.1 Pieza faltante en la consigna y decisión de método no declarada por escrito

El facilitador indicó que en C Digital **no se publicó** el documento completo del ACA 1: solo la guía de entrega y el encabezado. **No estaban disponibles** el Anexo A con los dos casos, el formato RAE ni la rúbrica (Ordóñez-Bolaños, retroalimentación ACA 1, 2026).

El equipo **improvisó** el Documento 1 derivando dos casos de Telltale en lugar de entregar en blanco o un relleno genérico. La calificación reconoce esa improvisación (C2 · 4,5), pero señala explícitamente que **en ninguna parte declararon el supuesto**: no aparece una frase del tipo *«no tuvimos acceso al Anexo A; construimos dos casos con estos criterios»*.

**Problema visible:** entrega completa a tiempo.  
**Problema estructural (patrón 6):** la decisión de método (cómo sustituir el Anexo A) **no quedó archivada** con criterio y fecha; meses después, en la autopsia, esa decisión **no es recuperable** por un lector externo como decisión nombrada.

### 1.2 Salida tardía de integrante y reparto sin registro de «entregado»

Faltando poco para el cierre del ACA 1, una integrante **dejó el equipo**. Según la consigna original, su parte correspondía a la **apertura inicial** que debía encadenar el resto de documentos del compendio.

Al retomar el trabajo quedaron **dos personas** (Jonnathan Martínez y Manuel Alejandro Domínguez Guerrero). Hubo **tensión** por reconstruir esa apertura a muy poco plazo de la entrega; por timing se consideró poco responsable escalar al docente a un día del cierre. El reparto efectivo fue:

- Jonnathan: parte inicial / encadenamiento y Documento 1 (dos casos).
- Tras acordar el caso Telltale, Manuel: continuidad del Documento 2 (autopsia).
- Documento 3 (anexos RAE, ficha, IA): **en conjunto**.

**No existe** en ACA 1 un acta, ADR o issue con: opciones consideradas de reparto, definición de qué contaba como «listo para que el otro continúe», ni desacuerdo registrado sobre quién asumía la apertura.

### 1.3 Borrón entre material propio y evidencia externa (feedback C3)

La retroalimentación documenta consecuencias típicas del patrón 6 cuando no hay frontera escrita:

- **Tensión 1:** la fuente declarada es el Documento 1, escrito por el mismo equipo; un externo no puede verificar allí hechos de Telltale.
- Un hito **viernes → lunes** nace del diálogo SBI (ejercicio de rol en Documento 1) y reaparece en Documento 2 como retraso documentado del estudio histórico.
- **Tensión 2:** se atribuyen al Documento 1 alegaciones de demanda colectiva que ese documento no contiene.
- **Tensión 3:** se citan informes financieros internos que el propio Documento 2 declara no haber visto.

El docente lo formula como riesgo estructural cuando casos improvisados y autopsia comparten el mismo caso sin etiquetado. **Neutralización que aplicamos en ACA 2:** ADR obligatorios + etiqueta *Material propio* vs *Evidencia externa* (ver `CONTRIBUTING.md` y antídoto en carta operativa).

### 1.4 Contradicción metodológica no cerrada por escrito

En Documento 2 se descartan explícitamente los estilos de liderazgo transaccional/transformacional como eje autónomo (limitación de fuentes), pero la Tensión 1 se califica usando transaccional vs transformacional (Megheirkouni, 2018). El docente pide **quedarse con una sola posición**; esa corrección **no quedó registrada** como decisión posterior en un documento trazable antes del ACA 2.

---

## 2. Evidencia hacia afuera (caso público · APA 7)

**Hecho observable (externo):** Tras el anuncio de reestructuración de **noviembre de 2017**, Telltale comunicó públicamente orientarse a **menos juegos y mayor calidad** con una plantilla reducida; en los meses siguientes, reportajes de investigación documentan **múltiples producciones simultáneas**, presión de calendario episódico y deterioro laboral **sin** que esa declaración estratégica se tradujera en un cambio verificable y estable de alcance (Favis, 2019).

**Fuente verificable:**

Favis, E. (2019, April 9). *The rise and fall of Telltale Games*. Game Informer. https://www.gameinformer.com/feature/2019/04/09/the-rise-and-fall-of-telltale-games

**Alcance:** Periodo 2017–2018; plantilla ~25% reducida en 2017 y cierre mayoritario en septiembre de 2018 (contexto ampliado en cobertura de prensa del mismo periodo).

**Por qué ilustra el patrón 6 (y no solo “mala gestión”):** Un observador externo puede leer la **decisión comunicada** en 2017 y contrastarla con el **patrón de ejecución** posterior en fuentes periodísticas, sin acceso a minutas internas. La brecha sugiere que la decisión estratégica **no quedó anclada** en mecanismos que sobrevivan al día a día (lo que en Taller Umbral resolvemos con ADR + definición de hecho).

**Límite:** No afirmamos intención psicológica de directivos; solo el contraste **público** entre declaración y hechos reportados.

---

## 3. Puente al diseño (insumo de «El antídoto»)

Si el patrón 6 ocurrió en ACA 1 **sin repositorio de decisiones**, en Taller Umbral el mecanismo será:

- Ningún cambio de alcance MVP/vertical slice sin ADR *Aceptada* en `decisiones/`.
- Campos obligatorios *Opciones consideradas* y *Desacuerdo registrado* (Anexo B ACA 2).
- Indicador auditable externamente (detalle en `estudio/carta-operativa.pdf`, sección «El antídoto»).

---

## Referencias (diagnóstico)

Favis, E. (2019, April 9). *The rise and fall of Telltale Games*. Game Informer. https://www.gameinformer.com/feature/2019/04/09/the-rise-and-fall-of-telltale-games

Ordóñez-Bolaños, O. A. (2026). Retroalimentación ACA 1 — equipo Telltale (C Digital / comunicación docente).
