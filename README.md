# Driving Assistant (Asistencia de Manejo)

Este es un sistema de asistencia de manejo básico basado en visión por computadora que procesa video en tiempo real para detectar y resaltar las líneas de carril en la carretera. 

El proyecto utiliza técnicas de procesamiento digital de imágenes con OpenCV y NumPy en Python para segmentar el camino y resaltar los carriles por los que transita el vehículo.

## 🚀 Características
* **Conversión a escala de grises y suavizado Gaussiano:** Reduce el ruido en los frames del video para optimizar la detección de bordes.
* **Detección de bordes con Canny:** Encuentra los contornos y límites de la carretera de manera eficiente.
* **Segmentación de Región de Interés (ROI):** Delimita el procesamiento únicamente a la zona de la carretera frente al vehículo, evitando procesar elementos irrelevantes (como el cielo o árboles).
* **Búsqueda y dibujado de contornos:** Identifica las líneas del carril y las dibuja rellenas para una visualización clara del camino.

## 🛠️ Requisitos de Hardware y Software
### Setup de Hardware (Recomendado si se implementa en hardware real como ESP32/Cámaras externas)
* **Cámara:** Resolución mínima de 720p orientada hacia el frente del vehículo.
* **Procesador:** Sistema capaz de ejecutar Python y OpenCV a un framerate aceptable (se recomienda una PC, Raspberry Pi 4 o similar).
* *Nota:* Para integraciones con microcontroladores como ESP32, recordar que los niveles de lógica son de 3.3V para los pines GPIO y se debe implementar debouncing para cualquier botón físico de control.

### Software y Dependencias
Para ejecutar este script, necesitas tener instalado **Python 3.x** junto con las siguientes bibliotecas:
* [OpenCV](https://opencv.org/) (`opencv-python`)
* [NumPy](https://numpy.org/) (`numpy`)

Puedes instalar las dependencias ejecutando:
```bash
pip install opencv-python numpy
```

## 📂 Estructura del Proyecto
* `Main.py.py`: Script principal de Python que procesa el video.
* `lineas.mp4`: Video de muestra utilizado para la detección de carriles.
* `Leame.txt`: Archivo de instrucciones rápidas original.

## 🔧 Ejecución
Para iniciar el asistente de manejo, sigue estos pasos:

1. Asegúrate de tener el archivo de video (`lineas.mp4` o el de tu preferencia) en el mismo directorio que el script.
2. Si utilizas un video con un nombre diferente, modifícalo en la línea 67 de `Main.py.py`:
   ```python
   video_path = 'tu_video.mp4'
   ```
3. Ejecuta el script desde tu terminal:
   ```bash
   python Main.py.py
   ```
4. Para salir de la visualización en tiempo real, presiona la tecla **`q`**.

## 📝 Reglas de Calidad y Estilo
Este proyecto sigue las guías de estilo **PEP 8** para Python. Todo el código debe estar debidamente documentado explicando el "porqué" de las decisiones algorítmicas y de diseño.
