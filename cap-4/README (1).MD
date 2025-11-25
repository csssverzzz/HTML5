# Llamémoslo una superficie de dibujo: cap4

El elemento `<canvas>` es una de las características más poderosas y versátiles introducidas por HTML5. A primera vista, puede parecer modesto —incluso invisible—, pero bajo su apariencia minimalista se esconde una verdadera *hoja en blanco digital* donde el programador puede crear gráficos, animaciones, juegos, visualizaciones de datos e incluso interfaces interactivas, todo ello mediante código JavaScript.

## ¿Qué es exactamente un `<canvas>`?

Según la especificación de HTML5, el `<canvas>` es un *"lienzo de mapa de bits dependiente de la resolución que se puede usar para representar gráficos, gráficos de juegos u otras imágenes visuales sobre la marcha"*. En términos más simples: es un rectángulo definido en tu página HTML que no muestra nada por sí mismo, pero que puede ser manipulado mediante JavaScript para dibujar formas, líneas, texto, imágenes y degradados en tiempo real.

Por defecto, un `<canvas>` no tiene borde ni contenido visible. Para verlo, suele ser útil añadirle un borde con CSS. Puedes tener tantos elementos `<canvas>` como desees en una misma página, y cada uno mantiene su propio estado gráfico independiente.

## El contexto de dibujo: donde ocurre la magia

Para dibujar en un `<canvas>`, primero debes obtener su **contexto de dibujo**. Esto se hace llamando al método `getContext("2d")` sobre el elemento. Este contexto es un objeto que contiene todas las funciones y propiedades necesarias para renderizar gráficos bidimensionales: colores, estilos, métodos para trazar líneas, rellenar formas, escribir texto, etc.

```javascript
const canvas = document.getElementById("miLienzo");
const ctx = canvas.getContext("2d");```

El elemento ```<canvas>``` es una de las características más poderosas y versátiles introducidas por HTML5. A primera vista, puede parecer modesto —incluso invisible—, pero bajo su apariencia minimalista se esconde una verdadera *hoja en blanco digital* donde el programador puede crear gráficos, animaciones, juegos, visualizaciones de datos e incluso interfaces interactivas, todo ello mediante código JavaScript.

## ¿Qué es exactamente un ```<canvas>```?

Según la especificación de HTML5, el `<canvas>` es un *"lienzo de mapa de bits dependiente de la resolución que se puede usar para representar gráficos, gráficos de juegos u otras imágenes visuales sobre la marcha"*. En términos más simples: es un rectángulo definido en tu página HTML que no muestra nada por sí mismo, pero que puede ser manipulado mediante JavaScript para dibujar formas, líneas, texto, imágenes y degradados en tiempo real.

Por defecto, un `<canvas>` no tiene borde ni contenido visible. Para verlo, suele ser útil añadirle un borde con CSS. Puedes tener tantos elementos `<canvas>` como desees en una misma página, y cada uno mantiene su propio estado gráfico independiente.

## El contexto de dibujo: donde ocurre la magia

Para dibujar en un `<canvas>`, primero debes obtener su **contexto de dibujo**. Esto se hace llamando al método `getContext("2d")` sobre el elemento. Este contexto es un objeto que contiene todas las funciones y propiedades necesarias para renderizar gráficos bidimensionales: colores, estilos, métodos para trazar líneas, rellenar formas, escribir texto, etc.
```
javascript
```const canvas = document.getElementById("miLienzo");```
```const ctx = canvas.getContext("2d");```

Es importante destacar que, a día de hoy, no existe un contexto 3D estandarizado en HTML5. Aunque algunos navegadores han experimentado con APIs propietarias (como WebGL, que sí permite gráficos 3D), el contexto "2d" sigue siendo el único oficial para dibujo plano.

##Sistema de coordenadas y precisión visual

El lienzo utiliza un sistema de coordenadas cartesiano donde el punto (0, 0) está en la esquina superior izquierda. El eje X crece hacia la derecha y el eje Y hacia abajo. Esto es crucial al posicionar elementos.

Un detalle sutil pero importante: para dibujar líneas de 1 píxel de ancho sin que el navegador las suavice o las haga parecer más gruesas, es recomendable desplazar las coordenadas en 0.5 píxeles. Esto se debe a que las coordenadas enteras caen entre píxeles, lo que hace que el navegador pinte a ambos lados, resultando en una línea de 2 píxeles de ancho aparente.

##Dibujar formas y rutas

El ```<canvas>``` permite dibujar rectángulos de forma directa con métodos como:

```fillRect(x, y, ancho, alto): rellena un rectángulo.```
```strokeRect(x, y, ancho, alto): dibuja el contorno.```
```clearRect(x, y, ancho, alto): borra un área.```

Para formas más complejas (círculos, polígonos, curvas), se usan rutas. Una ruta se construye con comandos como ```moveTo() y lineTo(),``` que definen puntos y segmentos. Estos comandos son como "dibujar con lápiz": no se ven hasta que se "entiñan" con ```stroke() (contorno) o fill()``` (relleno).

Los círculos, por ejemplo, se dibujan con arc(x, y, radio, ánguloInicial, ánguloFinal, sentido), aprovechando que un círculo completo equivale a 2π radianes.

Texto, imágenes y degradados
Además de formas geométricas, el contexto 2D permite:

Texto: ```mediante fillText()``` o ```strokeText()```. A diferencia del texto HTML, no hay flujo de caja ni ajuste automático; debes especificar posición exacta, fuente, alineación ```(textAlign) ```y línea base ```(textBaseline)```.
Imágenes: con  ``` ```drawImage() ```, que admite escalado, recorte y posicionamiento. Es útil para sprites, iconos o composiciones gráficas.
Degradados: tanto lineales ``` (createLinearGradient) ``` como radiales  ```(createRadialGradient ``` Se definen como objetos y luego se asignan a ``` fillStyle o strokeStyle ```.
Interactividad: respondiendo a clics
Un  ```<canvas>  ```puede escuchar eventos como clics del ratón. Sin embargo, dado que no "recuerda" los objetos dibujados (solo almacena píxeles), el desarrollador debe traducir manualmente las coordenadas del clic (relativas al documento) a coordenadas del lienzo, y luego determinar qué "objeto lógico" (por ejemplo, una pieza de juego) corresponde a esa posición.

##Compatibilidad y soporte en navegadores

La mayoría de los navegadores modernos (Firefox, Chrome, Safari, Opera, Android, iOS) soportan <canvas> desde versiones muy antiguas. Internet Explorer 9+ lo incluye de forma nativa. Para IE7 e IE8, existe la biblioteca excanvas.js, que emula el comportamiento usando VML, aunque con limitaciones: sin degradados radiales, sin regiones de recorte, y con menor rendimiento.
