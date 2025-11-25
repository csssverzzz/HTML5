# Resumen de A Form of Madness del cap9

Este documento contiene un resumen detallado del capítulo **"A Form of
Madness"**, el cual analiza las nuevas capacidades que HTML5 introduce
en los formularios web y cómo estas mejoras pueden usarse de inmediato
gracias a su degradación elegante.

## Resumen

El capítulo destaca que las nuevas características de HTML5 para
formularios son **compatibles incluso con navegadores antiguos**, porque
cuando un navegador no reconoce un tipo de entrada moderno, simplemente
lo trata como un campo de texto estándar.

### Atributos de utilidad

-   **placeholder**\
    Muestra un texto de ejemplo mientras el campo está vacío. Es
    ignorado sin problemas por navegadores antiguos.

-   **autofocus**\
    Asigna el foco automáticamente a un campo al cargar la página. Es
    más consistente que las soluciones anteriores con JavaScript. Se
    recomienda añadir un pequeño script de respaldo solo para
    navegadores que no lo soporten.

### Nuevos tipos de entrada en HTML5

HTML5 añade varios tipos que mejoran la experiencia del usuario,
especialmente en móviles:

-   **email** y **url**\
    Activan teclados optimizados en dispositivos móviles como iPhone.

-   **number**\
    Permite rangos (`min`, `max`, `step`) y puede mostrarse como
    spinbox. Incluye métodos JavaScript como `stepUp()` y
    `valueAsNumber`.

-   **range**\
    Control deslizante ideal para valores aproximados.

-   **date, time, month, week, datetime-local**\
    Totalmente soportados en algunos navegadores como Opera; se degradan
    a texto en otros, pero pueden complementarse con bibliotecas
    JavaScript.

-   **search**\
    En Safari y Chrome añade UI nativa como botón para borrar.

-   **color**\
    Abre el selector de color del sistema (soportado desde Opera 11).

### Validación nativa

Una de las mejoras más potentes: **la validación integrada del
navegador**.

Incluso sin JavaScript, el navegador verifica que:

-   un correo tenga formato válido,
-   un número esté en el rango correcto,
-   un campo marcado como **required** no esté vacío.

La validación puede desactivarse con `novalidate`. Aun así, siempre se
recomienda validar también del lado del servidor.

## Conclusión

HTML5 vuelve los formularios **más inteligentes, semánticos y usables**
sin necesidad de complejos scripts. Su diseño progresivo permite adoptar
estas funciones desde hoy, mejorando la experiencia en navegadores
modernos sin afectar a los antiguos.