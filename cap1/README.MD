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
##  El error del W3C: XHTML y la ilusión de la pureza

Tras publicar HTML 4.0 en 1997, el W3C abandonó HTML y apostó por **XHTML**: una reformulación de HTML bajo las reglas estrictas de XML.

- **XHTML 1.0 (1998)** incluyó una escapatoria: el **Apéndice C**, que permitía servir "XHTML" con el tipo MIME `text/html`, evitando el **manejo de errores draconiano** de XML (que detiene la renderización ante cualquier error).
- Pero **XHTML 1.1 (2001)** y el nunca terminado **XHTML 2.0** **eliminaron esa vía**, exigiendo el tipo MIME `application/xhtml+xml`.
- Como el 99% de las páginas web contienen errores, **XHTML 2.0 se volvió inviable en la práctica**.

Millones de páginas "dicen" ser XHTML (usan sintaxis como `<br />`), pero en realidad se sirven como `text/html` y se procesan como HTML.  
> **A menos que uses `application/xhtml+xml`, tu "XHTML" es solo HTML con maquillaje.**

##  Una visión alternativa: nace el WHATWG (2004)

Frente al rumbo del W3C, un grupo de actores clave —incluyendo **Mozilla y Opera**— presentó en 2004 una **visión competitiva** centrada en:

1. **Compatibilidad total con versiones anteriores**  
2. **Manejo de errores bien definido pero no catastrófico** (como en CSS, no como en XML)  
3. **Características basadas en casos de uso reales**  
4. **Proceso abierto y transparente**

El W3C rechazó esta propuesta (11 votos contra 8). En respuesta, los disidentes fundaron el **WHATWG** (*Web Hypertext Application Technology Working Group*), con el objetivo de **evolucionar HTML sin romper la web existente**.

El WHATWG:
- Documentó **cómo los navegadores realmente analizan HTML malformado** (ingeniería inversa de años de comportamientos).
- Creó **Web Forms 2.0** (mejoras a los formularios).
- Desarrolló **"Aplicaciones Web 1.0"**, que introdujo `<canvas>`, `<video>`, `<audio>` y otras APIs modernas.

## 🔹 De vuelta al W3C: la reconciliación (2006–2009)

Durante dos años y medio, el W3C y el WHATWG trabajaron en paralelo. Pero mientras **XHTML 2.0 seguía sin implementación real**, **HTML5 (del WHATWG) ganaba tracción** en navegadores como Firefox y Safari.

En **octubre de 2006**, **Tim Berners-Lee** anunció que el W3C **se uniría al esfuerzo del WHATWG**. Se formó un nuevo Grupo de Trabajo HTML con un mandato claro:

> **Mejorar HTML de forma incremental, manteniendo compatibilidad, y trabajar en paralelo con XHTML bien formado.**

Una de sus primeras decisiones fue renombrar **"Aplicaciones Web 1.0" como "HTML5"**.

Finalmente, en **octubre de 2009**, el W3C **disolvió oficialmente el Grupo de Trabajo de XHTML 2**, reconociendo que el futuro de la web no estaba en reinventar HTML desde cero, sino en **evolucionarlo desde la realidad existente**.

## Conclusión central

HTML5 no es un estándar impuesto desde lo alto, sino el resultado de **décadas de colaboración implícita entre desarrolladores, navegadores y usuarios**. Su éxito se basa en:

- Respetar la **historia funcional** de la web  
- Priorizar la **experiencia real sobre la pureza teórica**  
- Entender que **los estándares deben seguir a la implementación, no dictarla**

> **"Los que ganan son los que envían."**  
> — Y en la web, lo que cuenta es que **funcione para todos, no que sea perfecto para unos pocos**
