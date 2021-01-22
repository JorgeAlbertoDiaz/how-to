# Que hacer luego de instalar Ubuntu Server 20.04.01 (live server)

## Actualizar el Sistema

Esto es un apartado importante en la seguridad y estabilidad del sistema, por lo que lo primero que hay que hacer luego de instalar ubuntu-server es actualizar el sistema y todos sus paquetes y dependencias.

```sh
sudo apt update && sudo apt upgrade -y
```

> Ponemos nuestra contraseña y esperamos a que finalice el proceso de instalación.

## Recomendaciones Generales (Opcionales)

Cuando instalamos el sistema solo tenemos una única cuenta, la del superusuario o `root`.

No es seguro ni recomendable trabajar directamente con una sesión directamente como `root`, aunque usemos SSH en el servidor,
en su lugar se recomienda crear y usar cuentas de usuario sin privilegios para la mayoría de las tareas.

**Solo usaremos la cuenta `root` cuando ninguna otra cuenta de usuario de nivel administrador pueda resolver (por limitación de sus privilegios) una situación de gravedad**.

### Crear cuentas de usuarios
Para crear un nuevo usuario vamos a utilizar el comando `adduser`, el cual no simplemente lo crea sino que además hace otras tareas importantes.

```sh
sudo adduser nombre-del-usuario
```

1. Crea el nuevo usuario <`nombre-del-usuario`>.
2. Crea un grupo para el nuevo usuario - Con el mismo nombre del usuario <`nombre-del-usuario`>.
3. Asigna al nuevo usuario dentro de su grupo.
4. Crea el directorio `/home/<nombre-del-usuario>`.
5. Crea la estructura de directorios de la carpeta home, copiando los archivos del directorio `/etc/skel`.
6. Nos solicita la contraseña para el <`nombre-del-usuario`>.
7. Nos pide que repitamos la contraseña para asegurarnos que la hemos escrito bien.
8. Abre un asistente para completar los datos del nuevo usuario. (Este paso es opcional, podemos dejar todo en blanco).
9. Nos pregunta si la informaición que pusimos es correcta, en el caso que contestemos que si el asitente finaliza y nuestro usuario ya estará creado.

### Agregar permisos administrativos al nuevo usuario 
Necesario para que este usuario pueda crear, leer o modificar archivos de configuración o realizar tareas administrativas como actualizaciones de paquetes o ejecución de servicios, entre otras cosas.

```sh
sudo usermod -aG sudo nombre-del-usuario
```

## Instalar Servidor SSH
SSH o **S**ecure **Sh**ell es un protocolo de comunicaciones seguras para conectar de forma remota dos sistemas operativos para que podamos controlar mediante consola de comandos un equipo host desde un equipo cliente.
Lo más importante de `SSH` es que **es capaz de encriptar la sesión de conexión**, cosa que no es posible con FTP o Telnet, protocolos mucho más inseguros y ya poco utilizados.

```sh
sudo apt install -y openssh-server
```

## Configuración del firewall
El firewall que vamos a configurar es el que viene preinstalado en la distribución el cual es `ufw`, **U**ncomplicated **F**ire**w**all.

Podemos checkear si esta activado o no con el siguiente comando:

```sh
sudo ufw status
Status: inactive
``` 

Si el Firewall esta inactivo, lo podemos habilitar con el siguiente comando:


```sh
sudo ufw enable
Firewall is active anda enabled on system startup
```

Una vez que nos aseguramos que el firewall es activo, podemos ver la lista de aplicaciones disponibles que reconoce con el siguiente comando:

```sh
sudo ufw app list
Available applications:
  OpenSSH
```

Para permitir que `OpenSSH` a través del firewall usamos el comando:

```sh
sudo ufw allow OpenSSH
Rule added
Rule added (v6)
```

Podemos verificar que la aplicación `OpenSSH` esté permitida con el siguiente comando:

```sh
sudo ufw status
Status: active

To              Action        From
--              ------        ----
OpenSSH         ALLOW         Anywhere
OpenSSH (v6)    ALLOW         Anywhere

```

> Ahora en la columna From nos dice que acepta conexiones desde cualquier dirección pero podemos restrigir esto con direcciones específicas o con rangos de direcciones.

## Referencias

- [Recomendaciones generales luego de instalar linux][1].
- [Configurar SSH para usar autenticacion de dos factores][2].
- [Generar llaves SSH en Windows 10][3].


[1]: https://wiki.archlinux.org/index.php/Users_and_groups_(Espa%C3%B1ol)#Administraci%C3%B3n_de_usuarios
[2]: https://ubuntu.com/tutorials/configure-ssh-2fa#1-overview
[3]: https://ubuntu.com/tutorials/ssh-keygen-on-windows#1-overview
