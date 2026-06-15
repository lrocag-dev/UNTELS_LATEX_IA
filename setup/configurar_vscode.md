# Configuración de VS Code para LaTeX con GitHub Copilot

## 📋 Requisitos Previos

- [Visual Studio Code](https://code.visualstudio.com) instalado
- [MiKTeX](https://miktex.org) o [TeX Live](https://tug.org/texlive) instalado
- [Git](https://git-scm.com) instalado (opcional, para control de versiones)
- Cuenta de GitHub (gratis para estudiantes)

## 🧩 Paso 1: Instalar Extensiones Necesarias

### 1.1 Abrir VS Code

1. Abre **Visual Studio Code**
2. Presiona `Ctrl+Shift+X` para abrir el mercado de extensiones

### 1.2 Instalar LaTeX Workshop

1. En la barra de búsqueda, escribe: `LaTeX Workshop`
2. Selecciona la extensión de **James-Yu**
3. Haz clic en **"Install"**

**Funcionalidades:**
- Resaltado de sintaxis
- Autocompletado básico
- Compilación automática
- Visor de PDF integrado
- Sincronización entre código y PDF

### 1.3 Instalar GitHub Copilot (para estudiantes)

1. En la barra de búsqueda, escribe: `GitHub Copilot`
2. Selecciona la extensión de **GitHub**
3. Haz clic en **"Install"**

### 1.4 Instalar GitHub Copilot Chat (opcional)

1. En la barra de búsqueda, escribe: `GitHub Copilot Chat`
2. Selecciona la extensión de **GitHub**
3. Haz clic en **"Install"**

### 1.5 Instalar GitLens (recomendado)

1. En la barra de búsqueda, escribe: `GitLens`
2. Selecciona la extensión de **GitKraken**
3. Haz clic en **"Install"**

**Funcionalidades:**
- Gestión avanzada de Git
- Historial de archivos
- Blame annotations

## 🔐 Paso 2: Configurar GitHub Copilot

### 2.1 Obtener acceso gratuito como estudiante

1. Ve a [GitHub Education](https://education.github.com)
2. Haz clic en **"Get benefits"**
3. Verifica tu estado de estudiante con tu correo institucional (`@untels.edu.pe`)
4. Una vez verificado, solicita **"GitHub Copilot Student Pack"**
5. Recibirás un correo de confirmación

### 2.2 Activar Copilot en VS Code

1. Abre VS Code
2. Presiona `Ctrl+Shift+P`
3. Escribe: `GitHub Copilot: Sign in`
4. Sigue las instrucciones en el navegador
5. Cuando termine, verás el ícono de Copilot en la barra inferior (✓)

### 2.3 Verificar que Copilot funciona

1. Crea un nuevo archivo `prueba.tex`
2. Escribe un comentario:
   ```latex
   % Crear una ecuación de la Ley de Ohm
   ```
   
   Copilot debería sugerir automáticamente:
   
   ```latex
   \begin{equation}
      V = I \cdot R
   \end{equation}
    ```
   Presiona `Tab` para aceptar la sugerencia

## Paso 3: Configurar LaTeX Workshop
### 3.1 Abrir configuración
1. Presiona Ctrl+Shift+P
2. Escribe: Preferences: Open Settings (JSON)
3.Se abrirá el archivo settings.json

### 3.2 Agregar configuración
Copia y pega el siguiente bloque dentro de las llaves `{}`:

```json
{
    // ============================================
    // CONFIGURACIÓN DE LATEX WORKSHOP
    // ============================================
    
    // Compilación automática al guardar
    "latex-workshop.latex.autoBuild.run": "onSave",
    
    // Directorio de archivos temporales
    "latex-workshop.latex.outDir": "build",
    
    // Limpiar archivos auxiliares
    "latex-workshop.latex.clean.enabled": true,
    "latex-workshop.latex.clean.fileTypes": [
        "*.aux", "*.bbl", "*.blg", "*.idx", "*.ind", 
        "*.lof", "*.lot", "*.out", "*.toc", "*.acn", 
        "*.acr", "*.alg", "*.glg", "*.glo", "*.gls", 
        "*.ist", "*.fls", "*.log", "*.fdb_latexmk", 
        "*.snm", "*.nav", "*.dvi", "*.synctex.gz"
    ],
    
    // Herramientas de compilación
    "latex-workshop.latex.tools": [
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "-outdir=build",
                "%DOC%"
            ]
        }
    ],
    
    // Recetas de compilación
    "latex-workshop.latex.recipes": [
        {
            "name": "latexmk",
            "tools": ["latexmk"]
        }
    ],
    
    // Visualización del PDF
    "latex-workshop.view.pdf.viewer": "tab",
    "latex-workshop.synctex.afterBuild.enabled": true,
    
    // ============================================
    // CONFIGURACIÓN DE GITHUB COPILOT
    // ============================================
    
    // Habilitar Copilot para todos los lenguajes
    "github.copilot.enable": {
        "*": true,
        "plaintext": false,
        "scminput": false
    },
    
    // Habilitar sugerencias de siguiente edición
    "github.copilot.nextEditSuggestions.enabled": true,
    
    // ============================================
    // CONFIGURACIÓN PARA LATEX (evita conflictos)
    // ============================================
    
    "[latex]": {
        "editor.quickSuggestions": {
            "comments": "off",
            "strings": "off",
            "other": "off"
        },
        "editor.suggestOnTriggerCharacters": false,
        "editor.tabCompletion": "off",
        "editor.formatOnSave": true
    },
    
    // Habilitar sugerencias inline de Copilot
    "editor.inlineSuggest.enabled": true
}
```
### 3.3 Guardar configuración
Presiona Ctrl+S para guardar el archivo `settings.json`

## Paso 4: Crear y Compilar un Documento
### 4.1 Crear un documento de prueba
1. En VS Code, crea un nuevo archivo: File → New File
2. Guarda como mi_documento.tex
3. Copia el siguiente código:

```latex
\documentclass[12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[spanish]{babel}
\usepackage{amsmath, amssymb}

\title{Mi Primer Documento en VS Code}
\author{Tu Nombre}
\date{\today}

\begin{document}

\maketitle

\section{Introducción}
Este es mi primer documento \LaTeX\ creado en VS Code.

\section{Ecuación de ejemplo}
\begin{equation}
    V = I \cdot R
    \label{eq:ohm}
\end{equation}

La ecuación \ref{eq:ohm} representa la Ley de Ohm.

\end{document}
```
### 4.2 Compilar el documento
- Método 1: Presiona Ctrl+Alt+B
- Método 2: Abre la paleta de comandos (Ctrl+Shift+P) → LaTeX Workshop: Build LaTeX project
- Método 3: Guarda el archivo (Ctrl+S) → compila automáticamente

### Ver el PDF
- El PDF se abrirá automáticamente en una pestaña junto al código
- Puedes ver el código y el PDF lado a lado

## 🔄 Paso 5: Sincronización entre Código y PDF
LaTeX Workshop permite hacer clic en el PDF y saltar al código correspondiente:

1. Abre el PDF en VS Code
2. Haz clic en cualquier parte del PDF mientras mantienes presionado Ctrl
3. El cursor saltará automáticamente a la línea correspondiente en el código

| Acción                        | Atajo             |
|-------------------------------|-------------------|
| Compilar documento            | Ctrl+Alt+B        |
| Ver PDF                       | Ctrl+Alt+V        |
| Sincronizar código-PDF        | Ctrl+Click en PDF |
| Aceptar sugerencia de Copilot | Tab               |
| Rechazar sugerencia           | Esc               |
| Abrir chat de Copilot         | Ctrl+Shift+I      |
| Paleta de comandos            | Ctrl+Shift+P      |

## Solución de Problemas
### Problema: LaTeX Workshop no compila
#### Verificar instalación de MiKTeX:

```bash
pdflatex --version
```
#### Verificar ruta de pdflatex:

1. Abre terminal en VS Code (`Ctrl+ñ`)
2. Ejecuta: `where pdflatex`
3. Debe mostrar la ruta de instalación

### Problema: Copilot no sugiere nada
1. Verifica que el ícono de Copilot en la barra inferior muestre ✓
2. Si muestra una línea diagonal, haz clic y selecciona "Enable Completions"
3. Verifica la autenticación: `Ctrl+Shift+P` → `GitHub Copilot: Sign in`

### Problema: Conflictos con autocompletado
Asegúrate de que la configuración `[latex]` esté presente en `settings.json` (ya la incluimos arriba).

#### Problema: La compilación es muy lenta
1. Abre MiKTeX Console
2. Ve a "Packages"
3. Busca `latexmk` e instálalo si no está

## Recursos Adicionales
- [LaTeX Workshop Documentation](https://github.com/James-Yu/LaTeX-Workshop)
- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [VS Code Tips and Tricks](https://code.visualstudio.com/docs/getstarted/tips-and-tricks)
