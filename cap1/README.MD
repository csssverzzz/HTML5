# ¿CÓMO LLEGAMOS HASTA AQUÍ?CAP1

---
##  MIME Types

HTML5 no puede entenderse sin primero comprender los **tipos MIME**.  
Cada vez que un navegador solicita una página, el servidor envía encabezados que le dicen al navegador cómo interpretar el contenido.  
El más importante es:


Este define que el recurso es una página HTML.  
Imágenes, scripts, hojas de estilo y otros archivos también poseen su propio tipo MIME, sin el cual la web no podría funcionar.

---

##  Una larga digresión sobre cómo se crean los estándares

Los elementos de HTML no surgen de la nada: alguien los propone, discute y finalmente los integra en el estándar.  
Esto se puede rastrear en listas de correo y debates públicos que muestran cómo se tomaron las decisiones.  

Ejemplo: **¿Por qué tenemos una etiqueta `<img>`?**

---

##  La creación del elemento `<img>`

El 25 de febrero de 1993, **Marc Andreessen** propuso la etiqueta `<IMG SRC="url">` para incrustar imágenes en documentos HTML.

Su idea generó debates:

* Algunos preferían `<ICON>` o `<INCLUDE>`.
* Tim Berners-Lee sugirió usar atributos `REL="EMBED, PRESENT"`.
* Otros discutieron la importancia de MIME para soportar múltiples formatos.

Al final, Andreessen implementó `<img>` en el navegador Mosaic, y **el código que se publica primero suele ser el que gana**.

---

##  Una línea ininterrumpida

Desde 1990 hasta 2010, HTML ha evolucionado pero mantiene una **línea continua**:

* HTML 2.0
* HTML 3.2
* HTML 4.0
* Y finalmente HTML5

Cada versión ha sido una mezcla de formalizar lo que ya existía e introducir nuevas capacidades.

---

##  Línea de tiempo del desarrollo de HTML (1997 - 2004)

* **1997**: Se publica HTML 4.0, el W3C cierra el grupo de trabajo.
* **1998**: Surge XHTML 1.0, que reescribe HTML en XML.
* **1999**: Aparece “XHTML Extended Forms” → más tarde “XForms”.
* **2001**: XHTML 1.1 elimina la compatibilidad hacia atrás.
* **2003**: XForms 1.0 es publicado.
* **2004**: Inicia un nuevo enfoque que culminaría en **HTML5**.

---

## 7. Todo lo que sabes sobre XHTML está mal

XHTML introdujo **manejo de errores draconiano**.  
Mientras que HTML tradicionalmente era tolerante con errores (como etiquetas sin cerrar), XHTML exigía perfección, lo que generó múltiples problemas de adopción.

---

