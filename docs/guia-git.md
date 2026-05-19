# Guía Git + GitHub — 3 niveles progresivos

> Esta guía está pensada para que practiques con este repo antes de aplicar Git al proyecto formativo real (GA6 en adelante).

Pre-requisito: ya hiciste el ejercicio de [`git-onboarding-adso`](https://github.com/oele-dev/git-onboarding-adso) (Nivel 0 — fork + presentación). Si no, házlo primero.

---

## 🟢 Nivel 1 — Lectura y exploración (semana 1)

**Objetivo:** moverte por un repo sin miedo, entender qué tiene y qué pasó.

### Comandos clave

```bash
# 1. Clonar el repo a tu máquina
git clone https://github.com/{tu-usuario}/mini-sitio-adso.git
cd mini-sitio-adso

# 2. Ver el estado actual
git status

# 3. Ver el historial de cambios
git log --oneline -10

# 4. Ver qué cambió en el último commit
git show HEAD

# 5. Listar todas las ramas (locales y remotas)
git branch -a

# 6. Cambiar entre ramas
git checkout main
git checkout feature/menu-hamburguesa-mejorado

# 7. Volver a la última versión limpia
git checkout main
```

### Ejercicio Nivel 1

1. Clona el repo.
2. Lee el `README.md` completo.
3. Abre `index.html` en el navegador (doble clic).
4. Ejecuta `git log --oneline -20` y lee los últimos commits.
5. Cambia entre todas las ramas con `git checkout` y mira qué tiene cada una en `git status` y abriendo el `index.html`.
6. **Captura de pantalla** de la salida de `git log --oneline -20` + sube esa captura a tu daily de Discord / foro.

---

## 🟡 Nivel 2 — Commits y ramas (semana 2)

**Objetivo:** hacer un cambio real, commitearlo, subirlo a GitHub y abrir un Pull Request.

### Comandos clave

```bash
# 1. Crear una rama nueva desde main
git checkout main
git pull origin main           # asegurar que estás al día
git checkout -b feature/mi-mejora

# 2. Hacer cambios en archivos
# (editas un .html / .css / .md)

# 3. Ver qué cambió
git status
git diff

# 4. Agregar al "staging" y commitear
git add archivo.html
git commit -m "feat(catalogo): agrega producto 'Mousepad XL'"

# 5. Subir la rama al remoto
git push origin feature/mi-mejora

# 6. Abrir PR en GitHub (te da el link después del push)
```

### Convención de commits

Usamos **Conventional Commits**:

```
<tipo>(<área>): <descripción corta>
```

Tipos comunes:
- `feat` — nueva funcionalidad (ej. nueva página, nuevo producto)
- `fix` — corrección de bug (ej. botón roto)
- `docs` — solo cambios en documentación
- `style` — cambios de estilo (CSS, formato)
- `refactor` — reorganizar código sin cambiar comportamiento

Ejemplos buenos:
- ✅ `feat(contacto): agrega validación cliente en email`
- ✅ `fix(catalogo): corrige link roto en card de Laptop`
- ✅ `style(header): aumenta contraste del logo en modo oscuro`

Ejemplos malos:
- ❌ `cambios` — no dice nada
- ❌ `arreglos varios` — vago
- ❌ `WIP` — no debería estar en main

### Ejercicio Nivel 2 — Elige una rama TODO

El repo tiene varias ramas con tareas pendientes marcadas como `TODO`. Escoge **una** y complétala en tu fork:

| Rama | Qué falta |
|---|---|
| `feature/pagina-faq` | Agregar `faq.html` con preguntas frecuentes (5 preguntas, usar `<details>`) |
| `feature/footer-redes` | Agregar links a redes sociales en el footer (`<ul>` con `<a>`) |
| `feature/mejorar-a11y-formulario` | Mejorar errores accesibles en `contacto.html` (`aria-describedby`) |
| `feature/dark-mode-toggle` | Botón para alternar modo claro/oscuro manualmente |
| `feature/producto-nuevo` | Agregar un 7° producto al catálogo |

Pasos:

1. Haz fork del repo a tu cuenta.
2. Clona tu fork.
3. `git checkout -b feature/pagina-faq` (o la que elijas).
4. Implementa el TODO (lee los comentarios `<!-- TODO: ... -->` en los archivos).
5. Commits frecuentes y descriptivos.
6. `git push origin feature/pagina-faq`.
7. Abre Pull Request al repo original.

---

## 🔴 Nivel 3 — Colaboración avanzada (semana 3)

**Objetivo:** colaborar con compañeros sin romper nada — conflictos, code review, rebase.

### Conflictos de merge

Pasa cuando dos personas editan la misma línea. Git no sabe cuál ganar.

```bash
# Estás en feature/x, intentas mezclar main reciente
git checkout feature/mi-rama
git fetch origin
git merge origin/main

# Git dice: CONFLICT (content): Merge conflict in archivo.html
# Abres archivo.html y verás:
```

```html
<<<<<<< HEAD
<h1>Tu versión</h1>
=======
<h1>Versión de main</h1>
>>>>>>> origin/main
```

Resuélvelo eligiendo cuál quedarse (o combinando ambas), borrando las marcas `<<<<<<<`, `=======`, `>>>>>>>`, y:

```bash
git add archivo.html
git commit                     # mensaje automático "Merge ..."
git push
```

### Code review en PRs

Cuando otro abra un PR a tu fork (o tú al repo del compañero):

1. Lee los cambios en GitHub → pestaña **Files changed**.
2. Comenta línea por línea con sugerencias.
3. Aprueba con **Review → Approve** o pide cambios con **Request changes**.
4. El autor hace nuevos commits → el PR se actualiza solo.

### Rebase vs merge

```bash
# Estás en tu rama, quieres "ponerte al día" con main sin crear merge commit feo
git checkout feature/mi-rama
git fetch origin
git rebase origin/main         # reaplica tus commits SOBRE el main actual

# Si hay conflicto, lo resuelves, luego:
git add archivo.html
git rebase --continue
```

> ⚠️ **Regla de oro**: nunca hagas rebase de commits que ya están en `main` o que otros ya tienen. Solo rebase de **tu propia rama no compartida**.

### Ejercicio Nivel 3 (en parejas)

1. Aprendiz A hace fork y trabaja en `feature/agregar-buscador`.
2. Aprendiz B hace fork del fork de A (sí, fork-of-fork) y trabaja en `feature/agregar-buscador` también, modificando los **mismos archivos**.
3. Ambos abren PR.
4. Practican resolver el conflicto **deliberado**.
5. Hacen code review mutuo.

---

## 🛟 Cuando algo sale mal

```bash
# "Hice cambios y quiero descartarlos"
git checkout -- archivo.html             # descarta cambios sin commitear

# "Quiero deshacer el último commit (que no he pusheado)"
git reset --soft HEAD~1                  # mantiene los cambios en staging
git reset --hard HEAD~1                  # ⚠️ borra los cambios (irreversible)

# "Me cambié de rama sin guardar y necesito los cambios"
git stash                                # antes de cambiar
# trabajas en otra rama
git stash pop                            # recuperas los cambios

# "Hice commit en main por error, quiero moverlo a una rama"
git branch feature/movido                # crea rama desde el commit actual
git reset --hard HEAD~1                  # main vuelve atrás
git checkout feature/movido              # tu commit está aquí
```

## 📚 Recursos

- [Pro Git book](https://git-scm.com/book/es/v2) — el libro oficial, gratis y en español.
- [Oh My Git!](https://ohmygit.org/) — juego visual para aprender Git.
- [Visual Git Reference](https://marklodato.github.io/visual-git-guide/index-en.html) — los conceptos en diagramas.
- [Conventional Commits](https://www.conventionalcommits.org/es/v1.0.0/) — convención de mensajes.
- [GitHub Skills](https://skills.github.com/) — cursos interactivos oficiales de GitHub.
