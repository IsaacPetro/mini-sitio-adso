# 🛒 TechShop ADSO — Mini-sitio + práctica Git/GitHub

> Repo de práctica para **fichas 3235898 / 3235899** — ADSO 228118 (SENA).
> Mini-sitio completo en **HTML semántico + CSS mobile-first**, diseñado para servir simultáneamente como:
>
> 1. 📚 **Ejemplo de referencia** para las evidencias EV04/EV05/EV06/EV07 de GA5 (cierran 24/05).
> 2. 🌿 **Patio de juegos Git/GitHub** antes de aplicarlo al proyecto formativo real (GA6 en adelante).
> 3. 🔧 **Referencia técnica** para GA6-AA4 (front-end HTML/CSS/JS, junio).

---

## 🗺️ ¿Qué hay en este repo?

```
mini-sitio-adso/
├── README.md                   ← este archivo
├── index.html                  ← página de aterrizaje (hero + destacados + ventajas)
├── catalogo.html               ← grid de 6 productos + filtro
├── detalle.html                ← producto individual + relacionados
├── contacto.html               ← formulario accesible con fieldsets
├── css/
│   └── styles.css              ← mobile-first, variables CSS, media queries
├── docs/
│   ├── wireframes.md           ← bocetos Mermaid (EV03/EV07)
│   ├── mapa-navegacion.md      ← mapa jerárquico Mermaid (EV05/EV07)
│   ├── accesibilidad.md        ← checklist WCAG 2.1 AA (EV02/EV06)
│   └── guia-git.md             ← guía Git/GitHub en 3 niveles progresivos
└── .github/
    ├── pull_request_template.md
    └── ISSUE_TEMPLATE/
```

---

## 🚀 Cómo verlo

### Opción 1 — Doble clic

Abre `index.html` con tu navegador. Listo.

### Opción 2 — Servidor local (recomendado)

```bash
# Con Python 3 (viene en macOS y la mayoría de Linux)
python3 -m http.server 8000

# Con Node
npx serve .

# Con PHP
php -S localhost:8000
```

Luego abre <http://localhost:8000>.

---

## 🎯 Conexión con las evidencias de GA5 (cierran 24/05/2026)

| Evidencia | Qué pide | Dónde está en este repo |
|---|---|---|
| **EV02** — Reglas de usabilidad y accesibilidad (web) | Checklist de reglas aplicadas en escritorio | [`docs/accesibilidad.md`](docs/accesibilidad.md) (secciones 1–9) |
| **EV03** — Interfaz gráfica + mapa de navegación (web) | Wireframes y mapa de la web en escritorio | [`docs/wireframes.md`](docs/wireframes.md) + [`docs/mapa-navegacion.md`](docs/mapa-navegacion.md) |
| **EV04** — Maquetación HTML | HTML semántico de las pantallas diseñadas | `index.html`, `catalogo.html`, `detalle.html`, `contacto.html` + `css/styles.css` |
| **EV05** — Mapa de navegación | Mapa jerárquico web | [`docs/mapa-navegacion.md`](docs/mapa-navegacion.md) |
| **EV06** — Reglas de usabilidad y accesibilidad (móvil) | Reglas extra que aplican en móvil | [`docs/accesibilidad.md`](docs/accesibilidad.md) (sección "Reglas específicas para móvil") |
| **EV07** — Interfaz gráfica + mapa de navegación móvil | Wireframes y mapa de la versión móvil | [`docs/wireframes.md`](docs/wireframes.md) (sección "Móvil") + [`docs/mapa-navegacion.md`](docs/mapa-navegacion.md) (sección "móvil") |

> ⚠️ **Importante:** este repo es **referencia**, no plantilla para copiar literalmente. Tu entrega debe estar basada en **tu** proyecto formativo, no en una tienda de tecnología. Aquí ves *cómo se estructura*, no *qué entregar*.

---

## 🌿 Práctica Git/GitHub — 3 niveles

Lee la guía completa en [`docs/guia-git.md`](docs/guia-git.md).

| Nivel | Cuándo | Qué practicas |
|---|---|---|
| 🟢 **Nivel 1** | Semana 1 (25–31/05) | `clone`, `status`, `log`, `branch`, `checkout` |
| 🟡 **Nivel 2** | Semana 2 (01–07/06) | Editar, `add`, `commit`, `push`, abrir PR |
| 🔴 **Nivel 3** | Semana 3 (08–14/06) | Conflictos, code review, `rebase`, colaboración |

### Ramas TODO para practicar Nivel 2

El repo trae varias ramas con tareas pendientes — escoge una, complétala en tu fork, abre PR:

| Rama | TODO |
|---|---|
| `feature/pagina-faq` | Crear `faq.html` con 5 preguntas frecuentes usando `<details>` |
| `feature/footer-redes` | Agregar links a redes sociales en el footer (lista `<ul>`) |
| `feature/mejorar-a11y-formulario` | Mejorar mensajes de error accesibles en `contacto.html` |
| `feature/dark-mode-toggle` | Botón para alternar modo claro/oscuro manualmente |
| `feature/producto-nuevo` | Agregar un 7° producto al `catalogo.html` |

Cada rama tiene comentarios `<!-- TODO: ... -->` en los archivos donde toca trabajar.

---

## ♿ Accesibilidad

Este sitio cumple **WCAG 2.1 nivel AA**. Lo más importante:

- ✅ HTML semántico con landmarks (`<header>`, `<nav>`, `<main>`, `<aside>`, `<footer>`)
- ✅ Skip link al contenido principal
- ✅ Foco visible al navegar con teclado (`:focus-visible`)
- ✅ Contraste de color ≥ 4.5:1 en todo el texto
- ✅ `alt` descriptivo en todas las imágenes
- ✅ Formularios con `<label>`, `<fieldset>`, `<legend>`, `autocomplete`, `aria-required`
- ✅ Targets táctiles ≥ 44 px
- ✅ Respeta `prefers-reduced-motion` y `prefers-color-scheme`
- ✅ Una sola columna en móvil, sin scroll horizontal

Auditar con [Lighthouse](https://developer.chrome.com/docs/lighthouse/) (Chrome DevTools → Lighthouse → Accessibility).

---

## 📱 Responsive

| Breakpoint | Ancho | Cambios |
|---|---|---|
| 📱 Móvil (base) | < 600 px | 1 columna, menú colapsado en `<details>` |
| 📱 Tablet | ≥ 600 px | 2 columnas en grid, hero más amplio |
| 💻 Escritorio | ≥ 900 px | 3 columnas en grid, nav horizontal |

Probarlo con Chrome DevTools → Device Toolbar (⌘+⇧+M).

---

## 📖 Conexión con GA6

Este repo es el "calentamiento" antes de empezar GA6 (25/05). En GA6 vas a:

- **AA1–AA2** (25/05–14/06): construir el **modelo de base de datos** del proyecto formativo.
- **AA3–AA4** (13/06–05/07): construir la **interfaz gráfica + front-end** — y todo este mini-sitio te sirve como referencia técnica directa.

Y todo eso lo vas a versionar con Git/GitHub — donde lo que practiques en este repo ya lo tendrás dominado.

---

## ✉️ Contacto

**Instructor:** olcaicedo@sena.edu.co
**Foros Zajuna:** ficha 3235898 / 3235899
**Sesión sincrónica miércoles 7:30 PM** (Teams)
