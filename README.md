# 🤡 Filtro de Payaso con Realidad Aumentada

Un filtro facial que se ejecuta en el navegador usando tu cámara. Te pone maquillaje, peluca y sombrero de payaso, y reacciona cuando abres la boca.

## Qué hace

- Detecta tu cara en tiempo real con [MediaPipe Face Landmarker](https://ai.google.dev/edge/mediapipe/solutions/vision/face_landmarker).
- Dibuja nariz roja, maquillaje en los ojos, mejillas rosadas, sonrisa pintada, peluca y sombrero.
- El disfraz sigue el movimiento, el tamaño y la inclinación de tu cabeza.
- Al abrir la boca suena una bocina y sale confeti.
- Botón **Tomar foto** para descargar una imagen con el filtro.

## Cómo usarlo

1. Descarga `filtro_payaso.html` (y, si quieres tu propio sonido, `bocina.mp3` en la misma carpeta).
2. La cámara no funciona abriendo el archivo directo (`file://`), así que sírvelo desde un servidor local. Por ejemplo, desde la carpeta del archivo:

   ```bash
   python -m http.server 8000
   ```

3. Abre `http://localhost:8000/filtro_payaso.html` en tu navegador.
4. Presiona **¡Activar cámara!** y acepta el permiso.
5. Abre la boca y diviértete.

## Requisitos

- Navegador moderno (Chrome, Edge, Firefox o Safari recientes).
- Una cámara web.
- Conexión a internet la primera vez, para descargar el modelo de MediaPipe.

## Personalizar

- **Sonido:** reemplaza `bocina.mp3`. Si el archivo no existe, el filtro genera una bocina sintética.
- **Colores y formas:** están en las funciones `drawWig`, `drawFacePaint`, `drawSmile`, `drawNose` y `drawHat` dentro del archivo.
- **Sensibilidad de la boca:** cambia el valor `0.3` en `const isOpen = jaw > 0.3` (más bajo = se activa más fácil).

## Créditos

Hecho con HTML, JavaScript y [MediaPipe Tasks Vision](https://www.npmjs.com/package/@mediapipe/tasks-vision).
