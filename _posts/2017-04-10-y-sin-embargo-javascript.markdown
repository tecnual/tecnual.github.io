---
layout: post
title:  "Y sin embargo... JavaScript"
description: Hasta hace poco JavaScript se usaba principalmente en el navegador del lado del cliente para dar dinamismo a las páginas web. Ahora se ha convertido en el lenguaje universal y prácticamente cualquier aplicación se puede realizar con JavaScript...
date: 2017-04-09 15:10:25 +0200
categories: JavaScript, programación
img: nube-javascript.jpg
author: tecnual
---

### ¿De dónde venimos?

JavaScript nació a principios de los 90', por la necesidad de controlar cierta complejidad
en las páginas web que ya se empezaba a demandar en aquella época. Fruto de la alianza de Netscape y Sun Microsystems
se incluyó por primera vez JavaSript en el navegador Netscape Navigator. La elección del nombre fue exclusivamente por márketing
ya que Java era la palabra de moda en el Internet de la época. En 1997 Netscape decidió estandarizar el nuevo lenguaje
y envió la especificación JavaSript 1.1 al Organismo ECMA.

### ¿Hacia dónde vamos?

Desde hace ya varios años JavaScript es el lenguaje más utilizado por los
programadores según los [datos extraídos](http://githut.info/) de GitHub.

Hasta hace poco JavaScript se usaba principalmente en el navegador del lado del cliente,
para dar dinamismo a las páginas web. Con la aparaición de Node.js se ha extendido su uso también del lado del servidor,
Electron hace posible el desarrollo de aplicaciónes de escritorio multiplataforma
e Ionic, por su parte, en aplicaciones para dispositivos móviles. Es así como se ha convertido en el "lenguaje universal"
y prácticamente cualquier aplicación se puede realizar con JavaScript.

### ¿Quiénes somos?

Se han hecho muy populares los frameworks y librerías como `Jquery` y más recientemente `Angular`, `Ember`, `React`,...
que han trasladado gran parte de la lógica de la aplicación a la parte del cliente,
dejando en el servidor básicamente el acceso y el control de los datos.
En este sentido `JSON` (JavaScript Object Notation) ha sustituido a XML como modelo de representación de los datos
utilizado incluso por bases de datos como `mongoDB` y muy útil a la hora de desarrollar
una `API RestFull`.

Otra parte importante en la fase de desarrollo es la gestión de tareas automatizadas, compilar, minificar archivos, concatenar,
manejo de errores y estilos (linter), testing...  todo esto se puede simplificar con la ayuda de `gulp`, `grunt` o `webpack`.

Se puede gestionar con soltura diferentes paradigmas de programación como la programación funcional o la
programación asíncrona, han aparecido nuevas figuras, como los observables,
promesas, servicios,... nuevos patrones de diseño MVVC, FLUX...

En definitiva cualquier persona que se quiera dedicar al desarrollo de software a nivel profesional
tiene en Javascript la herramienta más poderosa de todas y es prácticamente imprescindible.

{% highlight typescript %}
console.log('La vida sería mucho más sencilla si pudiéramos echar un vistazo al código fuente.')
// prints 'La vida sería mucho más sencilla si pudiéramos echar un vistazo al código fuente.' to STDOUT.

{% endhighlight %}
