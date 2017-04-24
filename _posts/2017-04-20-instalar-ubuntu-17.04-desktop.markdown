---
layout: post
title:  "Instalar Ubuntu 17.04 Desktop"
description: En el mes de abril Ubuntu libera su nueva versión, este año corresponde a la 17.04 Zesty Zapus. Zapus es un pequeño ratón saltarín de Estados Unidos y Zesty es un adjetivo que se podría traducir por "gran energía y entusiasmo".
date: 2017-04-20 12:00:00 +0200
categories: linux, ubuntu, devops
img: posts/4/Ubuntu17.jpg
author: tecnual
---

Como todos los años en el mes de abril Ubuntu libera su nueva versión, este año corresponde a la 17.04 Zesty Zapus. Zapus es un pequeño ratón saltarín de Estados Unidos y Zesty es un adjetivo que se podría traducir por "gran energía y entusiasmo".

A diferencia de las versiones LTS, que corresponden a los números pares y que tienen cinco años de mantenimiento, la versión 17.04 solo tiene nueve meses de mantenimiento. Es una versión ideal para equipos de desarrollo, ya que incorpora todas las novedades y prepara el sistema para los futuros cambios. Considero que un buen desarrollador debe mantener su equipo actualizado siempre a la última versión para localizar antes los problemas que puedan surgir en los sistemas en producción, además, realizar una instalación limpia sirve para soltar lastre de pruebas y aplicaciones fallidas que tengamos hasta ese momento.

### Requisitos del sistema.

+ Procesador de doble nucleo a 2 GHz o superior
+ 2 GB de memoria RAM
+ 25 GB de espacio libre en disco
+ Puerto USB o lector de DVD para la instalación.
+ Acceso a Internet recomendado.

### Preparación del medio de instalación.

Lo primero que tenemos que hacer es descargar la imagen iso desde la web oficial de [Ubuntu](https://www.ubuntu.com/download/desktop). En este caso la versión que vamos a instalar es [Ubuntu 17.04 64-bit PC (AMD64) Zesty Zapus](http://releases.ubuntu.com/17.04/ubuntu-17.04-desktop-amd64.iso).

En este pequeño tutorial vamos a instalar Ubuntu a través de un pendrive USB, pero también se puede quemar la imagen en un DVD o desde un repositorio en red. Desde Windows recomiendo usar Rufus para [instalar una imagen ISO en USB](https://www.ubuntu.com/download/desktop/create-a-usb-stick-on-windows), pero desde otra versión de Ubuntu se puede hacer fácilmente con la herramienta "Creador de discos de arranque"...

![Creador de discos de arranque](/assets/images/posts/4/captura-discos-arranque.png)

Al insertar el pendrive podremos ver el dispositivo en el apartado `Disco a usar`. Seguidamente seleccionamos la imagen ISO que hemos descargado pulsando en el botón `Otro` y navegando hasta su ubicación. Pulsamos `Crear disco de arranque` esperamos a que finalice el proceso y ya tendremos listo nuestro pendrive con la imagen de Ubuntu 17.04.

A continuación detallaré el proceso de instalación propiamente dicho paso a paso.

## Instalación

Insertamos el pendrive USB en cualquier puerto disponible y configuramos la bios para que arranque desde esa misma unidad.

### Idioma

Seleccionamos el idioma que nos guiará durante la instalación.
![Idioma](/assets/images/posts/4/captura-idioma.png)

Seleccionamos *Instalar Ubuntu*.
![Instalar Ubuntu](/assets/images/posts/4/captura-ubuntu-instalacion.png)

### Preparamos la instalación.

Checkeamos las dos casillas que aparecen en esta ventana.

+ **Descargar actualizaciones al instalar Ubuntu.** Es recomendable si disponemos de buena conexión a Internet ya que instalará las actualizaciones que hayan podido aparecer para esta nueva versión, que serán sobre todo para corregir pequeños defectos.
+ **Instalar Software de terceros para multimedia, MP3, Flash y compatibilidad con gráficas y WI-FI.** Es software imprescindible, pero Ubuntu pide confirmación para poder instalarlo ya que se trata de software de terceros sujetos a sus propias licencias.

![Preparando la instalción](/assets/images/posts/4/captura-preparando-instalacion.png)

### Tipo de instalación

En este apartado debemos seleccionar cómo queremos instalar Ubuntu en nuestro equipo. Podemos instalarlo junto a otro sistema que tengamos ya instalado, borrar todo y utilizar todo el disco para realizar la instalación o más opciones. En esta ocasión seleccionamos `Más opciones` para configurar el tipo de instalación de forma manual.

![Tipos de instalción](/assets/images/posts/4/captura-tipos-instalacion.png)

En mi caso voy a utilizar todo el disco para realizar una instalación limpia pero de forma manual, si tenéis más sistemas instalados o alguna otra partición más tenéis que tener especial cuidado en esta parte de la instalación para no borrar discos ni particiones que necesitéis.

![Discos y particiones](/assets/images/posts/4/captura-tipos-instalacion-discos.png)

Haciendo click en `+` abajo a la izquierda se nos abre un cuadro de diálogo para crear una nueva partición. Voy a crear dos particiones, una para el sistema y otra para los datos. Una de las novedades en esta versión de Ubuntu es que ya no es necesario crear una partición de intercambio (Swap), ya que es sistema utilizará un archivo dedicado para ello.
Este apartado es el que más puede diferir dependiendo del uso que vayáis a hacer de vuestra máquina. Aquí pongo una configuración más o menos estándar y que puede funcionar muy bien en la mayoría de los equipos. Sed libres para adaptar esta configuración a vuestras necesidades.

![Particiones](/assets/images/posts/4/captura-tipos-instalacion-particiones.png)

Para la partición del sistema:

+ **tamaño:** *100.000 MB.*
+ **Tipo de la nueva partición:** *Primaria*
+ **Ubicación de la nueva partición:** *Al principio de este espacio*
+ **Utilizar como:** *Sistema de ficheros ext4 transaccional*
+ **punto de montaje:** `/`  

Para la partición de datos:

+ **tamaño:** *400.000 MB. (El resto del disco)*
+ **Tipo de la nueva partición:** *Lógica*
+ **Ubicación de la nueva partición:** *Al principio de este espacio*
+ **Utilizar como:** *Sistema de ficheros ext4 transaccional*
+ **punto de montaje:** `/home`  

Una vez creadas las particiones y asegurarnos de no que todo está correctamente hacemos click en `Instalar ahora`. Nos pedirá confirmación para sobreescribir el disco y borrar posibles particiones anteriores. Continuamos para seleccionar nuestra ubicación...


![Ubicación](/assets/images/posts/4/captura-ubicacion.png)

Seleccionamos nuestra ubicación lo más aproximado posible y hacemos click en `Continuar`.

Es el momento de elegir nuestra disposición de teclado...


Hacemos click en `Continuar`.

### Identificación

![Identificación](/assets/images/posts/4/captura-identificacion.png)

+ **Su nombre:** Nombre apellidos o alias.(Se mostrará como identificación del usuario).
+ **Nombre de su equipo:** Elegimos un nombre identificativo para nuestra máquina.
+ **introduzca un nombre de usuario:** Tu nombre de usuario para esta máquina (Si puede ser breve e identificativo).
+ **Contraseña:** Segura, fácil de recordar para el usuario, con letras números y a ser posible con más de 5 caracteres.
+ **Iniciar sesión automáticamente:** Elegir esta opción solo si este equipo se va a utilizar por un solo usuario, de lo contrario puede ser un importante agujero de seguridad.
+ **Cifrar mi carpeta personal** Recomendable si hay más sistemas operativos instalados en la misma máquina y no quieres que se pueda acceder a esta carpeta desde otro lugar.

### Instalación y copia de archivos.

Al hacer click en `Continuar` se inicia el proceso de inatalación y copia de archivos en nuestro equipo, que puede durar apenas unos minutos y va en función de la potencia de nuestra máquina y de la velocidad de nuestra conexión a Internet.

![Instalación y copia de archivos](/assets/images/posts/4/captura-archivos.png)

*La instalación se ha completado. Necesita reiniciar el equipo para poder usar la nueva instalación*. Pulsamos el botón de reiniciar y extraemos la unidad que hayamos utilizado como medio (USB o DVD) para realizar la instalación.

![Reiniciar, instalación finalizada](/assets/images/posts/4/captura-reiniciar.png)

¡Enhorabuena! Ya tenemos instalado Ubuntu 17.04 Zapus Zesty.

![Ubuntu 17.04 Zapus Zesty](/assets/images/posts/4/captura-escritorio.png)



{% highlight typescript %}
console.log('Las cosas más importantes no son cosas')
// prints 'Las cosas más importantes no son cosas' to STDOUT.

{% endhighlight %}
