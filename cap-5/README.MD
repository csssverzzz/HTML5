#El Video en la Web con HTML5 CAP5

El texto ofrece una explicación profunda sobre la evolución del video en la web, enfocándose en los componentes técnicos y los estándares modernos que surgieron con la llegada de HTML5. Describe cómo este lenguaje transformó la forma en que se integran los videos en los sitios web y los desafíos que aún persisten en torno a la compatibilidad de formatos y códecs.

## Antes y Después de HTML5

En los primeros años de internet, reproducir videos en una página web era complicado. No existía un método estandarizado, por lo que los desarrolladores debían recurrir a complementos externos como Flash Player, QuickTime o RealPlayer. Esto generaba problemas de seguridad, rendimiento y compatibilidad entre navegadores.

La introducción del elemento <video> en HTML5 marcó un cambio fundamental, ya que proporcionó una forma nativa y estandarizada de incrustar videos sin depender de plugins. Sin embargo, el avance no eliminó todos los problemas: aún no existe un único formato universal que funcione en todos los navegadores, lo que obliga a los desarrolladores a convertir cada video en distintos formatos para asegurar su correcta reproducción.

## Estructura del Video Digital: Contenedores y Códecs

Todo archivo de video está compuesto por dos elementos principales:

Contenedores de video:
Son formatos que agrupan distintos tipos de datos —como pistas de video, audio y metadatos— dentro de un solo archivo. Ejemplos:

MP4 (MPEG-4): Muy popular y basado en el contenedor QuickTime. Compatible con una amplia gama de dispositivos, incluyendo iPhone y Android.

Ogg (.ogv): Un formato abierto y libre de patentes, promovido por la comunidad del software libre.

WebM: Creado por Google en 2010, diseñado específicamente para la web y pensado para usarse junto con el códec VP8 y el audio Vorbis.

Códecs de video:
Son los algoritmos que comprimen y descomprimen los datos visuales. En la web se utilizan principalmente códecs con pérdida, lo que significa que eliminan parte de la información visual para reducir el tamaño del archivo. Los más comunes son:

H.264 (MPEG-4 AVC): Ofrece gran calidad y compresión eficiente, utilizado por plataformas como YouTube y Blu-Ray, aunque sujeto a licencias y patentes.

Theora: Un códec libre derivado de VP3, completamente sin regalías, compatible de forma nativa con navegadores como Firefox, Chrome y Opera.

VP8: Adquirido y liberado por Google como código abierto, es el códec estándar del formato WebM.

Códecs de audio:
Se encargan de la compresión del sonido. Los principales son:

MP3: Muy extendido y compatible, aunque con restricciones de patentes.

AAC: Usado por Apple, ofrece mejor calidad que el MP3 a igual tasa de bits.

Vorbis: Libre de patentes y ampliamente usado junto a Theora o WebM.

##Flujo de Trabajo y Compatibilidad entre Navegadores

Debido a la falta de un formato universal, se recomienda codificar cada video en tres versiones distintas, asegurando la reproducción en la mayoría de los navegadores modernos:

WebM (VP8 + Vorbis)

MP4 (H.264 + AAC)

Ogg (Theora + Vorbis)

Cada navegador ofrece soporte diferente:

Firefox, Chrome y Opera: Soportan Ogg/Theora y WebM.

Safari, iPhone y Android: Reproducen MP4 con H.264 + AAC.

Internet Explorer 9: Compatible con MP4 y, con instalación adicional, con WebM.

Esta fragmentación obliga a los desarrolladores a crear múltiples versiones del mismo contenido para garantizar que todos los usuarios puedan visualizar el video sin importar el navegador o dispositivo.

## El Marcado HTML5 y la Compatibilidad Retroactiva

El elemento <video> de HTML5 permite incluir varias fuentes mediante el uso de múltiples etiquetas <source>. Cada navegador intentará reproducir la primera que reconozca.
El atributo type ayuda a identificar el formato (contenedor + códecs) sin necesidad de descargar el archivo, optimizando el uso de ancho de banda.
Además, el atributo controls agrega los controles nativos del navegador (reproducir, pausar, volumen, etc.).

Para los navegadores más antiguos que no soportan HTML5, es posible incluir un reproductor Flash dentro del mismo elemento <video>. De esta forma, los navegadores modernos ignorarán el contenido Flash, mientras que los más antiguos lo usarán como alternativa.

Un detalle técnico importante es configurar correctamente el tipo MIME en el servidor (por ejemplo: video/mp4, video/ogg, video/webm). Si este parámetro no está bien definido, el navegador puede tener problemas para reproducir el video.

##Herramientas de Conversión

Existen varias herramientas gratuitas que facilitan la codificación y conversión de videos a los formatos más utilizados:

Miro Video Converter: Sencillo y multiplataforma.

Firefogg: Extensión pensada para generar archivos Ogg/Theora.

HandBrake: Muy popular para codificar videos en H.264 y AAC.