# 🏛️ SIGPRECO — Sistema Integral de Gestión Presupuestal

> Proyecto académico ADSO — SENA  
> Sistema orientado a la administración presupuestal, gestión de contratos y control institucional mediante una interfaz web responsive y accesible.

Este proyecto fue desarrollado como adaptación práctica de las evidencias GA5 del programa ADSO, utilizando:

- HTML semántico
- CSS responsive (mobile-first)
- Dashboard administrativo
- Accesibilidad web (WCAG 2.1 AA)
- Git y GitHub para control de versiones

---

# 🚀 ¿Qué es SIGPRECO?

SIGPRECO es un sistema administrativo diseñado para apoyar procesos institucionales relacionados con:

- 📄 Gestión de CDP
- 📑 Administración contractual
- 📈 Reportes institucionales
- 👥 Gestión de usuarios
- ⚙️ Configuración del sistema
- 🛠️ Soporte y solicitudes internas

El sistema utiliza una arquitectura tipo dashboard con sidebar lateral y diseño adaptable para escritorio y dispositivos móviles.

---

# 🗂️ Estructura del proyecto

```text
SIGPRECO/
├── README.md
├── login.html
├── index.html
├── catalogo.html
├── detalle.html
├── contacto.html
├── css/
│   └── styles.css
├── docs/
│   ├── wireframes.md
│   ├── mapa-navegacion.md
│   ├── accesibilidad.md
│   └── guia-git.md
└── .github/
```

---

# 📄 Descripción de archivos

| Archivo              | Función                          |
| -------------------- | -------------------------------- |
| `login.html`         | Pantalla de inicio de sesión     |
| `index.html`         | Dashboard principal              |
| `catalogo.html`      | Panel de módulos administrativos |
| `detalle.html`       | Gestión de certificados CDP      |
| `contacto.html`      | Centro de soporte institucional  |
| `styles.css`         | Estilos responsive del sistema   |
| `wireframes.md`      | Wireframes Mermaid               |
| `mapa-navegacion.md` | Arquitectura de navegación       |
| `accesibilidad.md`   | Checklist WCAG y usabilidad      |

---

# 🎯 Conexión con evidencias GA5

| Evidencia | Descripción                   | Implementación            |
| --------- | ----------------------------- | ------------------------- |
| EV02      | Reglas de accesibilidad web   | `docs/accesibilidad.md`   |
| EV03      | Wireframes e interfaz gráfica | `docs/wireframes.md`      |
| EV04      | Maquetación HTML y CSS        | Archivos HTML + CSS       |
| EV05      | Mapa de navegación            | `docs/mapa-navegacion.md` |
| EV06      | Accesibilidad móvil           | Responsive + WCAG         |
| EV07      | Interfaz gráfica móvil        | Wireframes responsive     |

---

# 🖥️ Tecnologías utilizadas

- HTML5
- CSS3
- Flexbox
- CSS Grid
- Media Queries
- Mermaid
- Git
- GitHub

---

# ♿ Accesibilidad

El sistema aplica buenas prácticas de accesibilidad basadas en WCAG 2.1 nivel AA:

- ✅ HTML semántico
- ✅ Navegación por teclado
- ✅ Contraste de color adecuado
- ✅ Formularios accesibles
- ✅ Diseño responsive
- ✅ Sidebar adaptable
- ✅ Skip links
- ✅ Focus visible

---

# 📱 Responsive Design

El proyecto utiliza diseño mobile-first con adaptación progresiva:

| Dispositivo   | Diseño                     |
| ------------- | -------------------------- |
| 📱 Móvil      | Sidebar vertical adaptable |
| 📱 Tablet     | Grid responsive            |
| 💻 Escritorio | Dashboard completo         |

---

# 🌿 Control de versiones

El proyecto utiliza Git y GitHub para:

- seguimiento de cambios,
- commits organizados,
- práctica de ramas,
- control de versiones,
- trabajo colaborativo.

---

# 🧪 Cómo ejecutar el proyecto

## Opción 1 — Live Server (VSCode)

1. Abrir el proyecto en VSCode.
2. Instalar la extensión **Live Server**.
3. Click derecho → `Open with Live Server`.

---

## Opción 2 — Servidor local

```bash
python3 -m http.server 8000
```

o

```bash
php -S localhost:8000
```

Luego abrir:

```text
http://localhost:8000
```

---

# 📌 Flujo principal del sistema

```text
Login
↓
Dashboard
↓
Módulos administrativos
↓
Gestión institucional
```

---

# 📖 Objetivo académico

Este proyecto busca fortalecer competencias en:

- maquetación web,
- diseño responsive,
- accesibilidad,
- navegación semántica,
- estructura frontend,
- control de versiones con Git/GitHub.

---

# 👨‍💻 Proyecto ADSO — SENA

Proyecto desarrollado como práctica académica para el programa:

**Análisis y Desarrollo de Software (ADSO)**  
Servicio Nacional de Aprendizaje — SENA
