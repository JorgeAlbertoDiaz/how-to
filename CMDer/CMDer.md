# CMDer
[Sitio Oficial][cmder-oficial],
[Repositorio GitHub][cmder-git]

## Descripción
Es un emulador de consola totalmente portable basado en [ConEmu] y en [Clink] que extiende la funcionalidad del tradicional cmd de Windows e incluso su powershell.


## Descarga
En la sección de descarga nos da a elegir entre dos versiones, ambas se descargarán como un zip:

![imagen](https://i.ibb.co/WfXpfm6/versiones-cmder.png)

+ **Mini**: La misma funcionalidad de cmd de windows sólo que a diferencia de la tradicional consola de windows a esta podremos personalizar a nuestro gusto al igual que lo hariamos en un entorno unix.
+ **Full**: Además de la personalización, esta version intregra la mayoria de los comandos de unix en windows como asi tambien [Git para Windows].

> Se recomienda descargar y utilizar la versión full.

## Instalación

Una vez descargado el archivo, podríamos simplemente descomprimirlo en cualquier lugar y ya comenzar a utilizarlo, pero recomiendo seguir los siguientes pasos para lograr una mejor integración.

**• Paso 1.** Descomprimir el archivo en la ruta `C:\Users\[User]\AppData\Roaming\Cmder`.
  1. Abre la aplicación Ejecutar en Windows con la siguiente combinación de teclas <kbd>Windows</kbd> + <kbd>R</kbd>.
  2. introduce el siguiente texto `%APPDATA%`.
  3. Crea una carpeta llamada `cmder`.
  4. Extrae el contenido del archivo descargado en dicha carpeta.

**• Paso 2.** Agregar las siguientes variables del entorno del Sistema:

| Variable | Valor de la Variable |
| ---- | ---- |
|`CMDER_ROOT` | `C:\Users\<User>\AppData\Roaming\Cmder` |
| `ConEmuDir` | `C:\Users\<User>\AppData\Roaming\Cmder\vendor\conemu-maximus5` |

> Como ubicamos a la aplicación en una carpeta que pertenece al usuario, lo recomendable es modificar las variables de ese usuario.

**• Paso 3.** Reiniciar el Sistema:
Una vez agregadas las variables podriamos reinicar el sistema o bien cerrar sesión y entrar de nuevo para poder probar que las variables fueron agregadas y que funcionan correctamente.

**• Paso 4.** Probar las variables que agregamos:
- Abre la aplicación Ejecutar en Windows con la siguiente combinación de teclas <kbd>Windows</kbd> + <kbd>R</kbd>
- introdce el valor `%CMDER_ROOT%` y presiona <kbd>Enter</kbd> `%ConEmuDir%`. Si se abren los directorios respectivos es que lo configuramos correctamente.



[ConEmu]: https://conemu.github.io/
[Clink]: https://github.com/mridgers/clink
[cmder-oficial]: https://cmder.net/
[cmder-git]: https://github.com/cmderdev/cmder
[Git para Windows]: https://gitforwindows.org/
