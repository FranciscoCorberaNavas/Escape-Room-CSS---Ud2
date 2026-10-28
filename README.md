# Cine Las Vías · Escape room CSS

Actividad gamificada por equipos para **DAW2 · Diseño de Interfaces Web**. Sirve para repasar:

- **Selectores CSS** básicos y combinados, más especificidad.
- **`position`** (`relative`, `absolute`, `fixed`, `sticky`) y `z-index`, sin flex ni grid.
- **Metodología BEM.**

Duración: una sesión de **50 minutos**, por equipos de 3 o 4 personas.

## Contenido del repositorio

| Archivo | Para qué sirve |
|---|---|
| `index.html` | El juego. Es lo que abren los alumnos. |
| `profesor.html` | Cuenta atrás de 50 min y clasificación para proyectar. |
| `css/juego.css` | Estilos del juego. |
| `js/datos.js` | Preguntas, retos y textos. **Edita aquí el contenido.** |
| `js/juego.js` | Lógica del juego. |

## Publicarlo con GitHub Pages

1. Crea un repositorio nuevo en GitHub, por ejemplo `escape-css`.
2. Sube todos los archivos manteniendo las carpetas `css/` y `js/`.
3. Ve a **Settings → Pages**.
4. En **Source** elige *Deploy from a branch*, rama `main` y carpeta `/ (root)`. Guarda.
5. En uno o dos minutos la web estará en:
   - Juego: `https://TU-USUARIO.github.io/escape-css/`
   - Marcador: `https://TU-USUARIO.github.io/escape-css/profesor.html`

Truco: proyecta un código QR con la URL del juego para que los equipos entren rápido.

## Cómo funciona en clase

- Cada equipo abre el juego en **un solo ordenador** y escribe su nombre.
- El progreso se guarda en el navegador de ese equipo. Si recargan la página, no pierden nada.
- **No hay servidor.** La puntuación de cada equipo se ve en la pestaña **Salida** como un código, por ejemplo `258-F-TEHU`.
- Tú introduces ese código en `profesor.html`. El marcador lo valida (la firma depende del nombre del equipo y de los puntos) y lo añade a la clasificación.
- Si se acaba el tiempo y un equipo no ha terminado, también tiene un código **provisional** (`P`) con sus puntos hasta ese momento.

## Puntuación (máximo 285)

| Prueba | Puntos |
|---|---|
| 1 · Selectores (11 preguntas) | 10 al primer intento, 6 al segundo y 3 después |
| 2 · Position (5 retos) | 20 por reto, −3 por cada comprobación fallida, −5 si usan la pista (mínimo 6) |
| 3A · ¿Es BEM? | 20, −4 por cada comprobación fallida (mínimo 6) |
| 3B · Conceptos BEM (3 preguntas) | 5 / 3 / 1 |
| 3C · Refactorización BEM | 30, −4 por cada comprobación fallida (mínimo 10) |
| Abrir la salida | 10 |

En el marcador puedes sumar o restar 5 puntos a mano: bonus al primer equipo en salir, comodines, etc.

## Cambiar el contenido

Todo está en `js/datos.js`:

- **Preguntas de selectores de tipo «clic»:** basta con cambiar `html` y `selector`. La corrección usa `querySelectorAll` real, así que no hay que escribir la solución.
- **Retos de position:** cada uno tiene su HTML, su CSS fijo, el CSS inicial del alumno y una función `comprobar()`. Esa función mide la escena real (posiciones en píxeles y qué elemento queda encima) y devuelve los criterios.
- **Respuestas de las preguntas tipo test, de BEM y de la contraseña:** están codificadas en la constante `SECRETOS`, en base64 invertido, para que no se lean a simple vista.

> ⚠ Es una web estática: un alumno que abra las DevTools podría encontrar las respuestas. En las reglas del juego se indica que mirar el código fuente es trampa.
