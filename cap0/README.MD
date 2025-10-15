
## 1. Introduccion
- HTML5 no es un único "paquete", sino un **conjunto de características individuales**.
- No se puede detectar "soporte de HTML5" como un todo, pero sí se puede detectar soporte para:
  - `<canvas>`
  - `<video>`
  - Geolocalización, entre otros.
- HTML5 también define cómo interactúan las etiquetas HTML con **JavaScript** mediante el **DOM (Document Object Model)**.

## 2. No necesitas desechar lo que ya tienes
- HTML5 **es compatible con HTML 4**.
- Tu sitio actual seguirá funcionando si fue construido en HTML 4.
- Puedes **mejorar tus formularios** usando nuevos controles como:
  - `type="email"` (con teclado especial en móviles).
  - Sliders, selectores de fecha, etc.
- En navegadores antiguos, los controles nuevos simplemente se degradan con gracia (graceful degradation).

## 3. Es fácil comenzar
- Comenzar con HTML5 puede  ser tan simple como **cambiar el doctype**::
  ```html
  <!DOCTYPE html>
