# Fundamentos de LaTeX + IA
## Duración: 2 horas
## Contenido Teórico (1 hora)
1.1 ¿Qué es LaTeX? (15 min)
- Diferencia entre LaTeX vs Word
- Ventajas: ecuaciones profesionales, referencias cruzadas, versionado
- Desventajas: curva de aprendizaje inicial

1.2 Estructura de un documento LaTeX (30 min)
```latex
\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage{amsmath, amssymb}

\title{Mi primer documento LaTeX}
\author{Estudiante Ingeniería Electrónica}
\date{\today}

\begin{document}

\maketitle

\section{Introducción}
LaTeX es excelente para documentos técnicos...

\end{document}
```
1.3 Herramientas de IA para LaTeX (30 min)
- ChatGPT: Generar código LaTeX desde lenguaje natural
- Overleaf AI: Explicar y corregir código
- GitHub Copilot: Autocompletado inteligente

1.4 Configuración del entorno (15 min)
- Opción 1: Overleaf (online, gratuito, con IA integrada)
- Opción 2: VS Code + LaTeX Workshop (offline, con Copilot)

## Práctica Guiada (1 hora)
### Ejemplo 1: Primer documento con ayuda de IA
### Prompt para ChatGPT:

```text
Quiero crear un documento LaTeX para mi curso de electrónica que incluya:
- Título: "Informe de Laboratorio N°1: Ley de Ohm"
- Autor: [tu nombre]
- Fecha: hoy
- Sección: Introducción (2 párrafos)
- Sección: Objetivos (lista)
- Sección: Marco Teórico (con ecuación V = I * R)

Genera el código completo.
```
### Ejemplo 2: Configurar Overleaf
1. Crear cuenta en overleaf.com
2. Crear nuevo proyecto
3. Pegar código generado por ChatGPT
4. Compilar y ver resultado

### Ejemplo 3: Usar IA para debuggear
#### Prompt para Overleaf AI:

```text
¿Por qué no compila mi código LaTeX?
[pegar código aquí]
```
### Ejercicios (1 hora)
| Ejercicio     | Descripción                                              | Dónde guardar             |
|---------------|----------------------------------------------------------|---------------------------|
| Ejercicio 1.1 | Crear documento con título, autor, fecha y 3 secciones   | ejercicios/ejercicio1.tex |
| Ejercicio 1.2 | Usar ChatGPT para generar documento sobre "Circuitos RC" | ejercicios/ejercicio2.tex |
| Ejercicio 1.3 | Configurar Overleaf y compartir enlace con el profesor   |                           |

## SESIÓN 2: Ecuaciones y Matemáticas con IA
### Duración: 1 hora
### Contenido Teórico (0.5 horas)
### 2.1 Sintaxis básica de ecuaciones (30 min)
```latex
% Modo inline: $E = mc^2$
% Modo display: $$E = mc^2$$ o \[E = mc^2\]

% Ecuaciones numeradas
\begin{equation}
    V = I \cdot R
\end{equation}

% Fracciones y raíces
\frac{V}{R} \quad \sqrt{R^2 + X^2}
```
#### 2.2 Matrices y sistemas de ecuaciones (30 min)
```latex
% Matriz
\begin{bmatrix}
    R_1+R_2 & -R_2 \\
    -R_2 & R_2+R_3
\end{bmatrix}

% Sistema de ecuaciones
\begin{cases}
    V_1 = I_1 R_1 + I_2 R_2 \\
    V_2 = I_2 R_2 + I_3 R_3
\end{cases}
```
#### 2.3 Fórmulas de electrónica (30 min)
```latex
% Ley de Ohm
$V = I \cdot R$

% Potencia
$P = V \cdot I = I^2 \cdot R = \frac{V^2}{R}$

% Reactancia capacitiva
$X_C = \frac{1}{2\pi f C}$

% Impedancia
$Z = \sqrt{R^2 + (X_L - X_C)^2}$

% Transformada de Laplace
$\mathcal{L}\{f(t)\} = F(s) = \int_0^\infty e^{-st} f(t) dt$
```
### Práctica Guiada (1 hora)
### Ejemplo 1: Usar Mathpix para convertir ecuaciones
1. Escribir ecuación a mano o tomar foto
2. Subir a mathpix.com
3. Copiar código LaTeX generado
4. Pegar en Overleaf

### Ejemplo 2: Usar ChatGPT para generar ecuaciones complejas
### Prompt:

```text
Genera el código LaTeX para la ley de voltajes de Kirchhoff en un 
circuito RLC serie con fuente de voltaje V(t). La ecuación debe ser 
numerada y usar formato profesional.
```
#### Respuesta esperada:

```latex
\begin{equation}
    V(t) = L\frac{di}{dt} + Ri + \frac{1}{C}\int i \, dt
    \label{eq:rlc_serie}
\end{equation}
```
### Ejemplo 3: Instalar LaTeX-OCR local (opcional)
```bash
pip install latex-ocr
latexocr
```
#### Ejercicios (1 hora)
|  Ejercicio	  |                Descripción                               |
|---------------|----------------------------------------------------------|
| Ejercicio 1	| Crear documento con 5 ecuaciones de electrónica (Ley de Ohm, Potencia, Reactancia, Impedancia, Frecuencia de corte)|
| Ejercicio 2 |	Escribir matriz de admitancias para un circuito de 2 nodos |
| Ejercicio 3 |	Usar Mathpix o ChatGPT para convertir imagen de ecuación a LaTeX |

## Tablas, Figuras y Diagramas con IA
### 3.1 Tablas en LaTeX (30 min)
```latex
\begin{table}[h]
\centering
\caption{Valores medidos vs teóricos}
\begin{tabular}{|c|c|c|}
\hline
\textbf{Componente} & \textbf{Valor Teórico} & \textbf{Valor Medido} \\
\hline
R1 & 100 Ω & 98.5 Ω \\
R2 & 220 Ω & 221.3 Ω \\
C1 & 10 μF & 9.8 μF \\
\hline
\end{tabular}
\label{tab:mediciones}
\end{table}
```
### 3.2 Figuras (30 min)
```latex
\usepackage{graphicx}
\graphicspath{{figuras/}}

\begin{figure}[h]
\centering
\includegraphics[width=0.7\textwidth]{circuito_rc.png}
\caption{Circuito RC serie}
\label{fig:circuito_rc}
\end{figure}
```
### 3.3 Diagramas de circuitos con TikZ (30 min)
```latex
\usepackage{tikz}
\usetikzlibrary{circuits.ee.IEC}

\begin{tikzpicture}[circuit ee IEC]
    \draw (0,0) to [resistor={info={R}}] (2,0)
                to [capacitor={info={C}}] (4,0)
                to [battery={info={V}}] (6,0);
\end{tikzpicture}
```
### Práctica Guiada (1.5 horas)
### Ejemplo 1: Generar tabla con IA
### Prompt para ChatGPT:

```text
Crea una tabla en LaTeX con los siguientes datos de un experimento de 
carga de capacitor:

Tiempo (ms): 0, 10, 20, 30, 40, 50
Voltaje (V): 0, 2.1, 3.5, 4.3, 4.7, 4.9

La tabla debe tener título y etiqueta.
``` 
### Ejemplo 2: Generar código TikZ con IA
### Prompt:

```text
Genera el código TikZ para dibujar un circuito amplificador operacional 
inversor con:
- R1 = 10kΩ en la entrada
- R2 = 100kΩ en retroalimentación
- Fuente de entrada Vin
- Voltaje de salida Vout
```
### Ejemplo 3: Diagramas de flujo con IA
### Prompt:

```text
Genera código LaTeX para un diagrama de flujo del proceso de medición:
- Inicio
- Medir voltaje
- ¿V > umbral? (Sí: Activar alarma, No: Continuar)
- Registrar datos
- Fin
````
#### Ejercicios (1 hora)
| Ejercicio     | Descripción                                              | 
|---------------|----------------------------------------------------------|
| Ejercicio 1 | Crear tabla de resultados de un experimento de ley de Ohm (5 mediciones)  |
| Ejercicio 2 | Insertar figura y referenciarla desde el texto |
| Ejercicio 3 | Dibujar circuito RC con TikZ o generar imagen con IA   |
