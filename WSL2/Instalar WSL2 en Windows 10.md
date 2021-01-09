# Instalar WSL 2 en Windows 10

WSL (**W**indows **S**ubsystem for **W**indows) te permite ejecutar un entorno **GNU/Linux** directamente sobre Windows sin modificarlo y sin la sobrecarga de las máquinas virtual tradicional o una configuración de arranque dual.

## Instalación Simplificada
El proceso de instalación para WSL para Linux ha sido significativamente mejorado en las últimas versiones de Windows 10 Insiders, ya que se reemplazaron todos los pasos manuales por un único compando.

### Requisitos: 
- Windows 10: OS build 20262 o superior.
- Pertenecer al programa de [Windows Insiders][6].
- Una línea de comandos de Powershell con privilegios de Administrador.

### Pasos:

**• Paso 1:** Abrir la Powershell con privilegios de Administrador.

**• Paso 2:** Ingresar el comando:

```PowerShell
wsl.exe --install
```

El comando `--install`realiza las siguientes operaciones:

- Habilita las características de Windows de ***Virtual Machine Platform*** y ***Windows Subsystem for Linux***.
- Descarga e instala la última versión del Kernel de Linux.
- Establece a WSL 2 como predeterminado.
- Descarga e installa una distribución de Linux (se requiere reiniciar).

> Por defecto, la distribución Linux que se instalará será Ubuntu, esto se puede modificar con el parámetro `--install -d <Nombre de la distrubución>`.

**• Paso 3:** Reiniciar tu PC.

## Instalación Manual
Si no quieres pertenecer al grupo de Insiders de Windows 10, entonces tienen que hacer la instalación manualmente.


### Requisitos.
- Para sistemas X64: Version 1903 o superior, con la Build 18362 o superior.
- Una línea de comandos de Powershell con privilegios de Administrador.

#### **• Paso 1:** Activar características de Windows.

##### Subsistema de Windows para Linux.

Para que podamos correr cualquier distribución de linux, lo primero que debemos hacer es abrir una instacia de **PowerShell** como **Administrador** y ejecutar el siguiente comando:

```PowerShell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```

> Despuúes de hacer este paso ya es posible ejecutar cualquier distribución de Linux (que esté en la microsoft store), pero con la **versión 1 de WSL**, es recomendable hacer los siguientes pasos para poder ejecutarla sobre la **versión 2 de WSL**.

##### Plataforma de Máquina Virtual
Antes de instalar WSL 2 debes habilitar esta característica opcional de Windows 10.
Sobre la PowerShell de Windows ejecuta el siguiente comando:

```PowerShell
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
#### **• Paso 2:** Reinica tu computadora.
Es necesario para que los cambios tomen efecto y puedas seguir con el proceso.

#### **• Paso 3:** Instalar el paquete de actualizaciones del **Kernel de Linux**.

1. Descarga el (WSL2 Acutalización de paquetes para máquinas x64)[https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi].
2. Instala el paquete que descargaste en el punto anterior.

#### **• Paso 4:** Configura WSL2  como la versión predeterminada.

```PowerShell
wsl --set-default-version 2
```

#### **• Paso 5:** Instala la distribución de Linux que desees desde la Tienda de Microsoft.

**1.** Abre la Microsoft Store y selecciona tu distribución favorita.

![windows store](https://docs.microsoft.com/en-us/windows/wsl/media/store.png)

**2.** Desde la página de la distribución presionamos ***Obtener*** y esperamos que se instale.

**3.** La primera vez que iniciemos la apliación nos pedirá que creemos un usuario y su contraseña, una vez hecho esto ya tendremos todo listo para usar.

## Referencias

- [David Bombal - WSL 2: Getting started (Youtube)][1]
- [Qué es WSL][2]
- [Documentación de WSL 2][3]
- [Anuncios sobre WSL 2][4]
- [Comparando WSL 2 con respecto a WSL 1][5]
- [Blog: Linea de Comandos de Windows]: [7]

[1]: https://www.youtube.com/watch?v=_fntjriRe48
[2]: https://docs.microsoft.com/en-us/windows/wsl/about
[3]: https://docs.microsoft.com/en-us/windows/wsl/
[4]: https://devblogs.microsoft.com/commandline/announcing-wsl-2/
[5]: https://docs.microsoft.com/en-us/windows/wsl/compare-versions
[6]: https://insider.windows.com/getting-started
[7]: https://devblogs.microsoft.com/commandline/
