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
