# Wireframes — TechShop ADSO

> Bocetos de baja fidelidad de las 4 pantallas del sitio, en versión móvil y escritorio.
> Hechos en **Mermaid** para que cualquiera pueda editarlos sin software extra.

Conexión con evidencias:
- **GA5-EV03** (interfaz gráfica + mapa de navegación — web)
- **GA5-EV07** (interfaz gráfica + mapa de navegación — móvil)

---

## 1. Inicio (`index.html`)

### Móvil (≤ 599 px)

```mermaid
flowchart TB
  subgraph movil_inicio[" "]
    direction TB
    H1["🏷️ Logo · ☰ Menú"]
    HERO["🎯 HERO<br/>Título grande<br/>+ botón Ver catálogo"]
    DEST["⭐ Destacados<br/>(3 cards apiladas)"]
    VENT["✅ Ventajas<br/>(lista numerada)"]
    F1["📄 Footer<br/>© 2026 + enlaces"]

    H1 --> HERO
    HERO --> DEST
    DEST --> VENT
    VENT --> F1
  end
```

### Escritorio (≥ 900 px)

```mermaid
flowchart TB
  subgraph desktop_inicio[" "]
    direction TB
    H2["🏷️ Logo&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Inicio · Catálogo · Detalle · Contacto"]
    HERO2["🎯 HERO (ancho completo, columna izquierda)"]
    DEST2["⭐ Destacados (3 cards en fila)"]
    VENT2["✅ Ventajas (lista numerada)"]
    F2["📄 Footer (© izquierda · enlaces derecha)"]

    H2 --> HERO2
    HERO2 --> DEST2
    DEST2 --> VENT2
    VENT2 --> F2
  end
```

---

## 2. Catálogo (`catalogo.html`)

### Móvil

```mermaid
flowchart TB
  H["🏷️ Header"]
  T["📑 Título: Catálogo completo"]
  ASIDE["🔧 Filtros (1 select)"]
  G1["🃏 Card 1"]
  G2["🃏 Card 2"]
  G3["🃏 Card 3"]
  G4["🃏 Card 4"]
  G5["🃏 Card 5"]
  G6["🃏 Card 6"]
  F["📄 Footer"]

  H --> T --> ASIDE --> G1 --> G2 --> G3 --> G4 --> G5 --> G6 --> F
```

### Escritorio

```mermaid
flowchart TB
  H["🏷️ Header (logo + nav horizontal)"]
  T["📑 Título: Catálogo completo"]
  ASIDE["🔧 Filtros"]
  subgraph fila1["Grid 3 columnas"]
    direction LR
    G1["🃏 Card 1"]
    G2["🃏 Card 2"]
    G3["🃏 Card 3"]
  end
  subgraph fila2[" "]
    direction LR
    G4["🃏 Card 4"]
    G5["🃏 Card 5"]
    G6["🃏 Card 6"]
  end
  F["📄 Footer"]

  H --> T --> ASIDE --> fila1 --> fila2 --> F
```

---

## 3. Detalle de producto (`detalle.html`)

### Móvil

```mermaid
flowchart TB
  H["🏷️ Header"]
  B["🍞 Migas de pan"]
  IMG["🖼️ Imagen grande"]
  TITLE["📝 Título + precio"]
  DESC["📄 Descripción"]
  CARAC["📋 Características (lista numerada)"]
  ESPEC["⚙️ Especificaciones (lista numerada)"]
  CTA["🟦 Botón 'Solicitar info'"]
  REL["🔁 Productos relacionados (cards apiladas)"]
  F["📄 Footer"]

  H --> B --> IMG --> TITLE --> DESC --> CARAC --> ESPEC --> CTA --> REL --> F
```

### Escritorio

```mermaid
flowchart TB
  H["🏷️ Header"]
  B["🍞 Migas de pan"]
  subgraph cuerpo["2 columnas"]
    direction LR
    IMG["🖼️ Imagen<br/>(columna izquierda)"]
    INFO["📝 Título + precio<br/>📄 Descripción<br/>📋 Características<br/>⚙️ Especificaciones<br/>🟦 CTA<br/>(columna derecha)"]
  end
  REL["🔁 Relacionados (grid horizontal)"]
  F["📄 Footer"]

  H --> B --> cuerpo --> REL --> F
```

---

## 4. Contacto (`contacto.html`)

### Móvil

```mermaid
flowchart TB
  H["🏷️ Header"]
  T["📞 Título: Contáctanos"]
  P["📝 Intro corta"]
  FS1["📦 Fieldset: Datos de contacto<br/>· Nombre<br/>· Email<br/>· Teléfono (opcional)"]
  FS2["📦 Fieldset: Tu mensaje<br/>· Asunto (select)<br/>· Mensaje (textarea)<br/>· ☑ Acepto política"]
  BTN["🟦 Enviar · ⬜ Limpiar"]
  F["📄 Footer"]

  H --> T --> P --> FS1 --> FS2 --> BTN --> F
```

### Escritorio

Mismo flujo pero el formulario tiene `max-width: 500px` y queda centrado en la columna principal. No cambia la estructura — solo el ancho.

---

## Convenciones del wireframe

| Símbolo | Significado |
|---|---|
| 🏷️ | Cabecera con logo + nav |
| 🎯 | Sección hero (llamado de atención) |
| ⭐ | Destacados |
| 🃏 | Card individual de producto |
| 🔧 | Filtros / aside |
| 🍞 | Breadcrumb / migas de pan |
| 📦 | Fieldset de formulario |
| 🟦 | Botón primario |
| ⬜ | Botón secundario |
| 📄 | Footer |

## Notas para EV04 (maquetación HTML)

Cada bloque del wireframe corresponde a un elemento semántico:
- 🏷️ → `<header>` con `<nav>`
- 🎯 / ⭐ / ✅ → `<section>` con `<h2>` propio
- 🃏 → `<article>` dentro de un `<li>` del `<ul class="product-grid">`
- 🔧 → `<aside>`
- 📦 → `<fieldset>` con `<legend>`
- 📄 → `<footer>`
