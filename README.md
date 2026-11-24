# EXAMEN TEST v1.04 — PRUEBA DE 2 PREGUNTAS

Versión de prueba de la aplicación de examen. **No es el examen oficial de 50 preguntas.**

## Qué incluye

- Pregunta original **1** (Introducción a la IA) y pregunta original **26** (Seguridad, privacidad y ética), con los textos y las respuestas correctas conservados.
- Nombre, apellidos, selector de grupo A–H, instrucciones, preguntas y opciones mezcladas, navegación, borrado de respuestas, corrección y resumen final.
- Calificación normalizada sobre 10: acierto **+5,00**; error **−1,25**; blanco **0**. Conserva la relación de penalización original (−25 % del valor del acierto).
- 30 minutos y posibilidad de ampliar 10 minutos una sola vez.
- Tras finalizar, los resultados **no revelan ninguna solución**. El código **123456789** permite desbloquear la revisión de las dos preguntas en pantalla.
- PDF descargado directamente desde el navegador con nombre, fecha, grupo, tiempo, ampliación, nota, aciertos, errores y blancos; sin preguntas ni soluciones.
- Guardado y recuperación en `localStorage` del navegador. La prueba tiene una clave de almacenamiento distinta a la del examen real, para no interferir con él.
- No hay Firebase, panel del profesor, analítica, librerías remotas, `fetch` ni envío automático de datos.

## Comprobar la ampliación sin esperar

Durante el examen despliega **Herramientas de prueba del temporizador**. Pulsa **Simular fin de 30 minutos**; verás la pantalla de ampliar o terminar. Si amplías, aparecerá **Simular fin de 40 minutos** para forzar la finalización. La ampliación utilizada aparece en el PDF.

## Abrir en Chrome

Descarga el archivo `index.html` y ábrelo directamente con Chrome o Edge. La vista previa dentro de ChatGPT puede bloquear JavaScript.

## Publicarlo en GitHub Pages

Sube `index.html` a la raíz de un repositorio, y activa GitHub Pages (rama `main`, carpeta `/ (root)`). No hacen falta otros archivos.

## Alcance y límites

Solo es una prueba de funcionamiento. El código no es seguridad fuerte (el HTML y las soluciones están en el equipo). Una app estática local tampoco puede garantizar que se haya respetado el reloj del dispositivo o que el PDF no se haya modificado.
