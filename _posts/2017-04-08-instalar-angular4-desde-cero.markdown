---
layout: post
title:  "Instalar Angular 4 desde cero"
description: Recientemente ha sido liberada la nueva versión de Angular. El equipo de Angular se han centrado sobre todo en mejorarlo de forma interna en cuanto a seguridad y velocidad y han conseguido que sea totalmente compatible con Angular 2 y no trae grandes cambios a la hora de programar.
date: 2017-04-08 15:10:25 +0200
categories: dev, Angular, TypeScript
img: angular4.jpg
author: tecnual
---

Recientemente ha sido liberada la nueva versión de Angular. El equipo de desarrollo se ha centrado sobre todo en mejorarlo de forma interna en cuanto a seguridad y velocidad, han conseguido que sea compatible con la mayoría de las aplicaciones Angular 2 y no trae grandes cambios a la hora de programar. Empezaremos por instalar Angular 4 en nuestro equipo y desplegar nuestra primera aplicación.

Mi equipo de desarrollo es Ubuntu 16.04 y todos los comandos que se van a mostrar en este post se ejecutaran sobre esta plataforma, de todas maneras tanto para Windows como para Mac los cambios son mínimos y probablemente funcione en la mayoría de los equipos, pero hay que tenerlo en cuenta.

En primer lugar tenemos que asegurarnos de tener instalado la ultima versión de nodeJS, podéis seguir las indicaciones oficiales aquí: https://nodejs.org/es/download/

Para instalar Angular 4 existen varios métodos, estos son los principales:

* Manual.
* Actualizar un proyecto de Angular 2.
* Clonar un repositorio de Angular 4 desde GitHub.
* angular-cli (Command Line Interface)

# Manual
 El método manual es inviable, realmente engorroso y no lo recomiendo, aún así si hay alguien que le guste la aventura enlazo aquí a la [documentación oficial](https://angular.io/docs/ts/latest/)

# Actualizar un proyecto de Angular2

Para actualizar un proyecto de Angular2 basta con instalar las nuevas dependencias:

```
npm install @angular/{common,compiler,compiler-cli,core,forms,http,platform-browser,platform-browser-dynamic,platform-server,router,animations}@latest typescript@latest --save

```
Es importante comprobar en el archivo package.json que las dependencias se han actualizado correctamente a la nueva versión.

# Clonar un repositorio de Angular 4 desde GitHub.

Otra manera de instalar Angular 4 es a través de un repositorio de GitHub, para ello el equipo de Angular ha creado un repositorio especifico para instalar una aplicación por defecto.
He hecho un fork del repositorio oficial y he actualizado las dependencias a Angular 4, de esta manera la instalación se realiza en cuatro sencillos pasos:

```
git clone https://github.com/tecnual/quickstart.git quickstart
cd quickstart
npm install
npm start
```

En este momento ya tenemos nuestra aplicación disponible en http://localhost:3000/

# angular-cli

En mi opinión la mejor manera de instalar Angular es con su interfaz de comandos **angular-cli**.

A continuación describo los pasos a seguir...

## 1. Instalar de forma global las dependencias.

```
npm install -g @angular/cli

```
Para saber que lo hemos instalado correctamente y la versión que estamos utilizando escribimos:

```
ng -v

```
```
    _                      _                 ____ _     ___
   / \   _ __   __ _ _   _| | __ _ _ __     / ___| |   |_ _|
  / △ \ | '_ \ / _` | | | | |/ _` | '__|   | |   | |    | |
 / ___ \| | | | (_| | |_| | | (_| | |      | |___| |___ | |
/_/   \_\_| |_|\__, |\__,_|_|\__,_|_|       \____|_____|___|
           |___/
@angular/cli: 1.0.0-rc.1
node: 7.7.1
os: linux x64

```


## 2. Crear un nuevo proyecto.

```
ng new my-app --ng4

```
Esto es lo que genera nuestro nuevo proyecto, es un proceso que toma su tiempo, hay que tener paciencia.

Para que nuestro proyecto se instale con la nueva versión debemos habilitar el flag `--ng4` o actualizarlo después tal y como vimos en el apartado anterior.


## 3. Iniciamos nuestra aplicación.

```
cd my-app
ng serve --open

```
El comando `ng serve` arranca el servidor, observa los ficheros y reconstruye la aplicación a medida que realiza cambios en esos archivos.

Usando la opción `--open` se abrirá automáticamente nuestra aplicación en el navegador que tengamos configurado por defecto en la url http://localhost:4200/

Hasta aquí el proceso de instalación, a continuación vemos como podemos iniciar el proceso de desarrollo de nuestra aplicación realizando unos pequeños cambios en la app.

## 4. Editar un componente.

Angular-cli crea el primer componente de la aplicación. Es el componente raíz y se llama `app-root`. Lo puedes encontrar en ./src/app/app.component.ts.

Abrimos el componente y cambiamos el texto de la propiedad `title`, así podremos ver los cambios de nuestra aplicación de forma visual.

{% highlight typescript %}

// ./src/app/app.component.ts

import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'Por mucho que buscamos, este es el mejor mundo que hemos encontrado. ¡Hola Mundo!';
}
{% endhighlight %}

El navegador se actualizará automáticamente con los cambios realizados. Para que podamos ver mejor lo que hemos hecho vamos a cambiar también los estilos.

{% highlight css %}
/* ./src/app/app.component.css */

h1 {
  color: #369;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 150%;
}

{% endhighlight %}
