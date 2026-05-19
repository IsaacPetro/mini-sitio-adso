# Mapa de navegación — TechShop ADSO

> Diagrama jerárquico de cómo se conectan las páginas del sitio.
> Hecho en **Mermaid** — listo para entregar como EV05 (mapa web) y EV07 (mapa móvil).

Conexión con evidencias:
- **GA5-EV05** — mapa de navegación (web)
- **GA5-EV07** — interfaz gráfica + mapa de navegación móvil

---

## Mapa principal del sitio

```mermaid
flowchart TD
  HOME[("🏠 Inicio<br/>index.html")]

  HOME --> CATALOGO["📋 Catálogo<br/>catalogo.html"]
  HOME --> DESTACADO["⭐ Producto destacado<br/>(desde hero)<br/>detalle.html"]
  HOME --> CONTACTO["✉️ Contacto<br/>contacto.html"]

  CATALOGO --> DETALLE["🛒 Detalle producto<br/>detalle.html"]
  CATALOGO -.->|filtro categoría| CATALOGO

  DETALLE --> RELACIONADO["🔁 Producto relacionado<br/>detalle.html"]
  DETALLE --> CONTACTO

  CONTACTO -->|envío exitoso| HOME

  classDef principal fill:#0052cc,stroke:#003d99,color:#fff,font-weight:bold
  classDef secundaria fill:#f5f5f5,stroke:#d6d6d6,color:#1a1a1a
  classDef accion fill:#d63a1f,stroke:#b8311a,color:#fff

  class HOME principal
  class CATALOGO,DETALLE,CONTACTO secundaria
  class DESTACADO,RELACIONADO,CONTACTO accion
```

---

## Niveles jerárquicos

```mermaid
flowchart TB
  N0["NIVEL 0 — Página de aterrizaje"]
  N1["NIVEL 1 — Secciones principales"]
  N2["NIVEL 2 — Páginas internas"]

  N0 --- HOME[("🏠 Inicio")]

  N1 --- CAT["📋 Catálogo"]
  N1 --- CON["✉️ Contacto"]

  N2 --- DET["🛒 Detalle de producto"]

  HOME --> CAT
  HOME --> CON
  CAT --> DET

  style N0 fill:none,stroke:none,font-weight:bold
  style N1 fill:none,stroke:none,font-weight:bold
  style N2 fill:none,stroke:none,font-weight:bold
```

---

## Mapa de navegación — versión móvil

En móvil la navegación principal **colapsa en un menú `<details>`** que se despliega al tocar "Menú". Las relaciones entre páginas son las mismas, solo cambia el acceso visual al menú.

```mermaid
flowchart TD
  MOBILE["📱 Header móvil<br/>Logo + botón ☰ Menú"]

  MOBILE -->|tap en ☰| MENU{{"📋 Menú desplegado<br/>(details abierto)"}}

  MENU --> HOME_M["🏠 Inicio"]
  MENU --> CAT_M["📋 Catálogo"]
  MENU --> DET_M["🛒 Detalle"]
  MENU --> CON_M["✉️ Contacto"]

  HOME_M -.->|scroll| HERO_M["Hero · CTA Ver catálogo"]
  HERO_M --> CAT_M

  CAT_M --> CARD_M["Card de producto"]
  CARD_M --> DET_M

  DET_M --> CTA_M["CTA Solicitar info"]
  CTA_M --> CON_M

  classDef mobile fill:#0052cc,stroke:#003d99,color:#fff
  class MOBILE,MENU mobile
```

### Diferencias clave móvil vs escritorio

| Elemento | Móvil | Escritorio |
|---|---|---|
| Nav | `<details>` desplegable | Horizontal siempre visible |
| Grid de productos | 1 columna | 3 columnas |
| Detalle | 1 columna (imagen arriba, info abajo) | 2 columnas (imagen ⟷ info) |
| Footer | Apilado vertical | Logo izquierda + enlaces derecha |
| CTA primario | Ancho completo | Ancho según contenido |

---

## Convenciones del mapa

- **Nodo redondeado** `(("..."))` → página de aterrizaje (home)
- **Nodo rectangular** `["..."]` → página interna
- **Nodo hexagonal** `{{"..."}}` → menú o componente desplegable
- **Flecha sólida** `-->` → enlace de navegación normal
- **Flecha punteada** `-.->` → navegación condicional o filtro
- **Color azul** → página principal (home)
- **Color gris** → páginas secundarias
- **Color naranja** → acciones / CTA
