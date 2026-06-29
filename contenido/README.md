# Fundamentos de LaTeX + IA
## Duración: 2 horas
## 🛠️ Herramientas necesarias
- [Overleaf](https://www.overleaf.com) (recomendado) o
- [VS Code](https://code.visualstudio.com) + LaTeX Workshop
- [ChatGPT](https://chat.openai.com)
- [Mathpix](https://mathpix.com) (opcional)
- [Generador de tablas](https://www.tablesgenerator.com/markdown_tables#)
- [Detexify](https://detexify.kirelabs.org)
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

## Ecuaciones y Matemáticas con IA
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

## Documento Completo + IA Avanzada
#### 4.1 Estructura de documento profesional (30 min)
```latex
\documentclass[12pt,letterpaper]{article}
\usepackage[spanish]{babel}
\usepackage{geometry}
\geometry{margin=1in}

% Secciones del documento
\begin{document}
\tableofcontents
\listoffigures
\listoftables

\section{Introducción}
\subsection{Antecedentes}
\subsection{Objetivos}

\section{Marco Teórico}

\section{Metodología}

\section{Resultados}

\section{Conclusiones}

\bibliographystyle{ieeetr}
\bibliography{referencias}

\end{document}
```
### 4.2 Referencias bibliográficas con BibTeX (30 min)
```latex
% archivo: referencias.bib
@book{boylestad2022,
    title={Electrónica: Teoría de circuitos},
    author={Boylestad, Robert L.},
    year={2022},
    publisher={Pearson}
}

@article{floyd2020,
    title={Dispositivos electrónicos},
    author={Floyd, Thomas L.},
    journal={Pearson Educación},
    year={2020}
}

% Citar en el documento
Según Boylestad \cite{boylestad2022}, ...
```
### 4.3 Plantilla para informe de laboratorio (30 min)
```latex
\documentclass[12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage{amsmath,amssymb,amsfonts}
\usepackage{graphicx}
\usepackage{float}
\usepackage[margin=1in]{geometry}

% Información del laboratorio
\newcommand{\labnum}{1}
\newcommand{\labtema}{Ley de Ohm y Kirchhoff}
\newcommand{\autor}{Estudiante: [Nombre]}
\newcommand{\fecha}{\today}

\begin{document}

\begin{titlepage}
    \centering
    {\Large UNIVERSIDAD NACIONAL TECNOLÓGICA DE LIMA SUR\par}
    \vspace{1cm}
    {\Large Facultad de Ingeniería Electrónica\par}
    \vspace{2cm}
    {\Huge \textbf{Informe de Laboratorio N°\labnum}\par}
    {\huge \textbf{\labtema}\par}
    \vspace{2cm}
    {\large \autor\par}
    {\large \fecha\par}
\end{titlepage}

\section{Objetivos}
\begin{itemize}
    \item Verificar experimentalmente la Ley de Ohm.
    \item Comprobar las Leyes de Kirchhoff en circuitos serie-paralelo.
\end{itemize}

\section{Materiales y Equipos}
\begin{itemize}
    \item Fuente de voltaje DC (0-30V)
    \item Multímetro digital
    \item Resistencias: 100Ω, 220Ω, 330Ω, 470Ω, 1kΩ
    \item Protoboard y cables
\end{itemize}

\section{Marco Teórico}
\subsection{Ley de Ohm}
La Ley de Ohm establece que la corriente que circula por un conductor es directamente proporcional al voltaje aplicado e inversamente proporcional a la resistencia:
\begin{equation}
    I = \frac{V}{R}
    \label{eq:ohm}
\end{equation}

\subsection{Leyes de Kirchhoff}
\begin{itemize}
    \item \textbf{LCK:} La suma de corrientes que entran a un nodo es igual a la suma de corrientes que salen.
    \item \textbf{LVK:} La suma de voltajes en una malla cerrada es igual a cero.
\end{itemize}

\section{Procedimiento Experimental}
\begin{enumerate}
    \item Medir el valor real de cada resistencia usando el multímetro.
    \item Armar el circuito de la Figura \ref{fig:circuito1}.
    \item Aplicar voltajes de 1V, 3V, 5V, 7V y 9V.
    \item Medir corriente y voltaje en cada elemento.
\end{enumerate}

\begin{figure}[H]
    \centering
    \includegraphics[width=0.5\textwidth]{circuito_serie.png}
    \caption{Circuito serie para verificar ley de Ohm}
    \label{fig:circuito1}
\end{figure}

\section{Resultados}
\begin{table}[H]
    \centering
    \caption{Mediciones realizadas}
    \begin{tabular}{|c|c|c|c|}
        \hline
        \textbf{V entrada (V)} & \textbf{V resistencia (V)} & \textbf{Corriente (mA)} & \textbf{Resistencia calculada (Ω)} \\
        \hline
        1.0 & 0.99 & 9.8 & 101.0 \\
        3.0 & 2.98 & 29.5 & 101.0 \\
        5.0 & 4.97 & 49.2 & 101.0 \\
        7.0 & 6.96 & 68.9 & 101.0 \\
        9.0 & 8.95 & 88.6 & 101.0 \\
        \hline
    \end{tabular}
    \label{tab:resultados}
\end{table}

\section{Análisis de Resultados}
Los resultados muestran una relación lineal entre voltaje y corriente, con una pendiente que corresponde a la resistencia del circuito (aproximadamente 101Ω), confirmando la Ley de Ohm.

\section{Conclusiones}
\begin{itemize}
    \item Se verificó experimentalmente la Ley de Ohm.
    \item El error porcentual entre valores teóricos y medidos fue menor al 2\%.
    \item La adquisición de datos digitales permite un análisis más preciso.
\end{itemize}

\section{Referencias}
\begin{thebibliography}{9}
\bibitem{ohm}
    Ohm, G. S. (1827). \textit{Die galvanische Kette, mathematisch bearbeitet}.
\bibitem{floyd}
    Floyd, T. L. (2020). \textit{Principios de circuitos eléctricos}. Pearson.
\end{thebibliography}

\end{document}
```
### Práctica Guiada con IA (1 hora)
### Ejemplo 1: Generar informe completo con ChatGPT
### Prompt:

```text
Quiero elaborar un informe de laboratorio sobre "Respuesta transitoria 
de un circuito RC" que incluya:

1. Portada profesional
2. Índice automático
3. 5 secciones: Introducción, Marco Teórico (con ecuación Vc(t)=Vin(1-e^-t/τ)), 
   Metodología, Resultados (tabla de 5 mediciones), Conclusiones
4. Al menos 2 figuras referenciadas
5. Bibliografía con 3 referencias

Genera el código LaTeX completo, bien estructurado y listo para compilar.
```
### Ejemplo 2: Revisión y corrección con IA
### Prompt para Overleaf AI:

```text
Revisa mi documento LaTeX y sugiere mejoras para:
- Mejorar la redacción académica
- Corregir errores gramaticales
- Optimizar el formato de las ecuaciones
- Sugerir referencias bibliográficas relevantes
```
### Ejemplo 3: Traducción automática
### Prompt:

```text
Traduce este párrafo al inglés manteniendo el formato LaTeX:
[pegar texto en español]
```
## Proyecto Final (1 hora)
### Enunciado:
Elaborar un documento completo en LaTeX sobre un tema de ingeniería electrónica asignado, utilizando herramientas de IA para:

- Generación de contenido (ChatGPT)
- Creación de ecuaciones (Mathpix)
- Diagramas de circuitos (TikZ con IA)
- Tablas de datos
- Bibliografía (BibTeX)
- Revisión gramatical (Grammarly/IA)

Temas sugeridos:

- Análisis de circuitos RLC
- Amplificadores operacionales
- Fuentes de alimentación
- Filtros activos
- Circuitos con diodos

## Prompts de IA útiles para cada sesión

### Prompt para crear plantilla
```text
Actúa como un experto en LaTeX. Genera una plantilla de documento 
para un estudiante de ingeniería electrónica que incluya:
- Portada personalizable
- Secciones predefinidas (Introducción, Desarrollo, Conclusiones)
- Configuración en español
- Comentarios explicativos para cada parte
```
### Prompt para debuggear
```text
Mi código LaTeX no compila. El error es: [pegar error]. 
¿Qué significa y cómo lo soluciono?
Sesión 2 - Ecuaciones
```
### Prompt para ecuaciones complejas
```text
Genera el código LaTeX para la ecuación de transferencia de un 
filtro pasa bajos de segundo orden: H(s) = ω₀²/(s² + (ω₀/Q)s + ω₀²). 
La ecuación debe ser numerada y usar notación profesional.
```
### Prompt para matrices
```text
Genera la matriz de admitancias para un circuito de 3 nodos 
usando notación de electrónica.
```
### Prompt para tablas
```text
Crea una tabla en LaTeX con datos de un experimento de 
diodo semiconductor. Incluye: Voltaje directo (V), Corriente (mA), 
y Resistencia dinámica (Ω). Usa 8 mediciones.
```
### Prompt para circuitos
```text
Genera código TikZ para un circuito rectificador de media onda 
con transformador, diodo y carga resistiva.
```
### Prompt para generar informe
```text
Elabora un informe de laboratorio completo en LaTeX sobre 
[especificar tema]. Incluye todos los elementos de un 
documento académico profesional.
```
## Prompt para revisión
```text
Revisa este documento LaTeX y sugiere 5 mejoras específicas 
para hacerlo más profesional: [pegar código]
```
