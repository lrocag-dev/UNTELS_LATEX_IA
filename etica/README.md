# Módulo 4: Publicación ética de resultados obtenidos con IA

**Duración sugerida:** 1,5 horas (30 min teoría · 30 min casos · 30 min declaración y checklist)
**Dirigido a:** tesis de pregrado, informes y artículos de ciencias e ingeniería.

> **Idea central.** La IA puede ayudarte a escribir, programar y analizar, pero **tú eres el único responsable** de lo que firmas: datos, resultados, citas y conclusiones. Usar IA no es una falta; **ocultarla, inventar datos o citar fuentes que no abriste, sí.**

| Archivo | Para qué sirve |
|---|---|
| [`declaracion_uso_ia.tex`](declaracion_uso_ia.tex) | Plantilla compilable de declaración de uso de IA y registro de prompts |
| Este README | Principios, niveles de uso, qué declarar, checklist y casos |

---

## 1. Principios

1. **Responsabilidad.** La IA no es autora ni coautora. Revistas y comités editoriales coinciden en esto (p. ej. recomendaciones del ICMJE y declaración de COPE sobre IA y autoría, 2023). Verifica su vigencia: las políticas cambian rápido.
2. **Transparencia.** Declara qué herramienta usaste, para qué y en qué parte del trabajo.
3. **Integridad de los datos.** Un dato generado por IA **no es un dato experimental**. Fabricar o falsificar resultados es mala conducta científica, la haya cometido una persona o un modelo.
4. **Verificabilidad.** Todo lo que afirmas debe poder comprobarse en una fuente primaria, en tus mediciones o en un código que ejecutaste.
5. **Confidencialidad y derechos.** No cargues en herramientas públicas datos personales, datos confidenciales de una empresa, resultados inéditos de un asesor ni textos protegidos que no puedes compartir.
6. **Equidad.** Revisa sesgos del modelo y no lo uses para suplantar tu trabajo en evaluaciones donde está prohibido.

> **Regla práctica:** si el docente, el asesor o el revisor preguntara "¿cómo obtuviste esto?", debes poder responder con documentos, no de memoria.

## 2. Niveles de uso y qué declarar

| Nivel | Uso de la IA | Ejemplo | ¿Declarar? |
|---|---|---|---|
| 0 | Ninguno | — | No aplica |
| 1 | Asistencia mecánica | Corregir ortografía, traducir un párrafo **tuyo**, formatear LaTeX/BibTeX | Recomendado; **obligatorio** si la política del curso, revista o universidad lo pide |
| 2 | Asistencia de código | Depurar un error de compilación, generar código TikZ/`circuitikz`, scripts de análisis | **Sí**, indicando qué validaste |
| 3 | Análisis | Procesar datos, ajustar curvas, resumir literatura | **Sí**, con el código y los datos de entrada |
| 4 | Generación de contenido | Redactar secciones, proponer estructura, crear figuras o tablas | **Sí, siempre**, en el texto y en la declaración |
| 5 | Generación de datos o resultados | Datos "simulados" por el modelo, resultados no medidos | **Solo** si el trabajo trata de eso, rotulado como sintético y nunca presentado como medición |

**No es aceptable en ningún caso:** presentar como medidos datos generados; citar referencias que la IA sugirió y no abriste; ocultar el uso cuando la norma exige declararlo; subir datos confidenciales a un servicio público.

## 3. Cómo se declara

### 3.1 Dónde
| Documento | Lugar habitual |
|---|---|
| Tesis | Sección "Declaración de uso de herramientas de IA" (después de la declaración de originalidad o en el apéndice) + nota en Metodología si afectó el método |
| Artículo | Agradecimientos o Métodos, según la revista; en la carta de presentación; **sigue la guía de autores de la revista** |
| Informe o trabajo de curso | Nota final o sección propia, según el sílabo |

### 3.2 Texto modelo (adáptalo a lo que realmente hiciste)
```text
Declaración de uso de inteligencia artificial.
Durante la preparación de este trabajo el/la autor/a utilizó [herramienta, versión o
modelo, proveedor] entre [fecha] y [fecha] para [finalidad concreta: depurar código LaTeX,
mejorar la redacción de la sección 2, etc.]. Tras su uso, el/la autor/a revisó, verificó y
editó el contenido y asume la plena responsabilidad por el trabajo. Todos los datos
experimentales fueron obtenidos y procesados por el/la autor/a; ningún resultado fue generado
por IA. Los prompts y respuestas se conservan en [ubicación] y están disponibles a solicitud.
```
La plantilla [`declaracion_uso_ia.tex`](declaracion_uso_ia.tex) incluye este texto y una tabla de registro. En la plantilla de tesis ([`../plantillas/tesis_untels.tex`](../plantillas/tesis_untels.tex)) ya vienen integrados: el capítulo preliminar *Declaración de uso de herramientas de IA* (opciones A «sí usé» y B «no usé»), la sección *Uso de herramientas de IA* en Metodología y el *Apéndice A: Registro de uso*.

### 3.3 Cómo se cita (APA 7)
APA trata a la herramienta como **software cuyo autor es la empresa**, y recomienda describir en el texto el *prompt* usado cuando se incorpora contenido generado:

```text
Cuando se le pidió explicar la tierra virtual del amplificador inversor, ChatGPT respondió… (OpenAI, 2025).

OpenAI. (2025). ChatGPT (versión de mayo) [Modelo de lenguaje de gran tamaño]. https://chatgpt.com
```
Con LaTeX: entrada `@software` de `apa7/referencias_apa.bib` y `\parencite{openai_chatgpt}`. Detalles en [`../apa7/README.md`](../apa7/README.md) §6.

> Citar la herramienta **no sustituye** citar la fuente real de una afirmación. Si la IA te dio una idea con respaldo en la literatura, busca, abre y cita esa literatura.

## 4. Riesgos concretos y cómo mitigarlos

| Riesgo | Ejemplo | Mitigación |
|---|---|---|
| **Referencias inventadas** | Autores, revista y DOI plausibles pero falsos | Abre cada DOI en <https://doi.org>; busca el título en Google Scholar o en la base de la revista; cita solo lo que leíste |
| **Resultados fabricados** | La IA "completa" una tabla experimental | Toda cifra debe rastrearse a una medición, simulación **declarada** o fuente citada |
| **Errores técnicos con apariencia correcta** | Ecuación con signo mal, código TikZ de un circuito que no funciona | Reproduce a mano el cálculo; simula el circuito; compila y revisa el PDF |
| **Plagio involuntario** | Texto que reproduce fragmentos de una fuente | Parafrasea con tus palabras, cita y pasa tu revisión de similitud institucional |
| **Fuga de información** | Pegar el borrador de tesis con datos de una empresa | Usa datos anonimizados, herramientas autorizadas o instalaciones locales |
| **Sesgo / generalización indebida** | Conclusiones "universales" sin respaldo | Delimita alcance y contrasta con literatura |
| **Figuras e imágenes generadas** | Fotografía "de laboratorio" creada por IA | **No** la uses como evidencia; muchas editoriales las prohíben. Los esquemas generados con código (TikZ, `pgfplots`) sí son reproducibles |
| **Licencias y derechos** | Reutilizar salida del modelo sin revisar términos | Lee los términos de uso y las reglas de la revista/universidad |
| **Falsa seguridad con detectores** | "Detector de IA" marca texto humano | Los detectores **no son concluyentes** y no deben ser la única prueba de nada; la mejor evidencia es tu registro de trabajo |

## 5. Reproducibilidad: qué registrar

Para cada uso relevante guarda (por ejemplo en `plantilla_documentacion_prompts.tex`, ya incluida en `recursos/`):

- Herramienta, **modelo/versión** y fecha de la consulta.
- *Prompt* completo y respuesta (o enlace compartido).
- Qué parte del trabajo afectó.
- Qué **verificaste** y cómo (cálculo propio, simulación, fuente primaria).
- Qué **cambiaste o rechazaste** y por qué.

Con LaTeX, controla versiones con Git: cada cambio asistido por IA en un *commit* con mensaje claro deja trazabilidad.

## 6. Con tu asesor y con la universidad

- Pregunta **antes** si el curso, el asesor o el reglamento de grados y títulos de tu universidad limita el uso de IA. Si no hay norma, pide una indicación por escrito.
- Si algo es ambiguo, **declara de más**, no de menos.
- La UNESCO publicó una *Recomendación sobre la ética de la inteligencia artificial* (2021) útil como marco general: <https://unesdoc.unesco.org/ark:/48223/pf0000380455_spa>.
- Este documento es una guía educativa, **no** un reglamento: prevalecen las normas de tu universidad, de la revista y de la legislación aplicable.

## 7. Checklist antes de entregar o enviar

- [ ] Conozco la política de IA de mi curso / asesor / revista y la cumplo.
- [ ] Toda referencia fue **abierta y leída** por mí; verifiqué cada DOI.
- [ ] Todo dato y resultado proviene de mis mediciones, de simulaciones declaradas o de fuentes citadas.
- [ ] Reproduje o comprobé por mi cuenta ecuaciones, código y circuitos.
- [ ] No usé datos confidenciales ni personales en herramientas públicas.
- [ ] Declaré el uso de IA (herramienta, versión, fecha, finalidad, verificación).
- [ ] Citaré la herramienta en APA 7 cuando incorporé su contenido.
- [ ] Guardé prompts y respuestas relevantes.
- [ ] Pasé la revisión de similitud que exige mi universidad.
- [ ] Yo entiendo y puedo defender cada línea del trabajo.

## 8. Casos para discutir (30 min, en grupos)

Para cada caso: ¿es aceptable? ¿qué falta declarar? ¿qué haría usted?

1. **La tabla "medida".** Ana no alcanzó a tomar las mediciones del laboratorio y le pidió a una IA "una tabla realista de corriente vs voltaje para un diodo". La incluye en su informe como "resultados experimentales".
2. **La bibliografía.** Luis pidió "10 referencias sobre filtros activos en BibTeX". Revisó que el formato compilara y las incluyó sin abrirlas.
3. **La traducción.** Marta escribió el resumen en español y usó una IA para traducirlo al inglés; lo leyó y corrigió. No lo declaró porque "es solo traducción".
4. **El código.** Jorge usó una IA para escribir el script que ajusta la curva de carga de un capacitor. Lo ejecutó con sus datos, comprobó dos puntos a mano y lo declaró en Métodos.
5. **El borrador del asesor.** Rosa pegó en un chatbot público un capítulo con datos de una empresa bajo acuerdo de confidencialidad para "mejorar la redacción".
6. **La figura.** Pedro pidió a una IA generar una "foto del montaje en protoboard" porque olvidó tomarla.
7. **El detector.** Un docente acusa a Carla de usar IA solo porque un detector marcó 80 %. Carla redactó sola y tiene su historial de Git.

*Orientación para el instructor:* 1, 2, 5 y 6 son faltas (fabricación, citas no verificadas, fuga de datos, evidencia falsa). 3 y 4 son aceptables **declarando** (nivel 1 y 2). En 7, un detector no es prueba concluyente; la conversación debe apoyarse en el historial de trabajo y en que Carla pueda explicar su trabajo.

## 9. Ejercicio 10 — Declaración y registro

1. Elige un trabajo anterior del curso en el que hayas usado IA (p. ej. el Ejercicio 3 o el 5).
2. Completa [`declaracion_uso_ia.tex`](declaracion_uso_ia.tex): declaración, tabla de registro (≥ 3 filas) y checklist.
3. Verifica **todas** las referencias de ese trabajo y anota cuáles no pudiste comprobar y qué hiciste.
4. Entrega `.tex` y PDF.

**Rúbrica (20 pts):** declaración completa y precisa (5) · registro con modelo/fecha/prompt/verificación (5) · verificación de referencias documentada (5) · reflexión sobre qué cambió o rechazó de la IA (5).

## 10. Lecturas
- ICMJE. *Recommendations for the Conduct, Reporting, Editing, and Publication of Scholarly Work in Medical Journals* (sección sobre IA y autoría).
- COPE. *Authorship and AI tools* (posición, 2023).
- UNESCO (2021). *Recomendación sobre la ética de la inteligencia artificial*.
- American Psychological Association (2020). *Publication manual* (7.ª ed.) y guía en línea de APA Style sobre citar IA generativa.
- Guía para autores de la revista o reglamento de tesis donde publicarás.
