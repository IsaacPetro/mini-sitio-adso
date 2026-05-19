# Checklist de usabilidad y accesibilidad

> Reglas que aplicamos en este mini-sitio y cómo se entregan como evidencia.

Conexión con evidencias:
- **GA5-EV02** — reglas de usabilidad y accesibilidad (escritorio)
- **GA5-EV06** — reglas de usabilidad y accesibilidad (móvil)

Estándar de referencia: [WCAG 2.1 nivel AA](https://www.w3.org/WAI/WCAG21/quickref/).

---

## 1. Estructura semántica (WCAG 1.3.1)

| Regla | ✅ Cómo lo aplicamos |
|---|---|
| Una sola `<h1>` por página | Cada página empieza con un `<h1>` único |
| Jerarquía sin saltos (`h1` → `h2` → `h3`) | No saltamos de `<h1>` a `<h3>` |
| Landmarks ARIA implícitos | Usamos `<header>`, `<nav>`, `<main>`, `<aside>`, `<footer>` |
| `<main>` con id `contenido` | Permite que el "skip link" salte ahí |
| Listas reales para listas | `<ol>` para pasos numerados, `<ul>` para items sin orden |
| Productos como `<article>` | Cada card es un artículo independiente |

## 2. Navegación por teclado (WCAG 2.1.1, 2.4.7)

- ✅ **Skip link**: `<a href="#contenido" class="skip-link">` aparece al hacer Tab.
- ✅ **`:focus-visible`** con un anillo de 3 px azul — siempre se ve dónde está el foco.
- ✅ **Orden lógico**: el orden del DOM coincide con el orden visual.
- ✅ **`<details>` para el menú**: nativamente accesible con teclado (Enter, Space).
- ✅ **Sin "trampas de foco"**: no hay modales sin escape.

**Cómo probarlo:** abre el sitio, presiona `Tab` repetidamente. Cada elemento interactivo debe recibir un anillo visible.

## 3. Contraste de color (WCAG 1.4.3)

| Elemento | Foreground | Background | Ratio | Cumple AA |
|---|---|---|---|---|
| Texto base | `#1a1a1a` | `#ffffff` | 16.1:1 | ✅ |
| Texto muted | `#595959` | `#ffffff` | 7.0:1 | ✅ |
| Enlace primario | `#0052cc` | `#ffffff` | 7.3:1 | ✅ |
| Botón primario | `#ffffff` | `#0052cc` | 7.3:1 | ✅ |
| Botón accent (hero) | `#ffffff` | `#d63a1f` | 4.7:1 | ✅ |

**Verificar:** [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/).

## 4. Imágenes (WCAG 1.1.1)

- ✅ **Todas las `<img>` tienen `alt`** descriptivo (no "imagen", no nombre del archivo).
- ✅ Para imágenes decorativas usamos `alt=""` (no aplica en este sitio porque todas comunican).
- ✅ `<img>` con `aspect-ratio` reservado vía CSS — no hay "salto" cuando carga la imagen.

Ejemplo de `alt` bueno y malo:

```html
<!-- ❌ Mal: no describe -->
<img src="auriculares.jpg" alt="imagen">

<!-- ✅ Bien: describe lo relevante -->
<img src="auriculares.jpg" alt="Audífonos inalámbricos Pro vista frontal, color negro mate">
```

## 5. Formularios (WCAG 1.3.5, 3.3.1, 3.3.2)

- ✅ **Todo `<input>` tiene `<label>`** asociado con `for`/`id` — clic en el label enfoca el campo.
- ✅ **`autocomplete`** correcto en cada campo (`name`, `email`, `tel`).
- ✅ **`aria-required="true"`** + asterisco visual en campos obligatorios.
- ✅ **Mensajes de error**: usamos `:invalid:not(:placeholder-shown)` para no mostrar error antes de tiempo.
- ✅ **`<fieldset>` + `<legend>`** para agrupar campos relacionados.
- ✅ **`type="email"`, `type="tel"`**: en móvil sale el teclado correcto.

## 6. Tamaños táctiles (WCAG 2.5.5 — AAA, pero lo aplicamos)

Todos los botones y inputs tienen `min-height: 44px` para que sean fáciles de tocar en pantalla táctil.

## 7. Idioma (WCAG 3.1.1)

```html
<html lang="es">
```

Esencial para lectores de pantalla — eligen la voz y la pronunciación correctas.

## 8. Responsive — sin scroll horizontal (WCAG 1.4.10)

- ✅ `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
- ✅ `img { max-width: 100%; height: auto; }`
- ✅ Grid colapsa de 3 → 2 → 1 columnas según ancho.
- ✅ Tipografía con `max-width: 65ch` para que ninguna línea sea muy larga.

## 9. Preferencias del usuario (WCAG 2.3.3)

- ✅ **`prefers-reduced-motion`**: si el usuario desactivó animaciones del sistema, no le animamos nada.
- ✅ **`prefers-color-scheme: dark`**: el sitio se adapta a modo oscuro automáticamente.

## 10. Estructura del HTML válida

- ✅ DOCTYPE HTML5 (`<!DOCTYPE html>`).
- ✅ `<meta charset="UTF-8">`.
- ✅ `<title>` único y descriptivo por página.

---

## Reglas específicas para móvil (EV06)

Las anteriores aplican, más estas extra del **mobile-first**:

1. **Viewport meta tag** — sin él, el navegador móvil renderiza como si fuera desktop.
2. **Tamaños táctiles 44 × 44 px mínimo** — Apple HIG / Google Material.
3. **Menú colapsado** — el `<details>` nativo es accesible sin JavaScript.
4. **Sin hover-only** — todo lo que se hace al pasar el mouse también debe funcionar al tocar.
5. **Imágenes optimizadas** — `aspect-ratio` evita "saltos" cuando cargan.
6. **Tipografía mínima de 16px** — debajo de eso, iOS hace zoom automático en inputs.
7. **Una columna por defecto** — el grid arranca en `1fr` y crece con media queries.

---

## Cómo entregar como evidencia

Esta tabla más los siguientes archivos del repo conforman la evidencia:

- `docs/accesibilidad.md` (este archivo) — el checklist.
- `index.html`, `catalogo.html`, `detalle.html`, `contacto.html` — implementación.
- `css/styles.css` — los media queries, las variables de contraste, los focus rings.
- Capturas de pantalla móvil y escritorio (las generan los aprendices con DevTools).

### Herramientas recomendadas para auditar

1. **Lighthouse** (Chrome DevTools → Lighthouse → Accessibility) — meta: ≥ 95.
2. **axe DevTools** (extensión de Chrome) — detecta problemas concretos.
3. **WebAIM Contrast Checker** — para verificar combinaciones de color.
4. **DevTools → Device Toolbar** — simula móviles (iPhone SE, Pixel 5).
5. **VoiceOver** (Mac: ⌘ + F5) / **NVDA** (Windows, gratis) — probar con lector de pantalla.
