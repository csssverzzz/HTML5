# CAPÍTULO 2: Detección de características HTML5

Durante los primeros años del desarrollo web moderno, muchos programadores se preguntaban cómo podían aprovechar las nuevas funciones de HTML5 si no todos los navegadores lo soportaban.  
La clave está en entender que **HTML5 no es una sola tecnología**, sino un **conjunto de características independientes**.

Por eso, **no se puede “detectar HTML5” como un todo**. En su lugar, se debe comprobar si el navegador es compatible con cada una de sus funciones:  
**geolocalización**, **video**, **almacenamiento local**, **canvas**, **Web Workers**, **formularios avanzados**, entre otras.

---

## Cómo saber si un navegador es compatible

Cuando un navegador interpreta una página web, crea una estructura interna llamada **DOM (Document Object Model)**.  
Cada etiqueta HTML se convierte en un objeto dentro del DOM, y gracias a eso podemos verificar si existen ciertas propiedades o métodos que indiquen compatibilidad con alguna función de HTML5.

Existen **cuatro formas básicas** de comprobarlo:

1. **Revisar si existe una propiedad en un objeto global** como `window` o `navigator`.  
   Ejemplo: `navigator.geolocation` para saber si se admite la geolocalización.

2. **Crear un elemento y verificar si tiene un método específico.**  
   Ejemplo: crear un `<canvas>` y comprobar si existe el método `getContext()`.

3. **Llamar a un método y analizar su resultado.**  
   Ejemplo: usar `canPlayType()` para ver qué formatos de video entiende el navegador.

4. **Asignar un valor a una propiedad y ver si se mantiene.**  
   Ejemplo: crear un `<input>` y cambiar su tipo a `"color"` o `"date"` para ver si el navegador lo reconoce.

---

## Modernizr: tu aliado para la detección

Para no tener que escribir todas esas pruebas a mano, existe **Modernizr**, una biblioteca de JavaScript de código abierto que detecta automáticamente qué funciones de HTML5 y CSS3 soporta un navegador.

Al cargarla, genera un objeto global llamado `Modernizr`, que contiene propiedades con valores booleanos (`true` o `false`).  
Por ejemplo:

```javascript
Modernizr.canvastext
```

## Video y formatos compatibles
Antes de HTML5, ver videos en la web requería complementos externos como Flash o QuickTime.Con la llegada del elemento``` <video>```, los navegadores pueden reproducirlos directamente, aunque no todos aceptan los mismos formatos: 

 H.264 (MP4): funciona muy bien en Safari, iPhone y Edge.
WebM: formato libre usado por Chrome, Firefox y Opera.
Ogg Theora: también libre, pero menos común hoy en día.
Para saber qué formato soporta el navegador, se usa el método canPlayType, que devuelve:

```probably```(muy probable que funcione),
```maybe``` (quizás),
"o una cadena vacía " (no funciona).

Modernizr simplifica esta tarea con propiedades como:

```Modernizr.video.h264```
```Modernizr.video.webm```
```Modernizr.video.ogg```

## Almacenamiento local (Local Storage)

El almacenamiento local es la evolución de las cookies.
Permite guardar más datos directamente en el navegador, sin enviarlos al servidor en cada solicitud.

Para verificar su soporte, basta comprobar si existe window.localStorage.
Si está disponible, el sitio puede guardar información que persiste incluso después de cerrar la página.

Modernizr también lo detecta fácilmente con:
Modernizr.localstorage

## Web Workers

Los Web Workers permiten que el navegador ejecute código JavaScript en segundo plano, como si fueran pequeños “subprocesos”.
Esto mejora el rendimiento de las aplicaciones, ya que evita que la interfaz se congele durante tareas pesadas.

Para saber si están disponibles, se comprueba si existe window.Worker.

Modernizr incluye:
```Modernizr.webworkers```

## Aplicaciones sin conexión
HTML5 introdujo la posibilidad de crear aplicaciones web que funcionan sin conexión, usando el Application Cache.

Cuando el sitio se carga por primera vez, el navegador guarda los archivos necesarios y los reutiliza si no hay conexión.
La compatibilidad se detecta comprobando si existe window.applicationCache.

Modernizr lo detecta con:
```Modernizr.applicationcache```

## Geolocalización
La geolocalización permite saber en qué parte del mundo se encuentra el usuario, usando datos como la IP, torres celulares o el GPS.
Se detecta fácilmente con:
```navigator.geolocation```

Aunque técnicamente no es parte del estándar HTML5, suele incluirse dentro del conjunto de tecnologías modernas que forman la web actual.

Modernizr lo detecta con:
```Modernizr.geolocation```

## Nuevos tipos de entrada en formularios
HTML5 amplió las opciones para los formularios al incluir nuevos tipos de ```<input> ```como:

Texto y contacto: search, tel, url, email
Fechas: date, month, week, time, datetime-local
Números y selección: number, range, color
Para saber si un tipo es compatible, se crea un campo ```<input> ```y se cambia su tipo.
Si el navegador mantiene ese valor (por ejemplo, "color"), significa que lo reconoce.

Modernizr también puede comprobarlo automáticamente con:
```Modernizr.inputtypes.color```
```Modernizr.inputtypes.date```
```Modernizr.inputtypes.range```

Placeholder y Autofocus (detalles que marcan la diferencia)
placeholder: muestra texto de ayuda dentro del campo mientras está vacío.
Detección: ```Modernizr.input.placeholder```
autofocus: mueve el foco automáticamente al cargar la página.
Detección: ```Modernizr.input.autofocus```
Ambas mejoran la experiencia del usuario sin necesidad de JavaScript personalizado.