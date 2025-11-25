# README -- Microdata en HTML5 (Resumen Completo)

Este documento contiene un resumen claro y organizado sobre
**microdata**, una característica de HTML5 que permite añadir semántica
adicional a las páginas web mediante pares nombre/valor dentro de
vocabularios personalizados. Su objetivo es enriquecer la información
sin crear etiquetas nuevas ni afectar la apariencia visual de la página.

## ¿Qué es Microdata?

Microdata permite describir el significado del contenido dentro del HTML
**sin inventar elementos nuevos** como `<person>`, los cuales serían
inválidos y poco compatibles. En cambio, se agregan atributos especiales
como *itemscope*, *itemtype* e *itemprop* para aportar estructura
semántica sin modificar el diseño.

## Conceptos Clave

### 1. Vocabularios personalizados

Cada vocabulario está definido por una URL, por ejemplo:\
`http://data-vocabulary.org/Person`

### 2. Pares nombre/valor

El **nombre** es una propiedad del vocabulario (ej. *name*, *photo*,
*url*).\
El **valor** se obtiene del contenido del elemento (texto, `src`,
`href`, etc.).

### 3. Ámbito (scoping)

Cuando un elemento tiene `itemscope` y `itemtype`, todo elemento dentro
con `itemprop` pertenece a ese ítem según la estructura del DOM.

## Ejemplos de Uso

### Persona

``` html
<section itemscope itemtype="http://data-vocabulary.org/Person">
  <h1 itemprop="name">Ada Lovelace</h1>
  <img itemprop="photo" src="ada.jpg">
  <a itemprop="url" href="https://example.com">Sitio Web</a>
</section>
```

### Datos Anidados

``` html
<div itemprop="address" itemscope itemtype="http://data-vocabulary.org/Address">
  <span itemprop="street-address">123 Main St</span>
</div>
```

### Datos invisibles

``` html
<meta itemprop="latitude" content="37.4149">
```

## Google Rich Snippets

Microdata permite que Google muestre información enriquecida como:

-   Nombres\
-   Fotos\
-   Fechas\
-   Calificaciones\
-   Direcciones

Aunque no garantiza que siempre aparezcan, ayuda enormemente a la
comprensión del contenido.

## Importancia del buen HTML

Microdata no reemplaza un marcado limpio.\
Cuanto mejor esté estructurado el HTML original, más fácil será
implementar microdata correctamente.

## Conclusión

Microdata permite:

-   Añadir semántica sin cambiar el diseño\
-   Mejorar la interpretación por buscadores\
-   Anotar información visible de forma ordenada\
-   Manejar estructuras complejas como eventos, personas y reseñas
