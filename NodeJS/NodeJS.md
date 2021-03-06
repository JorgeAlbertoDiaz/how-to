# Node.js

  ## Dependencias
   
  ### Librerías
 
  - **V8**: Proporciona a Node.js un motor JavaScript el cual Node.js controla a través de la API V8 C++. V8 es mantenido por Google para ser usado en chrome. [Más sobre V8][2].
  - **libuv**: Es una librería desarrollada en C que proporciona mecanismos para manejar el sistema de archivos, DNS, red, procesos secundarios, canalizaciones, manejo de señales, sondeo y transmisión. [Más sobre libuv][3].
  - **llhttp**: Es un librería desarrolla en Typescript y C. Se encarga del análisis HTTP. [Más sobre llhttp][4].
  - **c-ares**: Para algunas solicitudes DNS, Node.js usa esta librería dearrollada en C. [Más sobre c-ares][5].
  - OpenSSL: OpenSSL se usa mucho en los módulos de **tls** y **crypto**. [más sobre OpenSSL][6].
  - **zlib**: Se usa para la compresión y descompresión de interfaces. [Más sobre zlib][7].
  
  ### Herramientas
  
  - **npm**: Es un administrador de paquetes de alta calidad que maneja la modularidad en Node.js. [Más sobre npm][8].
  - **gyp**: Maneja el sistema de compilación, es un generador de proyectos basado en python y copiado de V8. [Más sobre gyp][9].
  - **gtest**: también conocida como **GoogleTest**, es una librería C/C++ diseñada para probar el código nativo, esta librería fue tomada de **chromium**. [Más sobre gtest][10].
  - **nvm**: **N**ode **V**ersion **M**anager, es una herramienta que nos permite instalar y gestionar las versiones que tengamos instaladas en el sistema de NodeJs. Es la forma recomendada de instalar y usar NodeJS. [Más sobre nvm][13].
  
  ## Instalación de NodeJS en Linux
  
  ### Instalación mediante nvm
  Este sería el método de instalación recomendado de NodeJS.
   
   #### **Paso 1.**: Instalar nvm
   Para instalar nvm puedes seguir [esta guia][14].
   
   #### **Paso 2.**: Instalar Nodejs con nvm
   En este caso vamos a instalar la última versión LTS, para verificar cual es puedes visitar el [sitio oficial de NodeJS][9].
   
```bash
$ nvm install 14.15.4
   
Downloading and installing node v14.15.4...
Downloading https://nodejs.org/dist/v14.15.4/node-v14.15.4-linux-x64.tar.xz...
################################################################################################################# 100.0%
Computing checksum with sha256sum
Checksums matched!
Now using node v14.15.4 (npm v6.14.10)
Creating default alias: default -> 14.15.4 (-> v14.15.4)
```
   > Podríamos poner directamente `nvm install node` pero es buena práctica especificar que versión estamos instalando.
   
   #### Verificar instalación
   Podemos verificar la instalación el siguiente comando:
   
   ```bash
   $ node --version
   v14.15.4
   ```
   
   > Node 14.15.4 ya viene con **npm 6.14.10**, podemos verificarlo con el comando `npm --version`.
   
  ## Referencias:
  
  #### Sitio Oficial:
  - [Sitio Oficial de Nodejs][9]
  - [Repositorio oficial Github][10]
 
 #### Documentación sobre librerías usadas por Node.js.
 - [Documentacíon sobre Node.JS][1]
 - [Documentación sobre V8][2]
 - [Documentación sobre libuv][3]
 - [Documentación sobre llhttp][4]
 - [Documentación sobre c-ares][5]
 - [Documentación sobre openSSL][6]
 - [Documentación sobre zlib][7]
 
 #### Documentación sobre herramientas usadas por Node.js.
 - [Documentación sobre npm][8]
 - [Documentación sobre gyp][9]
 - [Documentación sobre gtest (Google Test)][10]
 - [Documentación sobre nvm][13]
 
  [1]: https://nodejs.org/en/docs/
  [2]: https://v8.dev/docs
  [3]: http://docs.libuv.org/en/v1.x/
  [4]: https://github.com/nodejs/llhttp
  [5]: https://c-ares.haxx.se/docs.html
  [6]: https://www.openssl.org/docs/
  [7]: https://www.zlib.net/manual.html
  [8]:https://docs.npmjs.com/
  [9]: https://gyp.gsrc.io/docs/UserDocumentation.md
  [10]: https://github.com/google/googletest
  [11]: https://nodejs.org/es/
  [12]: https://github.com/nodejs/node
  [13]: https://github.com/nvm-sh/nvm
  [14]: https://github.com/JorgeAlbertoDiaz/how-to/blob/main/NodeJS/instalaci%C3%B3n%20de%20nvm.md
