Como desarrolladores, a menudo nos enfrentamos con decisiones que afectarán todo 
 arquitectura de nuestras aplicaciones. Una de las decisiones centrales que los desarrolladores web deben 
 make es donde implementar la lógica y el renderizado en su aplicación. Esto puede ser 
 Es difícil, ya que hay varias formas diferentes de crear un sitio web.

Nuestra comprensión de este espacio está informada por nuestro trabajo en Chrome hablando con 
 sitios grandes en los últimos años. En términos generales, alentaríamos 
 los desarrolladores deben considerar la representación del servidor o la representación estática en un 
 enfoque de rehidratación.

Para entender mejor las arquitecturas que estamos eligiendo cuando hacemos 
 esta decisión, necesitamos tener una comprensión sólida de cada enfoque y 
 terminología consistente para usar cuando se habla de ellos. Las diferencias entre 
 Estos enfoques ayudan a ilustrar las compensaciones de renderizar en la web a través de 
 La lente del rendimiento.

## Terminología {: #terminología}

**Representación**

- **SSR:** Representación del lado del servidor **:** representación de una aplicación universal o del lado del cliente para  HTML en el servidor.
- **CSR:** Representación del lado del cliente **:** renderizar una aplicación en un navegador, generalmente  usando el DOM.
- **Rehidratación:** "arrancar" las vistas de JavaScript en el cliente de modo que  Reutilice el árbol y los datos DOM del HTML del servidor.
- **Representación previa:** ejecutar una aplicación del lado del cliente en el momento de la compilación para capturar  su estado inicial como HTML estático.

**Actuación**

- **TTFB:** Tiempo hasta el primer byte: visto como el tiempo entre hacer clic en un enlace y  la primera parte del contenido que entra.
- **FP:** Primera pintura: la primera vez que un píxel se vuelve visible para el  usuario.
- **FCP:** Primera pintura satisfactoria: el momento en que se solicita el contenido (artículo  cuerpo, etc.) se hace visible.
- **TTI:** Time To Interactive: el momento en que una página se vuelve interactiva  (eventos cableados, etc.).

## Representación del servidor {: # representación del servidor}

*La representación del servidor genera el HTML completo para una página en el servidor en respuesta 
 a la navegación Esto evita viajes de ida y vuelta adicionales para la obtención de datos y 
 plantillas en el cliente, ya que se maneja antes de que el navegador obtenga un 
 respuesta.*

La representación del servidor generalmente produce una [primera pintura](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics#first_paint_and_first_contentful_paint) rápida (FP) y una [primera 
 Pintura contenta](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics#first_paint_and_first_contentful_paint) (FCP). Ejecutar la lógica de la página y la representación en el servidor hace que 
 posible evitar el envío de muchos JavaScript al cliente, lo que ayuda a lograr 
 un [tiempo](https://developers.google.com/web/tools/lighthouse/audits/time-to-interactive) rápido [para interactuar](https://developers.google.com/web/tools/lighthouse/audits/time-to-interactive) (TTI). Esto tiene sentido, ya que con el servidor 
 En realidad, solo estás enviando texto y enlaces al navegador del usuario. Esta 
 el enfoque puede funcionar bien para un amplio espectro de dispositivos y condiciones de red, 
 y abre interesantes optimizaciones del navegador, como el análisis de documentos en tiempo real.

<img src="../../images/2019/02/rendering-on-the-web/server-rendering-tti.png" alt="Diagram showing server rendering and JS execution affecting FCP and TTI" width="350">
