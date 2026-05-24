# Mapa de navegación — SIGPRECO

> Diagrama jerárquico de navegación del sistema SIGPRECO.
> Sistema orientado a la gestión presupuestal y administrativa institucional.
> Elaborado en **Mermaid** para las evidencias EV05 y EV07.

Conexión con evidencias:

- **GA5-EV05** — mapa de navegación web
- **GA5-EV07** — navegación responsive y móvil

---

# Mapa principal del sistema

```mermaid
flowchart TD

  LOGIN[("🔐 Login<br/>login.html")]

  LOGIN --> DASHBOARD["📊 Dashboard<br/>index.html"]

  DASHBOARD --> MODULOS["📁 Módulos<br/>catalogo.html"]

  DASHBOARD --> SOPORTE["🛠️ Soporte<br/>contacto.html"]

  MODULOS --> CDP["📄 Gestión CDP<br/>detalle.html"]

  MODULOS --> CONTRATOS["📑 Contratos"]

  MODULOS --> REPORTES["📈 Reportes"]

  MODULOS --> USUARIOS["👥 Usuarios"]

  MODULOS --> CONFIG["⚙️ Configuración"]

  CDP --> HISTORIAL["🕘 Historial presupuestal"]

  SOPORTE --> DASHBOARD

  classDef principal fill:#1E3A8A,stroke:#162C6B,color:#fff,font-weight:bold
  classDef secundaria fill:#E5E7EB,stroke:#D1D5DB,color:#1F2937
  classDef accion fill:#162C6B,stroke:#0F172A,color:#fff

  class LOGIN,DASHBOARD principal
  class MODULOS,CDP,SOPORTE secundaria
  class CONTRATOS,REPORTES,USUARIOS,CONFIG,HISTORIAL accion
```

---

# Niveles jerárquicos

```mermaid
flowchart TB

  N0["NIVEL 0 — Acceso al sistema"]

  N1["NIVEL 1 — Panel principal"]

  N2["NIVEL 2 — Módulos administrativos"]

  N3["NIVEL 3 — Funciones internas"]

  N0 --- LOGIN["🔐 Login"]

  N1 --- DASH["📊 Dashboard"]

  N2 --- MOD["📁 Módulos"]
  N2 --- SOP["🛠️ Soporte"]

  N3 --- CDP["📄 Gestión CDP"]
  N3 --- CON["📑 Contratos"]
  N3 --- REP["📈 Reportes"]
  N3 --- USR["👥 Usuarios"]
  N3 --- CFG["⚙️ Configuración"]

  LOGIN --> DASH
  DASH --> MOD
  DASH --> SOP

  MOD --> CDP
  MOD --> CON
  MOD --> REP
  MOD --> USR
  MOD --> CFG

  style N0 fill:none,stroke:none,font-weight:bold
  style N1 fill:none,stroke:none,font-weight:bold
  style N2 fill:none,stroke:none,font-weight:bold
  style N3 fill:none,stroke:none,font-weight:bold
```

---

# Mapa de navegación — versión móvil

En dispositivos móviles el sistema adapta el sidebar lateral a una navegación vertical optimizada para pantallas pequeñas, manteniendo accesibilidad y navegación responsive.

```mermaid
flowchart TD

  MOBILE["📱 Vista móvil<br/>SIGPRECO"]

  MOBILE --> MENU{{"☰ Sidebar móvil"}}

  MENU --> DASH_M["📊 Dashboard"]

  MENU --> MOD_M["📁 Módulos"]

  MENU --> CDP_M["📄 Gestión CDP"]

  MENU --> SOP_M["🛠️ Soporte"]

  MENU --> REP_M["📈 Reportes"]

  MENU --> USR_M["👥 Usuarios"]

  DASH_M --> MOD_M

  MOD_M --> CDP_M

  CDP_M --> SOP_M

  classDef mobile fill:#1E3A8A,stroke:#162C6B,color:#fff

  class MOBILE,MENU mobile
```

---

# Diferencias clave móvil vs escritorio

| Elemento        | Móvil                      | Escritorio                    |
| --------------- | -------------------------- | ----------------------------- |
| Navegación      | Sidebar vertical adaptable | Sidebar lateral fijo          |
| Dashboard       | Cards en 1 columna         | Cards en múltiples columnas   |
| Formularios     | Diseño apilado             | Distribución más amplia       |
| Layout          | Flujo vertical             | Layout dividido               |
| Acceso módulos  | Scroll vertical            | Navegación lateral permanente |
| Panel principal | Compacto                   | Expandido                     |

---

# Convenciones del mapa

- **Nodo redondeado** `(("..."))` → acceso principal del sistema
- **Nodo rectangular** `["..."]` → módulos y páginas internas
- **Nodo hexagonal** `{{"..."}}` → componente desplegable o navegación móvil
- **Flecha sólida** `-->` → navegación principal
- **Color azul oscuro** → páginas principales del sistema
- **Color gris** → módulos secundarios
- **Color azul intenso** → acciones y funcionalidades internas
