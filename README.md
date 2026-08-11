# 🟢 Luigi Theme Assistant

**Luigi Theme Assistant** es un sistema de temas para Windows que permite cambiar fácilmente el aspecto y el ambiente del escritorio mediante temas personalizados.

Cada tema puede tener:

- 🖼️ Un fondo de escritorio personalizado.
- 🎵 Música de fondo.
- 🖥️ Un icono personalizado en el área de notificaciones.
- ▶️ Controles para reproducir la música.
- ⏸️ Controles para pausar y reanudar la música.
- ⏹️ Controles para detener la música.
- ❌ Una opción para cerrar el tema.

La idea es que instalar un tema sea tan sencillo como **meter su carpeta dentro de `Themes`**.

---

# ✨ Características

- 🎨 Detección automática de temas.
- 📁 Instalación de temas mediante carpetas.
- 🎵 Música de fondo en bucle.
- 🖼️ Cambio automático del fondo de escritorio.
- 🟢 Icono personalizado en el área de notificaciones.
- ▶️ Reproducir música.
- ⏸️ Pausar y reanudar música.
- ⏹️ Detener música.
- ❌ Cerrar el tema.
- 🐍 Detección automática de Python.
- 📄 Guardado automático de la ruta de Python.
- 🖥️ Diseñado para Windows.
- 📦 El programa principal se distribuye como `.exe`.

---

# 📦 Requisitos

Para utilizar Luigi Theme Assistant necesitas:

- Windows.
- Python **3.10.11 o una versión superior**.
- `python.exe`.
- `pythonw.exe`.
- Las siguientes librerías de Python:
  - `pygame`
  - `pystray`
  - `Pillow`

> **Importante:** se recomienda utilizar una versión de Python superior a 3.10.11 para asegurar la compatibilidad.

---

# 🐍 Instalación de Python

Si no tienes Python instalado, primero debes instalarlo.

Durante la instalación de Python se recomienda activar la opción:

```text
Add Python to PATH
```

Después de instalarlo, abre una ventana de **CMD** y escribe:

```bat
python --version
```

También puedes comprobar:

```bat
pythonw --version
```

Si ambos comandos funcionan y muestran una versión de Python igual o superior a 3.10.11, puedes continuar.

---

# 📚 Instalación de las librerías

Abre CMD y ejecuta:

```bat
python -m pip install pygame pystray Pillow
```

Espera a que termine la instalación.

Una vez instaladas las librerías, Luigi Theme Assistant podrá ejecutar los temas.

---

# 🚀 Instalación de Luigi Theme Assistant

Descarga la versión de Luigi Theme Assistant que quieras utilizar.

La estructura principal debería quedar parecida a esta:

```text
Luigi Theme Assistant/
│
├── Luigi Theme Assistant.exe
├── Luigi_Theme_Assistant.exe
├── icon.png
│
├── config/
│
└── Themes/
```

El archivo que debes ejecutar normalmente es:

```text
Luigi Theme Assistant.exe
```

Este archivo funciona como **launcher**.

El launcher inicia:

```text
Luigi_Theme_Assistant.exe
```

---

# ⚙️ ¿Qué hace Luigi_Theme_Assistant.exe?

`Luigi_Theme_Assistant.exe` es el programa principal.

Cuando se inicia:

1. Busca una instalación válida de Python.
2. Comprueba `python.exe`.
3. Comprueba `pythonw.exe`.
4. Guarda sus rutas.
5. Busca la carpeta `Themes`.
6. Busca los temas disponibles.
7. Crea el menú del área de notificaciones.
8. Permite seleccionar y ejecutar los temas.

---

# 📄 ruta_python.json

Luigi Theme Assistant guarda automáticamente las rutas de Python en:

```text
config/ruta_python.json
```

Por ejemplo:

```json
{
    "python": "C:\\Users\\Usuario\\AppData\\Local\\Programs\\Python\\Python312\\python.exe",
    "pythonw": "C:\\Users\\Usuario\\AppData\\Local\\Programs\\Python\\Python312\\pythonw.exe"
}
```

Las rutas serán diferentes dependiendo del ordenador.

## ¿Tengo que crear este archivo?

**No.**

Luigi Theme Assistant lo crea automáticamente.

Tampoco necesitas escribir manualmente la ruta de Python dentro del programa.

Esto permite que Luigi Theme Assistant funcione en diferentes ordenadores sin tener que modificar el código para cada instalación.

---

# 🎨 Crear tu propio tema

Una de las partes principales de Luigi Theme Assistant es que puedes crear tus propios temas.

No necesitas modificar Luigi Theme Assistant para hacerlo.

---

## 1. Crea una carpeta dentro de `Themes`

Ve a:

```text
Themes/
```

Y crea una carpeta con el nombre que quieras.

Por ejemplo:

```text
Themes/
└── Mi Tema/
```

El nombre de esta carpeta será el nombre que aparecerá en el menú de Luigi Theme Assistant.

Por ejemplo:

```text
Themes/
├── Super Mario Galaxy The Movie/
├── Super Mario Lofi/
└── Mi Tema/
```

---

# 🖼️ 2. Consigue una imagen `.png`

Busca o crea una imagen que quieras utilizar como fondo de escritorio.

Debe ser un archivo `.png`.

Colócala dentro de la carpeta del tema y llámala exactamente:

```text
background.png
```

> **Importante:** `background.png` está escrito así intencionadamente. El programa utiliza exactamente ese nombre.

La carpeta quedaría:

```text
Mi Tema/
└── background.png
```

---

# 🎵 3. Consigue un archivo de audio `.wav`

Ahora necesitas un archivo de audio para la música de fondo.

Debe ser un archivo:

```text
.wav
```

Renómbralo exactamente:

```text
bgm.wav
```

Y colócalo dentro de la carpeta del tema.

Ahora tendremos:

```text
Mi Tema/
├── background.png
└── bgm.wav
```

La música se reproducirá automáticamente cuando se active el tema.

Además, se reproducirá en bucle.

---

# 🟢 4. Consigue un icono `.png`

El tema también necesita un icono para el área de notificaciones de Windows.

Consigue una imagen `.png` y llámala:

```text
icon.png
```

Colócala dentro de la carpeta.

Ahora tendremos:

```text
Mi Tema/
├── background.png
├── bgm.wav
└── icon.png
```

---

# 🐍 5. Crea `config_desktop.py`

Ahora crea un archivo Python llamado exactamente:

```text
config_desktop.py
```

Colócalo dentro de la carpeta del tema.

La estructura final será:

```text
Mi Tema/
├── config_desktop.py
├── bgm.wav
├── background.png
└── icon.png
```

---

# 💻 Código de `config_desktop.py`

Copia exactamente este código dentro de `config_desktop.py`:

```python
import pygame
import pystray
from PIL import Image
from pystray import MenuItem as item
import ctypes
import os

# =========================
# CONFIGURACIÓN
# =========================

CARPETA = os.path.dirname(os.path.abspath(__file__))

MUSICA = os.path.join(CARPETA, "bgm.wav")
FONDO = os.path.join(CARPETA, "background.png")

# =========================
# FONDO
# =========================

ctypes.windll.user32.SystemParametersInfoW(
    20,
    0,
    FONDO,
    3
)

# =========================
# PYGAME
# =========================

pygame.mixer.init()
pygame.mixer.music.load(MUSICA)
pygame.mixer.music.play(-1)

pausada = False

# =========================
# CONTROLES
# =========================

def pausar_reanudar(icon=None, item=None):
    global pausada

    if pausada:
        pygame.mixer.music.unpause()
        pausada = False
    else:
        pygame.mixer.music.pause()
        pausada = True

    icon.update_menu()


def detener(icon=None, item=None):
    pygame.mixer.music.stop()


def reproducir(icon=None, item=None):
    pygame.mixer.music.play(-1)


def salir(icon=None, item=None):
    pygame.mixer.music.stop()
    pygame.mixer.quit()
    icon.stop()


# =========================
# ICONO
# =========================

ICONO = os.path.join(CARPETA, "icon.png")

imagen = Image.open(ICONO)

# =========================
# MENÚ DE LA BANDEJA
# =========================

menu = pystray.Menu(
    item(
        "▶ Reproducir",
        reproducir
    ),
    item(
        "⏸ Pausar / Reanudar",
        pausar_reanudar
    ),
    item(
        "⏹ Detener",
        detener
    ),
    pystray.Menu.SEPARATOR,
    item(
        "❌ Salir",
        salir
    )
)

# =========================
# ICONO DE LA BANDEJA
# =========================

icono = pystray.Icon(
    "Desktop Music",
    imagen,
    "Settings Desktop Music",
    menu
)

# =========================
# EJECUTAR
# =========================

icono.run()
```

---

# 📁 Estructura final de un tema

Cuando hayas terminado, tu tema debería tener exactamente esta estructura:

```text
Themes/
└── Mi Tema/
    │
    ├── config_desktop.py
    ├── bgm.wav
    ├── background.png
    └── icon.png
```

No necesitas añadir nada más.

---

# 🎮 Instalar un tema descargado

Si alguien comparte contigo un tema, normalmente tendrás una carpeta parecida a:

```text
Super Luigi Theme/
├── config_desktop.py
├── bgm.wav
├── background.png
└── icon.png
```

Para instalarlo:

### 1. Copia la carpeta completa.

### 2. Ve a:

```text
Luigi Theme Assistant/Themes/
```

### 3. Pega la carpeta ahí.

Por ejemplo:

```text
Luigi Theme Assistant/
└── Themes/
    └── Super Luigi Theme/
        ├── config_desktop.py
        ├── bgm.wav
        ├── background.png
        └── icon.png
```

### 4. Ejecuta Luigi Theme Assistant.

El tema debería aparecer automáticamente en el menú.

---

# 🖱️ Utilizar un tema

Cuando Luigi Theme Assistant esté ejecutándose, aparecerá su icono en el **área de notificaciones de Windows**.

Haz clic derecho sobre el icono.

Aparecerá una lista con los temas disponibles.

Por ejemplo:

```text
Super Mario Galaxy The Movie
Super Mario Lofi
Mi Tema
-------------------------
❌ Salir
```

Selecciona el tema que quieras.

Luigi Theme Assistant:

1. Detendrá el tema anterior.
2. Ejecutará el nuevo `config_desktop.py`.
3. Cambiará el fondo.
4. Comenzará la música.
5. Mostrará el icono del nuevo tema.

---

# 🎵 Controles de música

Al hacer clic derecho sobre el icono del tema en el área de notificaciones encontrarás:

```text
▶ Reproducir
⏸ Pausar / Reanudar
⏹ Detener
-------------------------
❌ Salir
```

### ▶ Reproducir

Inicia la música.

### ⏸ Pausar / Reanudar

Pausa la música o la vuelve a reproducir desde donde estaba.

### ⏹ Detener

Detiene completamente la música.

### ❌ Salir

Cierra el tema y detiene la música.

---

# 🛠️ Solución de problemas

## ❌ Mi tema no aparece

Comprueba que la carpeta esté dentro de:

```text
Themes/
```

Y que contenga:

```text
config_desktop.py
```

Por ejemplo:

```text
Themes/
└── Mi Tema/
    └── config_desktop.py
```

El nombre debe ser exactamente:

```text
config_desktop.py
```

---

## ❌ No se reproduce la música

Comprueba que el archivo se llame:

```text
bgm.wav
```

y que esté dentro de la carpeta del tema.

También puedes comprobar que Pygame esté instalado:

```bat
python -m pip install pygame
```

---

## ❌ No cambia el fondo

Comprueba que el archivo se llame exactamente:

```text
background.png
```

y que esté en la misma carpeta que:

```text
config_desktop.py
```

---

## ❌ No aparece el icono

Comprueba que tengas:

```text
icon.png
```

dentro de la carpeta del tema.

También asegúrate de que el archivo sea realmente un PNG.

---

## ❌ Python no se detecta

Prueba en CMD:

```bat
python --version
```

y:

```bat
pythonw --version
```

Si Python no aparece, vuelve a instalar Python y activa:

```text
Add Python to PATH
```

Después instala las librerías:

```bat
python -m pip install pygame pystray Pillow
```

---

# ⚠️ Importante al crear temas

Los nombres de los archivos son importantes.

Actualmente Luigi Theme Assistant espera:

```text
config_desktop.py
bgm.wav
background.png
icon.png
```

No los cambies.

Por ejemplo, esto podría causar problemas:

```text
backround.png
```

❌ Incorrecto.

Debe ser:

```text
background.png
```

---

# 📌 No utilices rutas absolutas

No debes escribir rutas específicas de tu ordenador como:

```text
C:\Users\TuNombre\Desktop\Mi Tema\bgm.wav
```

El código proporcionado utiliza:

```python
CARPETA = os.path.dirname(os.path.abspath(__file__))
```

Esto hace que el tema encuentre sus archivos dentro de su propia carpeta.

Por eso puedes compartir la carpeta del tema con otras personas sin tener que modificar las rutas.

---

# 🧩 ¿Cómo funciona el sistema?

Luigi Theme Assistant está dividido en dos programas principales.

## `Luigi Theme Assistant.exe`

Es el **launcher**.

Es el archivo que el usuario ejecuta normalmente.

Su función es iniciar:

```text
Luigi_Theme_Assistant.exe
```

---

## `Luigi_Theme_Assistant.exe`

Es el programa principal.

Se encarga de:

- Detectar Python.
- Guardar las rutas de Python.
- Buscar los temas.
- Crear el menú del área de notificaciones.
- Ejecutar los temas.
- Cambiar entre temas.
- Cerrar los temas anteriores.

---

# 📂 Estructura completa recomendada

Una instalación completa puede tener esta estructura:

```text
Luigi Theme Assistant/
│
├── Luigi Theme Assistant.exe
├── Luigi_Theme_Assistant.exe
├── icon.png
│
├── config/
│   └── ruta_python.json
│
└── Themes/
    │
    ├── Super Mario Galaxy The Movie/
    │   ├── config_desktop.py
    │   ├── bgm.wav
    │   ├── background.png
    │   └── icon.png
    │
    ├── Super Mario Lofi/
    │   ├── config_desktop.py
    │   ├── bgm.wav
    │   ├── background.png
    │   └── icon.png
    │
    └── Mi Tema/
        ├── config_desktop.py
        ├── bgm.wav
        ├── background.png
        └── icon.png
```

---

# ✅ Lista rápida para crear un tema

Antes de compartir tu tema, comprueba que tengas:

```text
☐ config_desktop.py
☐ bgm.wav
☐ background.png
☐ icon.png
```

Y que estén todos dentro de una única carpeta:

```text
Themes/
└── Mi Tema/
    ├── config_desktop.py
    ├── bgm.wav
    ├── background.png
    └── icon.png
```

---

# 🚀 Crear un tema desde cero — resumen

Si quieres crear un tema rápidamente:

### 1. Crea una carpeta dentro de `Themes`

```text
Themes/Mi Tema/
```

### 2. Añade el fondo

```text
background.png
```

### 3. Añade la música

```text
bgm.wav
```

### 4. Añade el icono

```text
icon.png
```

### 5. Crea el archivo Python

```text
config_desktop.py
```

### 6. Copia el código proporcionado anteriormente.

### 7. Instala Python y las librerías necesarias.

### 8. Ejecuta Luigi Theme Assistant.

### 9. Busca tu tema en el menú.

### 10. Selecciónalo y disfruta de tu nuevo tema. 🟢🎵

---

# 🟢 Luigi Theme Assistant

**Crea tus propios temas. Compártelos. Personaliza tu escritorio.**

🎨 🖼️ 🎵 🟢

**Si te a gustado agradecería que me dieras una estrella**
