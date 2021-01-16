# NVM
Es una herramienta que nos permite instalar y manejar distintas versiones de NodeJS en nuestro equipo.

## Instalación (o actualiación) para Linux
Para instalar (o actualizar) **nvm** debemos descargar y ejecutar un script que esta disponible en su [repositorio oficial de github][1]. Podemos descargar este script y ejecutarlo manualmente o bien podríamos hacerlo meidante `cURL` o `Wget`.

**opción con cURL**
```bash
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
```

**opción Wget**
```bash
$ wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
```

## Verificar Instalación
Para verificar que la instalación haya sido exitosa puedes ejecutar alguno de los siguientes comandos:

**opción 1**
```bash
$ command -v nvm
nvm
```

**opción 2**
```bash
$ nvm --version
0.37.2
```

## Referencias
- [Sitio oficial de **nvm**][1]


[1]: https://github.com/nvm-sh/nvm
