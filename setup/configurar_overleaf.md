# Configuración de Overleaf para LaTeX con IA

## 📋 Requisitos Previos

- Navegador web actualizado (Chrome, Edge, Firefox, Safari)
- Conexión a internet
- Correo electrónico (recomendado: correo institucional `@untels.edu.pe`)

## 🌐 Paso 1: Crear una cuenta en Overleaf

### 1.1 Acceder a Overleaf

1. Abre tu navegador
2. Ve a: [https://www.overleaf.com](https://www.overleaf.com)

### 1.2 Registrarse

1. Haz clic en **"Sign Up"** (botón azul en la esquina superior derecha)

2. **Opción recomendada para estudiantes:**
   - Haz clic en **"Sign up with Google"**
   - Usa tu correo institucional (`tu_nombre@untels.edu.pe`)

3. **Opción alternativa:**
   - Completa el formulario con tu nombre, correo y contraseña
   - Haz clic en **"Register"**

### 1.3 Verificar correo

1. Revisa tu bandeja de entrada (o spam)
2. Haz clic en el enlace de verificación enviado por Overleaf

## 🎓 Paso 2: Obtener beneficios de estudiante

Overleaf ofrece **cuenta Pro gratuita** para estudiantes y profesores.

### 2.1 Solicitar cuenta Pro

1. Ve a: [https://www.overleaf.com/edu](https://www.overleaf.com/edu)
2. Haz clic en **"Get 30-day free trial"** o **"Apply for student offer"**

### 2.2 Verificar estado de estudiante

1. Completa el formulario con:
   - Tu correo institucional (`@untels.edu.pe`)
   - Tu nombre completo
   - Institución: "Universidad Nacional Tecnológica de Lima Sur"

2. Haz clic en **"Apply"**

3. Recibirás un correo de confirmación (puede tomar 1-2 días)

### 2.3 Beneficios de la cuenta Pro

| Característica | Gratis | Pro |
|----------------|--------|-----|
| AI Assistant | Limitado | ✅ Ilimitado |
| Colaboración | Público | ✅ Privado + invitados |
| Compilación | 20 segundos | ✅ 60 segundos |
| Historial de versiones | 1 día | ✅ 30 días |

## 🤖 Paso 3: Conocer el AI Assistant de Overleaf

### 3.1 ¿Qué es el AI Assistant?

Overleaf tiene un asistente de IA integrado que puede:
- Generar código LaTeX a partir de descripciones
- Corregir errores de compilación
- Sugerir mejoras de formato
- Explicar comandos de LaTeX

### 3.2 Activar AI Assistant

1. En un proyecto de Overleaf, busca el ícono **"AI"** en la barra lateral izquierda
2. Haz clic para abrir el panel de IA
3. Para usar el asistente, escribe tu pregunta o instrucción

## 📄 Paso 4: Crear tu Primer Proyecto

### 4.1 Crear proyecto en blanco

1. En el panel principal, haz clic en **"New Project"**
2. Selecciona **"Blank Project"**
3. Asigna un nombre: `Mi Primer Documento`

### 4.2 Explorar la interfaz
![interfaz overleaft](/setup/overleaft.png)
### 4.3 Escribir código básico

En el editor, reemplaza el contenido con:

```latex
\documentclass[12pt]{article}
\usepackage[utf8]{inputenc}
\usepackage[spanish]{babel}
\usepackage{amsmath, amssymb}

\title{Mi Primer Documento en Overleaf}
\author{Tu Nombre}
\date{\today}

\begin{document}

\maketitle

\section{Introducción}
¡Bienvenido a Overleaf! Este es mi primer documento.

\section{Ecuación de ejemplo}
\begin{equation}
    V = I \cdot R
    \label{eq:ohm}
\end{equation}

La ecuación \ref{eq:ohm} representa la Ley de Ohm.

\end{document}

### Compilar el documento
- El documento se compila automáticamente mientras escribes
- La vista previa del PDF se actualiza en tiempo real en el panel derecho
- También puedes compilar manualmente con `Ctrl+Enter`
