# EXAMEN TEST · Inteligencia Artificial · v1.04

Aplicación web estática para que el alumno haga un examen tipo test, **descargue un PDF con su nota y lo entregue manualmente**. Sin Firebase, sin panel del profesor y sin envío automático de resultados.

## Novedades de la versión 1.04

- **Grupo obligatorio A–H**, seleccionado desde un desplegable. Nombre y apellidos también son obligatorios.
- **Resultados privados hasta introducir un código:** tras finalizar, solo aparecen los datos del alumno, fecha/hora, nota, aciertos, errores, preguntas en blanco, tiempo empleado y ampliación. La revisión completa de las 50 preguntas, respuestas del alumno y soluciones requiere el código entregado por el profesor.
- **Ampliación opcional de 10 minutos:** cuando terminan los primeros 30 minutos se bloquean las respuestas y se ofrece finalizar o ampliar una sola vez. La ampliación **cuenta desde el minuto 30** (no pausa el reloj durante la decisión); el examen termina como máximo al minuto 40, incluso si se cierra la página. Si se rechaza, la duración contabilizada es 30 minutos.
- **PDF de una sola página, exclusivamente de resultados**, sin preguntas, respuestas del alumno ni soluciones; incluye explícitamente si hubo ampliación y el tiempo autorizado.
- También al **imprimir / guardar PDF** desde el navegador se oculta la revisión, aunque el alumno haya introducido el código.
- El código de revisión no queda desbloqueado de forma persistente al recargar.

**Atención:** al ser una web 100 % estática, el código de revisión puede averiguarse inspeccionando el código fuente. Es una barrera para el uso habitual, no una protección contra un estudiante con conocimientos técnicos. La hora local y el almacenamiento del navegador también pueden manipularse: no es un examen antifraude certificado.

## Funcionamiento

1. Introducir nombre, apellidos y grupo (A a H); pulsar **Aceptar**.
2. Leer instrucciones y pulsar **Comenzar examen**.
3. Contestar 50 preguntas, con preguntas y cuatro opciones barajadas por separado. Se puede navegar y borrar respuestas.
4. Finalizar voluntariamente o esperar al minuto 30, cuando aparece una **única** opción de ampliar 10 minutos (hasta el minuto 40).
5. Ver resumen y descargar PDF (sin soluciones) para entregarlo al profesor.
6. Solo con el código de revisión facilitado por el profesor se muestra en pantalla la revisión ordenada 1–50 con soluciones.

La nota se calcula como `máximo(0, mínimo(10, aciertos*0,20 - errores*0,05))`, con dos decimales. Sin contestar = 0. Las 50 preguntas, incluidas las correcciones de las preguntas **15, 29, 31 y 49** respecto al temario, están conservadas íntegramente desde v1.03.

## Publicación en GitHub Pages

Descomprimir el ZIP y subir **el contenido de la carpeta** a la raíz del repositorio:

- `index.html` — aplicación completa con 50 preguntas integradas; funciona al abrirla directamente con Chrome o Edge.
- `test.html` — copia íntegra para pruebas manuales.
- `data/questions.json` — banco editable utilizado opcionalmente desde GitHub Pages.
- `sw.js` — caché sin datos personales, para uso sin conexión tras la primera carga.
- `README.md` — estas instrucciones.

En **Settings > Pages** del repositorio, publicar desde `main`, carpeta `/ (root)`. Si había versiones antiguas, forzar actualización con **Ctrl + Mayús + R** o borrar datos de ese sitio si continúa mostrando código desactualizado.

El archivo HTML independiente entregado junto al ZIP tiene el mismo código de `index.html`: **descargar y abrir con un navegador**. La vista previa de HTML dentro de ChatGPT puede no ejecutar JavaScript.

## Recuperación del examen

El progreso (incluido el orden aleatorio, respuestas, tiempo y la ampliación solicitada) queda en el almacenamiento local del **mismo navegador, dispositivo y origen web**. El tiempo sigue corriendo al cerrar la página. Si se vuelve después de vencer el plazo máximo, el examen se corrige automáticamente. Tras finalizar, el intento no se puede modificar. Borrar datos del sitio puede eliminar el progreso.

## Privacidad y límites

Ningún nombre, respuesta, nota ni PDF se envía automáticamente. La web alojada requiere descargar el HTML y, opcionalmente, el banco JSON desde GitHub Pages, pero **no hace solicitudes a Firebase ni a servicios de terceros para procesar alumnos**. El PDF se genera completamente en el navegador. No hay autenticación real del profesor, telemetría ni base de datos. No se puede impedir que un alumno experto inspeccione las respuestas integradas o manipule datos locales. El PDF entregado no permite verificar criptográficamente su autenticidad.
