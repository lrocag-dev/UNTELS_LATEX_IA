# Módulo 3: Formato APA 7.ª edición con LaTeX (+ IA)

**Duración sugerida:** 2 horas (45 min teoría · 45 min práctica · 30 min ejercicio)
**Requisitos:** haber visto los Módulos 1 y 2 (estructura de documento, tablas, figuras, BibTeX).
**Archivos de esta carpeta**

| Archivo | Para qué sirve |
|---|---|
| [`articulo_apa7.tex`](articulo_apa7.tex) | Plantilla lista para compilar (modo estudiante, español) |
| [`referencias_apa.bib`](referencias_apa.bib) | Un ejemplo de cada tipo de fuente (libro, artículo, web, software, IA, tesis…) |
| [`ejercicio_apa7.tex`](ejercicio_apa7.tex) | Documento con **errores intencionales** que debes corregir |
| [`solucion_ejercicio_apa7.tex`](solucion_ejercicio_apa7.tex) | Versión corregida (para el instructor) |

---

## 1. ¿Por qué APA 7 en LaTeX?

APA (American Psychological Association) es el estilo más usado en ciencias e ingeniería de Latinoamérica para tesis, informes e investigación formativa. Hacerlo a mano en Word obliga a repetir tareas: sangría francesa, citas, orden alfabético, numeración de tablas. En LaTeX **declaras** el formato una vez y el sistema lo aplica:

| Tarea APA | En Word | En LaTeX |
|---|---|---|
| Portada, encabezado con número de página | manual | `\maketitle` + clase `apa7` |
| Citas (Autor, año) | manual / gestor | `\parencite{clave}` / `\textcite{clave}` |
| Lista de referencias (orden, sangría francesa, "&", "et al.") | manual / gestor | `\printbibliography` |
| Numeración de tablas y figuras | manual | automática (`\caption`, `\ref`) |
| Cambiar de APA a IEEE | rehacer | cambiar `style=apa` → `style=ieee` |

## 2. Dos caminos (elige uno)

| | **A. Clase `apa7`** (recomendado) | **B. `article` + `biblatex-apa`** |
|---|---|---|
| Qué cubre | Portada, encabezados, niveles de título, tablas, figuras, interlineado, sangrías | Solo citas y referencias |
| Cuándo usarlo | Trabajos que **deben** seguir APA completo | Ya tienes un formato institucional (p. ej. plantilla UNTELS) y solo necesitas citas/referencias APA |
| Modos | `stu` (estudiante), `man` (manuscrito), `jou` (revista), `doc` (documento) | — |

Esta guía usa el camino A. Para el B basta con copiar las líneas de bibliografía de la sección 4.

## 3. Estructura mínima (clase `apa7`)

```latex
\documentclass[stu,12pt,a4paper,floatsintext]{apa7}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[spanish,es-tabla]{babel}   % «Tabla» en lugar de «Cuadro»
\usepackage{csquotes}                  % necesario para biblatex + babel

\usepackage[style=apa,backend=biber,sortcites=true,sorting=nyt]{biblatex}
\DeclareLanguageMapping{spanish}{spanish-apa}
\addbibresource{referencias_apa.bib}

\title{Título del trabajo}
\shorttitle{Título corto}              % encabezado, máx. 50 caracteres
\authorsnames{Nombre Apellido}
\authorsaffiliations{Facultad, Universidad}
\course{Código: Curso}
\professor{Docente}
\duedate{27 de octubre de 2026}

\abstract{Entre 150 y 250 palabras…}
\keywords{palabra 1, palabra 2}

\begin{document}
\maketitle
\section{Introducción}
…
\printbibliography[title={Referencias}]
\end{document}
```

> **Compilación:** `pdflatex → biber → pdflatex → pdflatex`, o simplemente `latexmk -pdf articulo_apa7.tex`.
> En **Overleaf** elige *Menu → Compiler: pdfLaTeX*; ejecuta `biber` automáticamente.
> En **VS Code (LaTeX Workshop)** usa la receta *latexmk*. Si ves "citas indefinidas", casi siempre falta ejecutar `biber`.
>
> ⚠️ **BibTeX ≠ Biber.** `biblatex-apa` requiere **biber**. Si Overleaf/TeXstudio usan `bibtex` obtendrás errores.

### Qué hace APA 7 por ti (resumen de las reglas)

| Elemento | Regla APA 7 | Cómo se logra |
|---|---|---|
| Márgenes | 2,54 cm (1 pulgada) | la clase lo fija |
| Fuente | Times New Roman 12 pt (también admitidas Calibri 11, Arial 11, Georgia 11, Lucida Sans Unicode 10) | por defecto; con `\usepackage{...}` puede cambiarse |
| Interlineado | Doble en todo el documento | automático en `stu`/`man` |
| Sangría de párrafo | 1,27 cm (0,5 in) | automática |
| Numeración | Esquina superior derecha, desde la portada | automática |
| Títulos (5 niveles) | N1 centrado negrita · N2 izq. negrita · N3 izq. negrita cursiva · N4 sangría negrita punto final · N5 sangría negrita cursiva punto final | `\section`, `\subsection`, `\subsubsection`, `\paragraph`, `\subparagraph` |
| Tablas | Número en negrita, título en cursiva **arriba**, sin líneas verticales, nota debajo | `booktabs` + `threeparttable` (ver plantilla) |
| Figuras | Número en negrita, título en cursiva **arriba**, nota "Nota." debajo | `\caption` + `\figurenote{…}` |
| Referencias | Orden alfabético, sangría francesa, DOI como URL | `\printbibliography` |

## 4. Citas: qué comando usar

| Quiero escribir… | Comando | Resultado |
|---|---|---|
| Cita entre paréntesis | `\parencite{shannon1948}` | (Shannon, 1948) |
| Cita narrativa | `\textcite{shannon1948}` | Shannon (1948) |
| Con página | `\parencite[p.~381]{shannon1948}` | (Shannon, 1948, p. 381) |
| Varias fuentes | `\parencite{a,b}` | (A, 2020; B, 2021) — ordenadas alfabéticamente |
| Dos autores | automático | (Sedra & Smith, 2020) · narrativa: Sedra y Smith (2020) |
| 3 o más autores | automático | (Kasneci et al., 2023) |
| Solo el año | `\parencite*{clave}` | (2023) |
| Autor corporativo | `author = {{UNESCO}}` (**doble llave**) | (UNESCO, 2021) |
| Cita directa de ≥ 40 palabras | entorno `quote` | bloque con sangría, sin comillas |

**Regla de oro:** usa `\parencite` y `\textcite`, **no** `\cite` (en biblatex-apa `\cite` imprime la cita sin paréntesis).

## 5. El archivo `.bib` para APA

Usa los campos de **biblatex** (no los de BibTeX clásico):

| BibTeX clásico | biblatex |
|---|---|
| `journal` | `journaltitle` |
| `address` | `location` |
| `school` | `institution` |
| `@phdthesis` / `@mastersthesis` | `@thesis` con `type = {Tesis de licenciatura}` |
| URL de recurso web | `@online` con `url` y `urldate` |

Entradas imprescindibles:

```bibtex
@article{shannon1948,
  author       = {Shannon, Claude E.},
  title        = {A mathematical theory of communication},
  journaltitle = {Bell System Technical Journal},
  year         = {1948}, volume = {27}, number = {3}, pages = {379--423},
  doi          = {10.1002/j.1538-7305.1948.tb01338.x}
}

@online{unesco2021,
  author = {{UNESCO}},                       % autor corporativo: doble llave
  title  = {Recomendación sobre la ética de la inteligencia artificial},
  year   = {2021},
  url    = {https://unesdoc.unesco.org/ark:/48223/pf0000380455_spa}
}
```

**Detalles que más fallan**

- Las mayúsculas: en inglés APA usa mayúscula solo en la primera palabra del título; protege siglas y nombres propios con llaves: `{ChatGPT} for good? {O}n …`.
- Más de 20 autores: biblatex-apa abrevia solo (primeros 19 … último).
- `doi` va **sin** `https://doi.org/`; la plantilla lo añade.
- Si una fuente no tiene fecha, escribe `year = {s.f.}`.
- Pon `langid = {spanish}` o `{english}` para que "ed.", "&" / "y" salgan en el idioma correcto.

## 6. Citar herramientas de IA en APA 7

APA 7 (guía oficial 2023) trata a la IA generativa como **software**: el autor es la empresa, no el modelo, y debes poder indicar qué consultaste.

```text
OpenAI. (2025). ChatGPT (versión de mayo) [Modelo de lenguaje de gran tamaño]. https://chatgpt.com
```

**Buenas prácticas que exige el curso**

1. **Reconoce el uso** en el texto o en una nota de método: qué herramienta, para qué (p. ej. "depurar código LaTeX") y fecha.
2. **Cita la herramienta** en el texto como (OpenAI, 2025) cuando incluyas texto generado; si solo la usaste para depurar código, basta el reconocimiento.
3. **Nunca cites fuentes que la IA te dio sin abrirlas.** Los modelos pueden inventar referencias con autores, revistas y DOI plausibles pero falsos. Comprueba cada DOI en <https://doi.org>.
4. Guarda el *prompt* y la respuesta (usa `recursos/plantilla_documentacion_prompts.tex`).
5. Sigue la política de integridad académica de tu curso: la IA no es coautora.

### Prompts útiles (y seguros)

```text
Convierte esta referencia a una entrada BibTeX/biblatex para biblatex-apa,
usando journaltitle, doi y langid. No inventes datos: si falta algo, déjalo
en blanco y dime qué falta.

[pegar referencia copiada de la fuente real]
```

```text
Revisa esta entrada .bib frente a APA 7 y lista qué campos faltan o están
mal (mayúsculas del título, autor corporativo, tipo de entrada). No cambies
datos bibliográficos; solo señala problemas.
```

```text
Explica este error de biber/biblatex y dime cómo corregirlo:
[pegar el log]
```

❌ **No uses:** "Dame 5 referencias sobre filtros activos en formato BibTeX" (genera fuentes falsas).

## 7. Errores frecuentes

| Síntoma | Causa | Solución |
|---|---|---|
| `(?)` o "citation undefined" | No se ejecutó `biber` | Compilar con latexmk o la secuencia completa |
| `File 'lmodern.sty' not found` | Instalación mínima de TeX | Instalar `lmodern` (MiKTeX lo hace solo) |
| Error con `\addbibresource` | Se usó `\bibliography` | Con biblatex siempre `\addbibresource{…bib}` y `\printbibliography` |
| "Cuadro 1" en vez de "Tabla 1" | `babel` español por defecto | Opción `es-tabla` |
| Autor corporativo sale "Unesco, UNESCO" | Faltan dobles llaves | `author = {{UNESCO}}` |
| Tablas al final del documento | Modo `stu` por defecto | Opción `floatsintext` |
| Dos títulos seguidos | Se repitió el título con `\section` | `apa7` ya lo repite al empezar el cuerpo |
| `\tabnote` / `\note` no definido | Comandos de otras clases | `threeparttable` + `tablenotes` y `\figurenote` |

## 8. Ejercicio 9 — Corrige un documento APA

1. Compila `ejercicio_apa7.tex` y anota los avisos.
2. Corrige **los 10 errores** señalados con `% ERROR` (portada, citas, tabla con líneas verticales, referencia sin `doi`, uso incorrecto de `\cite`, etc.).
3. Añade una fuente nueva a `referencias_apa.bib` (de una fuente que hayas **abierto**) y cítala narrativa y entre paréntesis.
4. Reconoce el uso de IA con una oración y su cita.
5. Entrega `.tex`, `.bib` y `.pdf`.

**Rúbrica (20 pts):** compila sin errores (4) · portada y encabezados APA (3) · citas correctas, narrativa y parentética (4) · lista de referencias correcta (4) · tabla/figura APA (3) · reconocimiento de IA (2).

## 9. Recursos oficiales

- Manual: American Psychological Association (2020). *Publication manual of the American Psychological Association* (7.ª ed.).
- Guía de estilo en línea: <https://apastyle.apa.org>
- Documentación del paquete: <https://ctan.org/pkg/apa7> y <https://ctan.org/pkg/biblatex-apa>
