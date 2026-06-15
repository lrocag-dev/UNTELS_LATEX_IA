# Guía de Prompts para IA - LaTeX Académico

## ¿Qué es un Prompt?

Un **prompt** es la instrucción que le das a un modelo de Inteligencia Artificial (como ChatGPT, Gemini o Claude) para obtener una respuesta específica. En el contexto de LaTeX, los prompts permiten generar código, corregir errores y optimizar documentos.

> **Principio clave:** La calidad del resultado es directamente proporcional a la claridad de tu instrucción.

---

## Estructura de un Prompt Efectivo

Un buen prompt debe contener los siguientes elementos:

| Elemento | Descripción | Ejemplo |
|----------|-------------|---------|
| **Contexto** | Define el rol de la IA | "Actúa como un experto en LaTeX especializado en ingeniería electrónica..." |
| **Objetivo** | Qué quieres lograr | "Genera el código para un informe de laboratorio..." |
| **Especificaciones** | Detalles concretos | "Incluye ecuación numerada, tabla con 5 filas y figura referenciada" |
| **Restricciones** | Límites o reglas | "Usa solo paquetes estándar como amsmath y graphicx" |
| **Formato** | Cómo quieres la respuesta | "Proporciona solo el código, sin explicaciones adicionales" |

---

## Ejemplos de Prompts por Categoría

### 1. Generación de Ecuaciones

#### Prompt básico (menos efectivo)
```text
Escribe la ecuación de la Ley de Ohm
```
#### Prompt avanzado (más efectivo)
```text
Genera el código LaTeX para la ecuación de la Ley de Ohm: V = I * R.
La ecuación debe estar numerada automáticamente, usar formato profesional
con el punto central (\cdot) y tener una etiqueta para referenciarla.
```
#### Prompt para ecuaciones complejas
```text
Genera el código LaTeX para la función de transferencia de un filtro
pasa bajos de segundo orden: H(s) = ω₀² / (s² + (ω₀/Q)s + ω₀²).
La ecuación debe usar notación profesional, incluir el símbolo ω
(omega) y estar numerada.
```
### 2. Generación de Tablas

#### Prompt básico
```text
Crea una tabla con datos de voltaje y corriente
```
#### Prompt avanzado
```text
Crea una tabla en LaTeX con los siguientes datos de un experimento
de ley de Ohm:

Voltaje (V): 1.0, 3.0, 5.0, 7.0, 9.0
Corriente (mA): 9.8, 29.5, 49.2, 68.9, 88.6

La tabla debe:

Tener 3 columnas: Voltaje (V), Corriente (mA), Resistencia (Ω)

Incluir una fila de encabezado con formato negrita

Tener título (caption) llamado "Resultados experimentales"

Tener etiqueta (label) para referenciar

Usar líneas horizontales para separar encabezado y final
```

### 3. Generación de Documentos Completos

#### Prompt para informe de laboratorio
```text
Actúa como un asistente de LaTeX especializado en ingeniería electrónica.

Genera la estructura completa de un informe de laboratorio sobre
el "Circuito Rectificador de Media Onda" que incluya:

Portada profesional con:

Universidad: Universidad Nacional Tecnológica de Lima Sur

Facultad: Ingeniería Electrónica

Título del laboratorio

Espacio para nombre del estudiante y fecha

Índice automático (tableofcontents)

Sección de Objetivos (lista con 3 objetivos)

Sección de Marco Teórico con:

Explicación del rectificador

Ecuación: Vout = Vp - Vdiodo (numerada)

Ecuación: Vr = I/(2fC) (numerada)

Sección de Materiales (lista de 5 materiales)

Sección de Procedimiento (lista numerada con 5 pasos)

Sección de Resultados (tabla con 5 mediciones)

Sección de Conclusiones (lista con 3 conclusiones)

Bibliografía con 3 referencias en formato IEEE

Usa la clase article, configura el idioma español y comenta las
partes importantes del código.
```

### 4. Corrección de Errores

#### Prompt para depuración básica
```text
El siguiente código LaTeX tiene errores de compilación.
Identifica cada error, explica por qué ocurre y proporciona
el código corregido:
\began{ecuation}
\alfa>3*\psi+\amega
\ending{ecuation}
```

#### Prompt para optimización
```text

Revisa el siguiente documento LaTeX y sugiere 5 mejoras específicas para:

1.- Mejorar la estructura y organización
2.- Optimizar el formato de las ecuaciones
3.- Corregir posibles errores de estilo
4.- Recomendar paquetes adicionales útiles
5.- Mejorar la presentación general

Documento:
[pegar código aquí]

```

### 5. Generación de Diagramas TikZ

#### Prompt para circuitos
```text
Genera el código TikZ para dibujar un circuito amplificador
operacional inversor con los siguientes componentes:

R1 = 10kΩ en la entrada

R2 = 100kΩ en retroalimentación

Fuente de entrada Vin

Voltaje de salida Vout

Tierra

Usa la librería de circuitos de TikZ y formato profesional.
```
## Técnicas Avanzadas de Prompting

### 1. Encadenamiento de Prompts

En lugar de pedir todo de una vez, divide el trabajo en pasos:

**Paso 1:** 
```text
Genera solo la estructura de un artículo IEEE sobre filtros activos.
```

**Paso 2:** 
```text
Ahora, completa la sección de introducción del artículo anterior.
```

**Paso 3:** 
```text
Ahora, genera las ecuaciones para la sección de marco teórico.
```

### 2. Prompt con Ejemplos (Few-Shot)
```text
Genera el código LaTeX para la ecuación de potencia eléctrica
siguiendo EXACTAMENTE este formato de ejemplo:

EJEMPLO:
\begin{equation}
V = I \cdot R
\label{eq:ohm}
\end{equation}

Ahora genera para: P = V * I
```
