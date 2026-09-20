# Core loop — *Umbral*

Exportar diagrama a `core-loop.png` para el PDF del GDD (captura desde visor Mermaid o Figma).

```mermaid
flowchart LR
  subgraph session["Bucle de sesión (~15 min)"]
    A[Explorar 2,5D] --> B[Detectar tensión]
    B --> C[Dilema 2–3 opciones]
    C --> D[Estado del mundo cambia]
    D --> E[Thai: eco / pista]
    E --> F[Checkpoint]
  end
  subgraph meta["Metajuego MVP"]
    F --> G[Afinidad Thai]
    G --> H[Rasgo / habilidad]
    H --> A
  end
```

**Alimentación entre bucles:** la afinidad de Thai modifica qué ecos están disponibles en la siguiente sesión (progresión de vínculo, ADR 002).
