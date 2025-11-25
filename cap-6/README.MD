## Geolocalización en HTML5 cap6

La **geolocalización en HTML5** permite a los sitios web determinar la ubicación física del usuario mediante tecnologías como la dirección IP, redes Wi-Fi, torres celulares o hardware GPS.  
Sin embargo, por razones de **privacidad**, el consentimiento del usuario es obligatorio: ningún sitio puede acceder a la ubicación sin permiso explícito.

Los navegadores modernos (como **Chrome**, **Firefox**, **Safari**, **Opera** y versiones recientes de **Edge** e **IE9+**) implementan la **API de Geolocalización del W3C**, accesible mediante `navigator.geolocation`.

---

## Funciones principales

### getCurrentPosition()

La función principal es `getCurrentPosition()`, que recibe dos funciones:
- Una de **éxito**, con un objeto `position` que contiene:
  - `latitude`
  - `longitude`
  - Datos opcionales como `altitude`, `accuracy`, `heading` o `speed`.
- Una de **error**, para manejar casos de denegación, falta de señal o tiempo de espera.

Solo tres propiedades están garantizadas: `latitude`, `longitude` y `accuracy`; el resto depende del dispositivo y del hardware de ubicación.

```javascript
navigator.geolocation.getCurrentPosition(
  (pos) => {
    console.log(`Latitud: ${pos.coords.latitude}`);
    console.log(`Longitud: ${pos.coords.longitude}`);
  },
  (error) => console.error("Error obteniendo ubicación:", error),
  { enableHighAccuracy: true, timeout: 10000, maximumAge: 0 }
);
```

---

## Parámetros de configuración

Para ajustar el comportamiento de la API, se puede pasar un objeto de opciones con los siguientes parámetros:

- **enableHighAccuracy**: Prioriza la precisión, pero puede consumir más batería y tardar más.  
- **timeout**: Define el tiempo máximo de espera (en milisegundos).  
- **maximumAge**: Permite usar datos de ubicación almacenados en caché para ahorrar tiempo.

---

## Seguimiento en tiempo real

Cuando se requiere **seguimiento continuo** (por ejemplo, en una app de navegación o de fitness), se usa `watchPosition()`, que invoca la función de éxito cada vez que cambia la ubicación.  
Este método devuelve un identificador que puede usarse con `clearWatch()` para detener el seguimiento.

```javascript
const id = navigator.geolocation.watchPosition(
  (pos) => console.log("Nueva posición:", pos.coords),
  (err) => console.error(err)
);

// Detener el seguimiento
navigator.geolocation.clearWatch(id);
```

---

## Compatibilidad y soluciones para navegadores antiguos

Para navegadores antiguos sin soporte nativo (como **IE8 o inferiores**), existen soluciones alternativas como:
- **Google Gears**, un antiguo complemento que ofrecía geolocalización mediante Wi-Fi.  
- **geo.js**, una biblioteca que unifica distintas APIs (W3C, Gears, móviles antiguos) bajo una interfaz común.  

> Nota: `geo.js` no soporta `watchPosition()`, por lo que el seguimiento continuo debe implementarse mediante sondeo manual.

---

## Consideraciones de privacidad y seguridad

La API de Geolocalización exige consentimiento explícito del usuario, y los navegadores suelen mostrar un cuadro de diálogo pidiendo permiso.  
Además, las aplicaciones deben:
- Evitar almacenar coordenadas sin cifrado.
- No compartir ubicación sin consentimiento adicional.
- Implementar políticas de privacidad claras.  

También se recomienda usar **HTTPS**, ya que la geolocalización solo funciona en contextos seguros (sitios con certificado SSL).

---

## Ejemplo práctico: mapa interactivo

Un uso común es combinar la API con **Google Maps** o **Leaflet.js** para mostrar la ubicación en un mapa:



## Conclusión

La geolocalización en HTML5 es una herramienta poderosa, **respetuosa con la privacidad** y ampliamente compatible.  
Permite a los desarrolladores crear experiencias personalizadas, aplicaciones de mapas, servicios locales y más.  
No obstante, requiere un manejo cuidadoso de errores, control de precisión y estrategias de compatibilidad para navegadores más antiguos.

