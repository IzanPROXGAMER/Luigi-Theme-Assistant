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
- 🔧 Los temas utilizan Python y sus propias dependencias.

---

# 📦 Requisitos

Para utilizar Luigi Theme Assistant necesitas:

- Windows.
- Python **3.10.11 o una versión superior**.
- `python.exe`.
- `pythonw.exe`.
- `pygame`.
- `pystray`.
- `Pillow`.

> **Importante:** las librerías `pygame`, `pystray` y `Pillow` son necesarias para ejecutar los archivos `config_desktop.py` de los temas.

---

# 🐍 Instalación de Python

Si no tienes Python instalado, primero debes instalarlo.

Se recomienda utilizar una versión de Python **superior a 3.10.11** para asegurar la compatibilidad.

Durante la instalación de Python se recomienda activar:

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

# 📚 Instalar las librerías necesarias

Los temas incluidos en Luigi Theme Assistant utilizan:

- `pygame`
- `pystray`
- `Pillow`

Para instalarlas, abre **CMD** y ejecuta:

```bat
python -m pip install pygame pystray Pillow
```

Espera a que termine la instalación.

Una vez instaladas, los `config_desktop.py` de los temas podrán ejecutarse correctamente.

> **Importante:** estas librerías son necesarias para los temas porque sus archivos `config_desktop.py` se ejecutan directamente con Python.

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

El programa principal está compilado como `.exe`.

Sus propias dependencias se incluyen durante la compilación.

Sin embargo, esto **no significa que las dependencias utilizadas por los temas estén incluidas en Python**.

Los temas se ejecutan por separado mediante `pythonw.exe`.

---

# 🧩 Diferencia entre el Assistant y los temas

Luigi Theme Assistant funciona mediante varios componentes.

## `Luigi Theme Assistant.exe`

Es el **launcher**.

Es el programa que el usuario ejecuta normalmente.

Su función principal es iniciar:

```text
Luigi_Theme_Assistant.exe
```

El launcher utiliza principalmente módulos incluidos en Python, como:

```python
import os
import subprocess
```

---

## `Luigi_Theme_Assistant.exe`

Es el programa principal del sistema.

Se encarga de:

- Detectar Python.
- Guardar las rutas de Python.
- Buscar los temas.
- Crear el menú del área de notificaciones.
- Ejecutar los temas.
- Cambiar entre temas.
- Detener el tema anterior.

Este programa está compilado como `.exe`.

---

## `config_desktop.py`

Este archivo pertenece a cada tema.

A diferencia del Assistant, normalmente **no se ejecuta como un `.exe`**.

Luigi Theme Assistant lo ejecuta mediante:

```text
pythonw.exe
```

Por eso las librerías utilizadas por el tema tienen que estar instaladas en Python.

Por ejemplo, el `config_desktop.py` proporcionado utiliza:

```python
import pygame
import pystray
from PIL import Image
```

Por tanto, Python debe tener instalados:

```text
pygame
pystray
Pillow
```

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

Esto permite que Luigi Theme Assistant funcione en diferentes ordenadores sin tener que modificar manualmente las rutas.

Si la ruta guardada deja de funcionar, Luigi Theme Assistant intentará detectar Python de nuevo.

---

# 🎨 Crear tu propio tema

Una de las partes principales de Luigi Theme Assistant es que puedes crear tus propios temas.

No necesitas modificar Luigi Theme Assistant para hacerlo.

La creación de un tema es manual y consiste en crear una carpeta dentro de `Themes` y colocar dentro los archivos necesarios.

---

# 📁 Estructura de un tema

Cada tema necesita cuatro archivos:

```text
config_desktop.py
bgm.wav
background.png
icon.png
```

Por tanto, un tema completo tendrá esta estructura:

```text
Mi Tema/
├── config_desktop.py
├── bgm.wav
├── background.png
└── icon.png
```

---

# 1️⃣ Crear la carpeta del tema

Abre:

```text
Themes/
```

Crea una nueva carpeta y ponle el nombre que quieras.

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

# 2️⃣ Añadir el fondo de escritorio

Consigue una imagen que quieras utilizar como fondo de escritorio.

Debe ser un archivo:

```text
.png
```

Colócala dentro de la carpeta del tema y llámala exactamente:

```text
background.png
```

Por ejemplo:

```text
Mi Tema/
└── background.png
```

> **Importante:** el nombre debe ser exactamente `background.png`.

---

# 3️⃣ Añadir la música

Necesitas un archivo de audio para la música de fondo.

Debe estar en formato:

```text
.wav
```

Renómbralo exactamente:

```text
bgm.wav
```

Colócalo dentro de la carpeta del tema.

Ahora tendrás:

```text
Mi Tema/
├── background.png
└── bgm.wav
```

La música comenzará automáticamente cuando se active el tema y se reproducirá en bucle.

---

# 4️⃣ Añadir el icono

Cada tema también necesita un icono que aparecerá en el área de notificaciones de Windows.

Consigue o crea una imagen `.png`.

Renómbrala:

```text
icon.png
```

Colócala dentro de la carpeta del tema.

Ahora tendrás:

```text
Mi Tema/
├── background.png
├── bgm.wav
└── icon.png
```

---

# 5️⃣ Crear config_desktop.py

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

# 🐍 Código de config_desktop.py

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

> **Importante:** no cambies la indentación del código. Python utiliza la indentación para determinar qué instrucciones pertenecen a cada función.

---

# 📁 Estructura final de tu tema

Cuando hayas terminado todos los pasos:

```text
Themes/
└── Mi Tema/
    │
    ├── config_desktop.py
    ├── bgm.wav
    ├── background.png
    └── icon.png
```

---

# 🎮 Instalar un tema descargado

Si alguien comparte contigo un tema, normalmente recibirás una carpeta parecida a:

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

### 3. Pega la carpeta dentro.

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
3. Cambiará el fondo de escritorio.
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

## ▶ Reproducir

Inicia la música del tema.

## ⏸ Pausar / Reanudar

Pausa la música o la vuelve a reproducir desde donde estaba.

## ⏹ Detener

Detiene completamente la música.

## ❌ Salir

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

El archivo debe llamarse exactamente:

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

Comprueba también que no sea realmente:

```text
bgm.wav.wav
```

Windows puede ocultar las extensiones conocidas.

Si el problema continúa, comprueba que `pygame` esté instalado:

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

La estructura debe ser:

```text
Mi Tema/
├── config_desktop.py
└── background.png
```

---

## ❌ No aparece el icono

Comprueba que tengas:

```text
icon.png
```

dentro de la carpeta del tema.

También asegúrate de que sea realmente una imagen PNG válida.

---

## ❌ Python no se detecta

Abre CMD y prueba:

```bat
python --version
```

y:

```bat
pythonw --version
```

Si Python no aparece, vuelve a instalar Python.

Durante la instalación activa:

```text
Add Python to PATH
```

Después vuelve a iniciar Luigi Theme Assistant.

---

## ❌ Falta una librería al ejecutar un tema

Si aparece un error indicando que no existe un módulo como:

```text
ModuleNotFoundError: No module named 'pygame'
```

instala las dependencias de los temas:

```bat
python -m pip install pygame pystray Pillow
```

Después vuelve a ejecutar el tema.

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

Por ejemplo:

```text
background.jpg
```

❌ Incorrecto.

Debe ser:

```text
background.png
```

Y:

```text
music.wav
```

❌ Incorrecto.

Debe ser:

```text
bgm.wav
```

---

# 📌 No utilices rutas absolutas

No escribas rutas específicas de tu ordenador como:

```text
C:\Users\TuNombre\Desktop\Mi Tema\bgm.wav
```

El código proporcionado utiliza:

```python
CARPETA = os.path.dirname(os.path.abspath(__file__))
```

Esto permite que el tema encuentre automáticamente sus archivos dentro de su propia carpeta.

Por eso puedes compartir la carpeta del tema con otras personas sin tener que modificar las rutas.

---

# 🧩 ¿Cómo funciona el sistema?

Luigi Theme Assistant está dividido en varios componentes.

## `Luigi Theme Assistant.exe`

Es el **launcher**.

Es el programa que el usuario ejecuta normalmente.

Su función principal es iniciar:

```text
Luigi_Theme_Assistant.exe
```

---

## `Luigi_Theme_Assistant.exe`

Es el programa principal.

Se encarga de:

- Detectar Python.
- Comprobar `python.exe`.
- Comprobar `pythonw.exe`.
- Guardar las rutas de Python.
- Buscar la carpeta `Themes`.
- Detectar los temas disponibles.
- Crear el menú del área de notificaciones.
- Ejecutar los `config_desktop.py`.
- Cambiar entre temas.
- Detener el tema anterior.

---

## `config_desktop.py`

Es el programa de cada tema.

Se ejecuta utilizando:

```text
pythonw.exe
```

y utiliza las librerías instaladas en Python.

Por ejemplo:

```python
import pygame
import pystray
from PIL import Image
```

Por eso es necesario tener instaladas:

```text
pygame
pystray
Pillow
```

---

# 🐍 ¿Por qué los temas necesitan Python?

Luigi Theme Assistant no convierte automáticamente los temas en `.exe`.

Los temas utilizan:

```text
config_desktop.py
```

y estos archivos se ejecutan mediante el Python instalado en el ordenador.

Por eso cada ordenador que quiera utilizar temas debe tener:

```text
Python
pygame
pystray
Pillow
```

instalados.

---

# 📄 ¿Por qué existe `ruta_python.json`?

Cada ordenador puede tener Python instalado en una ubicación diferente.

Por ejemplo:

```text
C:\Users\Usuario\AppData\Local\Programs\Python\Python312\
```

o:

```text
C:\Python312\
```

Luigi Theme Assistant detecta automáticamente la instalación y guarda las rutas en:

```text
config/ruta_python.json
```

Así no tienes que modificar manualmente las rutas.

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

# 🎯 Recomendaciones para crear temas

## 🖼️ Fondo

Se recomienda utilizar una imagen con una resolución adecuada para el monitor.

Por ejemplo:

```text
1920x1080
```

para una pantalla Full HD.

## 🎵 Música

Se recomienda utilizar un archivo `.wav` que no sea excesivamente grande.

Recuerda que la música se reproduce continuamente.

## 🟢 Icono

Se recomienda utilizar una imagen sencilla que pueda reconocerse fácilmente en el área de notificaciones.

---

# 📋 Checklist para compartir un tema

Antes de compartir tu tema, comprueba que tenga:

```text
☐ config_desktop.py
☐ bgm.wav
☐ background.png
☐ icon.png
```

Y que todos estén dentro de una única carpeta:

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

### 1.

Crea una carpeta dentro de:

```text
Themes/
```

Por ejemplo:

```text
Themes/Mi Tema/
```

### 2.

Añade el fondo:

```text
background.png
```

### 3.

Añade la música:

```text
bgm.wav
```

### 4.

Añade el icono:

```text
icon.png
```

### 5.

Crea:

```text
config_desktop.py
```

### 6.

Copia el código proporcionado en esta guía.

### 7.

Asegúrate de tener Python 3.10.11 o superior.

### 8.

Instala las librerías necesarias:

```bat
python -m pip install pygame pystray Pillow
```

### 9.

Ejecuta:

```text
Luigi Theme Assistant.exe
```

### 10.

Busca tu tema en el menú.

### 11.

Selecciona tu tema.

### 12.

¡Disfruta de tu nuevo tema! 🟢🎵🎨

---

# 🟢 Luigi Theme Assistant

**Crea tus propios temas.**

**Personaliza tu escritorio.**

**Comparte tus temas.**

🎨 🖼️ 🎵 🟢
