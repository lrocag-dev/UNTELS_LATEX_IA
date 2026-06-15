# Instalación de MiKTeX en Windows 11

## 📋 Requisitos Previos

- Windows 10 o Windows 11 (64 bits)
- Conexión a internet
- Al menos 2 GB de espacio libre en disco
- Permisos de administrador (recomendado)

## 📥 Paso 1: Descargar MiKTeX

1. Abre tu navegador web (Chrome, Edge o Firefox)

2. Ve a la página oficial de descarga:
   
[https://miktex.org/download](https://miktex.org/download)

4. Haz clic en el botón **"Download MiKTeX"**

5. Selecciona la versión **"Basic MiKTeX Installer"** (64-bit)
- El archivo se llamará algo como: `basic-miktex-23.12-x64.exe`

## ⚙️ Paso 2: Instalar MiKTeX

1. **Ejecutar el instalador**
- Haz doble clic en el archivo descargado
- Si aparece una advertencia de seguridad, haz clic en "Ejecutar de todas formas"

2. **Seleccionar tipo de instalación**
- ✅ Selecciona **"Install for all users"** (requiere permisos de administrador)
- 🔘 O selecciona **"Install for me only"** (no requiere administrador)

3. **Elegir directorio de instalación**
- Por defecto: `C:\Program Files\MiKTeX`
- Puedes cambiarlo si lo deseas
- Haz clic en **"Next"**

4. **Configuración de paquetes**
- En "Install missing packages on the fly" selecciona:
  - ✅ **"Yes"** (recomendado para principiantes)
- Esto permite que MiKTeX instale automáticamente paquetes cuando sean necesarios

5. **Configuración adicional**
- Deja las opciones por defecto
- Haz clic en **"Next"**

6. **Iniciar instalación**
- Haz clic en **"Start"**
- Espera a que termine la instalación (puede tomar varios minutos)

7. **Finalizar**
- Haz clic en **"Close"** o **"Finish"**

## 🔍 Paso 3: Verificar la instalación

1. Abre el **Símbolo del sistema (CMD)**:
- Presiona `Windows + R`
- Escribe `cmd` y presiona Enter

2. Ejecuta el siguiente comando:
```cmd
pdflatex --version
```
Resultado esperado:
```text
pdfTeX 3.141592653-2.6-1.40.25 (MiKTeX 23.12)
```
Si ves información similar, la instalación fue exitosa.

# Recursos Adicionales
- [Documentación oficial de MiKTeX](https://miktex.org/documentation)
- [MiKTeX Community Forum](https://miktex.org/support)
- [Guía rápida de LaTeX en español](https://mirror.utexas.edu/ctan/info/lshort/spanish/lshort-esp.pdf)

