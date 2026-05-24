# Checklist de usabilidad y accesibilidad — SIGPRECO

> Reglas de accesibilidad y usabilidad aplicadas al sistema SIGPRECO.
> Basado en estándares WCAG 2.1 nivel AA y diseño responsive institucional.

Conexión con evidencias:

- **GA5-EV02** — reglas de accesibilidad y usabilidad web
- **GA5-EV06** — accesibilidad y usabilidad móvil

Estándar de referencia:
https://www.w3.org/WAI/WCAG21/quickref/

---

# 1. Estructura semántica (WCAG 1.3.1)

| Regla                      | ✅ Cómo se aplicó                                                         |
| -------------------------- | ------------------------------------------------------------------------- |
| Una sola `<h1>` por página | Cada pantalla tiene un encabezado principal único                         |
| Jerarquía correcta         | Uso progresivo de `<h1>`, `<h2>` y `<h3>`                                 |
| HTML semántico             | Uso de `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>` |
| Sidebar semántico          | El menú lateral usa `<aside>` + `<nav>`                                   |
| Formularios accesibles     | Uso de `<fieldset>` y `<legend>`                                          |
| Cards administrativas      | Cada módulo usa `<article>` independiente                                 |

---

# 2. Navegación por teclado (WCAG 2.1.1, 2.4.7)

- ✅ Existe un **skip link** para saltar al contenido principal.
- ✅ Todos los elementos interactivos muestran foco visible.
- ✅ El orden del teclado coincide con el orden visual.
- ✅ El sidebar puede navegarse completamente con teclado.
- ✅ Los formularios permiten navegación mediante `Tab`.

## Cómo probarlo

Presionar:

```text
Tab
```

Todos los botones, inputs y enlaces deben recibir foco visible.

---

# 3. Contraste de color (WCAG 1.4.3)

| Elemento           | Foreground | Background | Cumple |
| ------------------ | ---------- | ---------- | ------ |
| Texto principal    | `#1F2937`  | `#FFFFFF`  | ✅     |
| Sidebar            | `#FFFFFF`  | `#1E3A8A`  | ✅     |
| Botones            | `#FFFFFF`  | `#1E3A8A`  | ✅     |
| Texto secundario   | `#6B7280`  | `#FFFFFF`  | ✅     |
| Hero institucional | `#FFFFFF`  | `#162C6B`  | ✅     |

Herramienta usada:

- WebAIM Contrast Checker

---

# 4. Imágenes e iconografía (WCAG 1.1.1)

- ✅ Todas las imágenes tienen atributo `alt`.
- ✅ Los elementos decorativos no afectan lectores de pantalla.
- ✅ Las imágenes son responsive (`max-width: 100%`).
- ✅ El sistema evita desplazamientos visuales inesperados.

Ejemplo:

```html
<img src="dashboard.png" alt="Panel administrativo SIGPRECO" />
```

---

# 5. Formularios (WCAG 1.3.5, 3.3.1, 3.3.2)

- ✅ Todos los inputs tienen `<label>`.
- ✅ Se utilizan tipos correctos (`email`, `text`, `password`).
- ✅ Campos obligatorios marcados correctamente.
- ✅ Formularios agrupados con `<fieldset>`.
- ✅ Inputs adaptados para dispositivos móviles.
- ✅ Validación básica implementada.

---

# 6. Tamaños táctiles (WCAG 2.5.5)

Todos los botones e inputs utilizan:

```css
min-height: 44px;
```

Esto mejora la interacción táctil en móviles y tablets.

---

# 7. Idioma del sistema (WCAG 3.1.1)

```html
<html lang="es"></html>
```

Permite que lectores de pantalla utilicen pronunciación correcta.

---

# 8. Responsive design (WCAG 1.4.10)

- ✅ Diseño mobile-first.
- ✅ Sidebar adaptable en pantallas pequeñas.
- ✅ Cards administrativas responsive.
- ✅ Formularios adaptables.
- ✅ Layout sin scroll horizontal.
- ✅ Uso de media queries.

---

# 9. Preferencias del usuario (WCAG 2.3.3)

- ✅ Compatibilidad con `prefers-reduced-motion`.
- ✅ Compatibilidad con `prefers-color-scheme: dark`.
- ✅ Transiciones suaves y no invasivas.

---

# 10. Estructura HTML válida

- ✅ `<!DOCTYPE html>`
- ✅ `<meta charset="UTF-8">`
- ✅ `<meta name="viewport">`
- ✅ `<title>` descriptivo por página
- ✅ Navegación semántica válida

---

# Reglas específicas para móvil (EV06)

Además de las reglas anteriores:

1. Sidebar adaptable para móviles.
2. Navegación táctil optimizada.
3. Inputs con tamaño adecuado.
4. Layout de una columna en pantallas pequeñas.
5. Cards reorganizadas automáticamente.
6. Formularios responsive.
7. Diseño sin necesidad de zoom manual.

---

# Componentes principales del sistema

| Componente         | Estructura HTML         |
| ------------------ | ----------------------- |
| Sidebar            | `<aside>` + `<nav>`     |
| Dashboard          | `<main>` + `<section>`  |
| Cards módulos      | `<article>`             |
| Formularios        | `<form>` + `<fieldset>` |
| Panel soporte      | `<section>`             |
| Actividad reciente | `<article>`             |

---

# Cómo entregar la evidencia

Archivos utilizados:

- `docs/accesibilidad.md`
- `docs/wireframes.md`
- `docs/mapa-navegacion.md`
- `index.html`
- `catalogo.html`
- `detalle.html`
- `contacto.html`
- `css/styles.css`

---

# Herramientas recomendadas

1. Lighthouse (Chrome DevTools)
2. axe DevTools
3. WebAIM Contrast Checker
4. Device Toolbar (responsive)
5. NVDA / VoiceOver
