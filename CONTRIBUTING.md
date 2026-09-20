# Convenciones de trabajo — Taller Umbral / *Umbral*

**Motor:** Unity (C#). Las reglas de **assets y código** siguen convenciones **Unity + C#** (Microsoft).  
**Repositorio ACA:** markdown, PDFs, ADR — convenciones propias abajo.

Referencia ACA 2 (punto de partida, no destino): [Recommended Asset Naming Conventions — Unreal Engine](https://docs.unrealengine.com/5.0/en-US/recommended-asset-naming-conventions-in-unreal-engine-projects/).

---

## 1. Principio tomado de Unreal (referencia ACA 2)

| Idea Unreal | Cómo la aplicamos en Unity |
|-------------|----------------------------|
| Prefijo por **tipo de asset** para ordenar y buscar | **Carpetas + tipo implícito** (`Textures/`, `Prefabs/`, `Audio/`) y sufijos en texturas (`_Albedo`, `_Normal`) |
| Nombre estable + variante + índice | `Thai_Idle_04`, `Door_Umbral_01` |
| Separar material base vs instancia | Material base + Material Variant (Unity) en lugar de `M_` / `MI_` en el nombre del archivo |
| Un autor, un criterio | Este documento + revisión en PR del Producer |

---

## 2. Qué **no** importamos de Unreal (y por qué)

| Convención Unreal | Por qué no en *Umbral* (Unity + C#) |
|-------------------|-------------------------------------|
| `SM_` en meshes | En Unity el tipo ya figura en el import; el Project window filtra por carpeta. Prefijo `SM_` confunde a herramientas y paquetes Unity. |
| `SC_` en scripts C# | **C#:** el archivo debe coincidir con la clase (`BondProgression.cs` → `class BondProgression`). Prefijos en el nombre del archivo rompen convención .NET y el linter de Unity. |
| `BP_` / Blueprint | Equivalente Unity: **Prefab**, sin prefijo tipo Unreal; vive en `Assets/Prefabs/`. |
| Rutas `/Game/...` | Usamos estructura `Assets/` estándar (ver §3). |

---

## 3. Estructura de proyecto Unity (`Assets/`)

```
Assets/
├── _Project/                 # Scope del juego (evita mezclar con packages)
│   ├── Scenes/
│   ├── Prefabs/
│   │   └── Companions/
│   │       └── Thai.prefab
│   ├── Art/
│   │   ├── Sprites/Thai/
│   │   ├── Textures/
│   │   └── Materials/
│   ├── Audio/Thai/
│   └── Scripts/
│       ├── Companions/
│       ├── Narrative/
│       └── Core/
├── Settings/                 # URP/HDRP, Input Actions
└── Plugins/                  # Solo si aplica
```

**Escenas:** PascalCase descriptivo — `BosqueUmbral_VSlice.unity` (build settings documentadas en carta operativa).

---

## 4. Nomenclatura de assets (Unity)

| Tipo | Convención | Ejemplo | Notas |
|------|------------|---------|--------|
| **Script C#** | PascalCase; **nombre de archivo = nombre de clase** | `ThaiBondController.cs` | [Microsoft C# naming](https://learn.microsoft.com/en-us/dotnet/csharp/fundamentals/coding-style/identifier-names) |
| **Prefab** | PascalCase; carpeta indica categoría | `Prefabs/Companions/Thai.prefab` | Sin prefijo `PF_` |
| **Sprite** | `{Personaje}_{Accion}_{Frame}` | `Thai_Idle_04` | Atlases: `Thai_Atlas_UI` |
| **Texture** | `{Subject}_{Map}` | `Thai_Fur_Albedo`, `Thai_Fur_Normal` | Sufijos `_Albedo`, `_Normal`, `_Mask` (habitual Unity/URP) |
| **Material** | `{Subject}_{Uso}` | `Thai_Fur`, `Thai_Fur_Outline` | Variants desde el material base |
| **Audio** | `{Contexto}_{Evento}_{Variant}` | `Thai_Purr_Soft_01` | Carpetas por contexto (`UI/`, `Ambience/`) |
| **Animation clip** | `{Subject}_{Action}` | `Thai_Sit` | Controller: `Thai_Animator.controller` |
| **ScriptableObject** | `{Domain}{Purpose}` | `BondProgressionConfig.asset` | Datos de progresión de vínculos |

**Prohibido en código C#:** espacios en nombres de archivo, prefijos tipo `SC_`, abreviaturas crípticas en clases públicas.

---

## 5. Estilo C# (resumen)

- Clases, métodos, propiedades públicas: **PascalCase**.
- Campos privados serializados: `_camelCase` o `[SerializeField] private` según guía del equipo.
- Namespaces: `TallerUmbral.Companions`, `TallerUmbral.Narrative`.
- Un tipo principal por archivo.

*(Detalle de revisión en pipeline: carta operativa → Definition of Done.)*

---

## 6. Repositorio de documentación (este repo Git)

| Ruta | Convención |
|------|------------|
| `decisiones/` | `NNN-titulo-en-kebab-case.md` (ADR) |
| `gdd/`, `estudio/` | PDF finales en mayúsculas cortas: `GDD.pdf`, `carta-operativa.pdf` |
| Idioma | Español; referencias APA 7 en diagnóstico y carta |

---

## 7. Ramas Git

| Prefijo | Uso |
|---------|-----|
| `feat/` | Contenido nuevo |
| `fix/` | Coherencia alcance–cronograma–presupuesto |
| `docs/` | ADR, diagnóstico, README |

Ejemplo: `docs/adr-003-cadencia-sprint`.

---

## 8. Mensajes de commit

Formato: `tipo(alcance): descripción en imperativo`

| Tipo | Alcance | Ejemplo |
|------|---------|---------|
| `docs` | `diag`, `adr`, `gdd`, `estudio` | `docs(diag): evidencia interna patrón 6` |
| `feat` | `gdd` | `feat(gdd): diagrama core loop` |
| `fix` | `gdd` | `fix(gdd): alinear MVP con ADR 002` |

---

## 9. Definition of Done (documentación y alcance)

- Cambio de **alcance MVP / vertical slice** → ADR *Aceptada* en `decisiones/` + enlace en PR (plantilla `.github/pull_request_template.md`, ADR 004).
- Material de rol o hipotético del equipo → etiqueta **Material propio — no verificable externamente**.
- Assets Unity futuros → §3 y §4 de este archivo (no prefijos Unreal).
