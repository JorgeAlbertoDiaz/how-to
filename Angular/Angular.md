# Angular
Angular es un framework de diseño de aplicaciones y una plataforma para desarrollar aplicaciones del tipo **single-page app** de manera eficiente, moderna y sofisticada.

## Requisitos
Debes tener instalado `node` y `npm`. Para instalarlo en tu sistema siguie la [siguiente guía][2].

## Instalación
Para tener angular funcionando solo debemos instalar su herramienta llamada `Angular CLI`.
### Angular CLI
Es una herramienta que nos permite entre otras cosas a crear nuestros proyectos y a generar sus componentes.
Para instalarlo debemos ejecutar el siguiente comando:

```sh
$ npm install -g @angular/cli
```

## Primer Proyecto
Para crear un nuevo `workspace` y una nueva aplicación debemos ejecutar el siguiente comando:

```sh
$ ng new my-app
```

Luego se ejecutará un asistente el cual nos pedirá que aceptemos o no unas cuantas configuraciones.
Una vez que finalice la configuración previa, se instalarán las dependencias necesarias para tener nuestra app funcionando.

## Ejecutar nuestra aplicación
Primero debemos ingresar al directorio donde se generó nuestra app y luego ejecutar el comando `ng serve --open`.

```sh
$ cd my-app
$ ng serve --open
```
Una vez finalice la ejecución del comando de arriba se nos abrirá automáticamente una ventana como la siguiente:

![Primera APP Angular](https://angular.io/generated/images/guide/setup-local/app-works.png)


## Referencias
- [Sitio Oficial de Angular][1]
- [Guía de instalación de NodeJS][2]

[1]: https://angular.io/
[2]: https://github.com/JorgeAlbertoDiaz/how-to/blob/main/NodeJS/NodeJS.md
