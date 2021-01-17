# Angular desde Docker
Esto es una guía del paso a paso que debemos seguir para crear un proyecto desde cero con Angular desde Docker y como trabajar con Angular CLI desde otro contenedor Docker.

## Requisitos
- Tener instalado y configurado Docker en tu sistema.

## Creando un nuevo Proyecto
Vamos a crear un Dockerfile con el que vamos a compilar una imagen de docker que utilizaremos para ejecutar un contenedor con el que vamos a poder crear nuestra aplicación de Angular.

### Estructura del Proyecto

```
mi-proyecto/
├── builder/
|   ├── Dockerfile
├── Dockerfile
└── docker-compose.yml
```

### **Paso 1**: Crear el `./builder/Dockerfile`
Nos dirigmos a la carpeta donde vamos a trabajar con nuestra app y lo primero que vamos a hacer será crear un `Dockerfile` dentro de una carpeta llamada `builder`.

```
mi-proyecto/builder/Dockerfile
```

```Dockerfile
FROM node:lts-alpine
RUN npm install -g @angular/cli
WORKDIR /app
```

### **Paso 2**: Crear la `imagen` de docker
Vamos a compilar el Dockerfile creado en el punto anterior para crear nuestra imagen.

```sh
$ sudo docker build -t ngbuilder ./builder
```

> Esperamos a que el proceso termina y opcionalmente podemos verificar que la imagen se haya creado exitosamente con el siguiente comando:

```sh
$ sudo docker images | grep ngbuilder
```

### **Paso 3**: Ejecutar el `contenedor` de la imagen que creamos en el punto anterior
Ejecutar el contenedor de la imagen creada en el punto anterior.

```sh
$ sudo docker run -itd -v ${PWD}:/app --name angularWeb ngbuilder
```

> Esperamos a que el proceso termina y opcionalmente podemos verificar que la imagen se haya creado exitosamente con el siguiente comando:

```sh
$ sudo docker ps -a | grep angularWeb
```

### **Paso 4**: Creamos el proyecto de Angular
Desde el contenedor que ejecutamos en el punto anterior vamos a crear el proyecto de Angular con la herramienta `Angular CLI`.

```sh
$ sudo docker exec -it angularWeb ng new projectName --directory=.
```

> Una vez finalizado este paso vamos a tener todos los archivos generados en nuestro directorio del proyecto.

### **Paso 5**: Cambiamos el propietario de los archivos generados
Todos los archivos generados en el punto anterior pertenecen al usuario `root` dentro del grupo `root`, para poder evitar problemas lo mejor es cambiar la propiedad a nuestro usuario.

```sh
$ sudo chown -R $USER:$(id -gn $USER) ./*
$ sudo chown -R $USER:$(id -gn $USER) ./.[^.]*
```

### **Paso 6**: Eliminar el contenedor
Ya no necesitaremos el contenedor por lo que procedemos a eliminarlo.

```sh
$ sudo docker rm -f angularWeb
```

## Crear un Enviroment para desarrollar con Angular

### **Paso 1**: `Dockerfile` principal

Vamos a crear o modificar el archivo Dockerfile de la carpeta raíz del proyecto para que quede de la siguiente manera:

```Dockerfile
FROM node:lts-alpine
RUN npm install -g @angular/cli
WORKDIR /app
COPY package.json  ./
RUN npm install
EXPOSE 4200
CMD ["ng", "serve", "--host", "0.0.0.0"]
```

### **Paso 2**: Configurar nuestro `docker-compose`
Este paso es importante porque desde este archivo podemos incluir este y otros servicios a nuestra aplicación de Angular.

```docker-compose
version: '3'
services:
    web:
        build: .
        ports: 
            - "4200:4200"
        volumes:
            - "/app/node_modules" 
            - ".:/app"
```

### **Paso 3**: Ejecutamos nuestro `docker-compose`

```
$ sudo docker-compose up -d
```

## Ejecutando comandos de `Angular CLI`
Si seguimos correctamente los pasos anteriores y si tenemos corriendo nuestro `docker-compose` vamos a poder correr cualquier comando de `Angular CLI` de la siguiente manera:

```
$ sudo docker-compose exec web ng generate component xyz
```

> El ejemplo de arriba es para generar un nuevo componente xyz pero puedas usar este u otros comandos.
