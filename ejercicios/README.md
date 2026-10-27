# Ejercicios del Curso

Cada ejercicio es un archivo `.tex` **de partida**: compila tal como está y contiene
instrucciones, marcas `TODO` y la rúbrica (20 pts) al final. Las soluciones de referencia
están en [`../soluciones/`](../soluciones/) (para el instructor; los ejercicios 5–8 son abiertos
y no tienen solución única).

> **Regla del curso:** documente el *prompt* que usó y **revise críticamente** lo que devuelve la IA.
> Toda referencia bibliográfica debe ser una fuente que usted haya abierto. Las IA inventan citas.

## Módulo 1: Fundamentos de LaTeX
| Ejercicio | Descripción | Archivo | Solución |
|---|---|---|---|
| 1 | Ecuaciones de electrónica (6 ecuaciones + cálculo con `siunitx`) | [ejercicio1_ecuaciones.tex](ejercicio1_ecuaciones.tex) | [solución](../soluciones/ejercicio1_ecuaciones.tex) |
| 2 | Tablas y datos experimentales (carga de capacitor, estimación de τ) | [ejercicio2_tablas.tex](ejercicio2_tablas.tex) | [solución](../soluciones/ejercicio2_tablas.tex) |
| 3 | Informe de laboratorio completo (amplificador operacional inversor) | [ejercicio3_informe.tex](ejercicio3_informe.tex) | [solución](../soluciones/ejercicio3_informe.tex) |

## Módulo 2: LaTeX + IA
| Ejercicio | Descripción | Archivo | Solución |
|---|---|---|---|
| 4 | Corrección asistida por IA (documento con 8+ problemas de buenas prácticas) | [ejercicio4_correccion.tex](ejercicio4_correccion.tex) | [solución](../soluciones/ejercicio4_corregido.tex) |
| 5 | Proyecto integrador (IA en ≥ 4 etapas, con registro de uso) | [ejercicio5_proyecto.tex](ejercicio5_proyecto.tex) | — |
| 6 | Conversión de imagen a LaTeX con Mathpix / LaTeX-OCR | [ejercicio6_mathpix.tex](ejercicio6_mathpix.tex) | — |
| 7 | Comparación de herramientas de IA (misma tabla, mismo prompt) | [ejercicio7_comparacion.tex](ejercicio7_comparacion.tex) | — |
| 8 | Artículo académico avanzado (IA en todas las etapas) | [ejercicio8_avanzado.tex](ejercicio8_avanzado.tex) | — |

## Módulo 3: APA 7
| Ejercicio | Descripción | Archivo | Solución |
|---|---|---|---|
| 9 | Corregir un documento APA 7 con 10 errores | [apa7/ejercicio_apa7.tex](../apa7/ejercicio_apa7.tex) | [solución](../apa7/solucion_ejercicio_apa7.tex) |

Ejemplos de apoyo: [`../ejemplos/`](../ejemplos/).

## Cómo compilar
```bash
cd ejercicios && latexmk -pdf ejercicio1_ecuaciones.tex
```
En Overleaf: suba el archivo y use el compilador **pdfLaTeX**. Los paquetes `siunitx`, `circuitikz`,
`booktabs` y `pgfplots` vienen con TeX Live y MiKTeX.

> **Nota sobre la numeración.** Las guías PDF de los módulos numeran sus propios ejercicios de forma
> distinta (Módulo 1: 1–5; Módulo 2: 1–8). Esta tabla es la numeración **del repositorio**.
