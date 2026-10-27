# Revisión del repositorio y propuesta de mejoras

Revisión realizada el 2026-10-27 compilando las plantillas con TeX Live 2023. Las mejoras marcadas ✅ ya están implementadas en esta rama; las demás son propuestas.

## 1. Hallazgos

| # | Hallazgo | Impacto | Estado |
|---|---|---|---|
| 1 | `plantillas/informe_laboratorio.tex` **no compilaba**: el carácter `Ω` no está soportado con `inputenc`, y `\ref{fig:circuito}` apuntaba a una figura inexistente | Alto: es la plantilla base del Ejercicio 3 | ✅ Corregido (`siunitx`, `circuitikz`, `booktabs`) |
| 2 | Los ejemplos de `contenido/README.md` usaban `$$…$$`, `Ω` en tablas, `[h]`, líneas verticales y `circuits.ee.IEC` en TikZ puro | Medio: enseñan malas prácticas | ✅ Reemplazados por `\[…\]`, `siunitx`, `booktabs`, `circuitikz` |
| 3 | El ejemplo BibTeX modelaba un libro como `@article` con `journal={Pearson Educación}` | Medio: enseña un error de datos | ✅ Sustituido por un artículo real |
| 4 | No existía ninguna sección de APA, aunque `referencias.bib` lo menciona | Alto (solicitado) | ✅ Módulo 3 en `apa7/` |
| 5 | `ejercicios/README.md` enlaza `ejercicio1…8_*.tex` que **no existían**; tampoco `soluciones/` | Alto: enlaces rotos | ✅ Creados los 8 ejercicios y `soluciones/` (1–4). Falta `estudiantes/` (carpeta vacía por alumno) |
| 6 | `recursos/referencias.bib` contiene entradas que parecen inventadas o con datos dudosos (p. ej. `openai2023`, `claude2024`, `ieeelatex2020`, `thd2021`, `pwm2022`, `pid2023`) | Alto: contradice la enseñanza de verificar fuentes | ✅ Depurado: el archivo pasó de 47 a 22 entradas al eliminar las no verificables (artículos técnicos, tesis, congresos, cursos, normas); los libros restantes quedan marcados *VERIFICAR* y sin ISBN. No hubo acceso a Crossref/WorldCat desde la sesión, así que la comprobación final de DOI y ediciones queda para el instructor |
| 7 | Los PDF de `guias/` están versionados junto a los `.tex` y pueden desfasarse | Bajo | Propuesta: compilar con GitHub Actions |
| 8 | Solo se enseña IEEE/BibTeX; el curso no menciona `biblatex` + `biber`, que es lo que Overleaf recomienda hoy | Medio | ✅ Cubierto en el Módulo 3 |
| 9 | Los prompts de ejemplo piden "referencias bibliográficas" a la IA sin advertir que pueden ser falsas | Medio: riesgo de integridad académica | ✅ Advertencia en `apa7/README.md` §6; pendiente replicar en `recursos/guia_prompts_ia.md` |

## 2. Qué se añadió

- **`apa7/`**: guía del Módulo 3 (APA 7), plantilla `articulo_apa7.tex` (modo estudiante, español, tabla/figura/nota, citas y reconocimiento de IA), `referencias_apa.bib` (libro, manual, artículo, congreso, web, software, IA, tesis) y el **Ejercicio 9** con solución.
- **`ejemplos/`**: dos ejemplos compilables (ecuaciones; tablas + gráfica + circuito + diagrama de flujo) que sustituyen a los fragmentos sueltos.
- **`plantillas/informe_laboratorio.tex`** corregida y mejorada.
- `.gitignore` ampliado para `biber`.

## 3. Propuestas pendientes (por prioridad)

1. ~~Crear ejercicios 1–8 y `soluciones/`~~ ✅ hecho. Pendiente: soluciones modelo para 5–8 si se desea y la carpeta `estudiantes/`.
2. ~~Auditar `recursos/referencias.bib`~~ ✅ hecho. Pendiente: confirmar con el ejemplar de biblioteca edición/año de los libros marcados *VERIFICAR* y el DOI de las entradas de IA.
3. **Un criterio de evaluación por módulo** (rúbrica de 20 pts, como en el Ejercicio 9) y una evaluación de entrada/salida de 10 preguntas.
4. **Módulo de "depuración con IA"**: banco de 10 errores reales de compilación (`Undefined control sequence`, `Missing $ inserted`, `File not found`…), con el log y el prompt que ayuda a resolverlos.
5. **Integridad académica**: añadir a `recursos/guia_prompts_ia.md` la plantilla de declaración de uso de IA y la cita APA 7 de herramientas de IA.
6. **CI**: workflow de GitHub Actions (`latexmk`) que compile `plantillas/`, `ejemplos/` y `apa7/` en cada PR, para que no vuelva a haber plantillas rotas.
7. **Compatibilidad de motores**: unificar `inputenc`/`fontenc` (pdfLaTeX) o migrar a LuaLaTeX/XeLaTeX con `fontspec`; documentar la elección en `setup/`.
8. **Plantilla de tesis UNTELS con APA 7** (`biblatex-apa`) como opción además de IEEE.
9. **Accesibilidad**: texto alternativo en figuras (`\pdftooltip`/PDF/UA) y paleta de colores apta para daltonismo en las guías.
10. **Diapositivas Beamer** del curso reutilizando la plantilla existente.
