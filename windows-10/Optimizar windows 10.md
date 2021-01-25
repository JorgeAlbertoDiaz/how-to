# Optimizar Windows 10 para computadoras de bajos recursos

## Ajustar las opciones de rendimiento

Para configurar el equipo para tener un mejor rendimiento debemos hacer lo siguiente:

- Presionar al combinación <kbd>Windows</kbd> + <kbd>PAUSA</kbd> para abrir la ventana ***Acerca de*** de Windows donde nos muestra las especificaciones de hardware de nuestro sistema.
- Buscar la opción ***Configuración Avanzada del sistema***, y se nos abrirá la ventana ***Propiedades del sistema***.
- En la pestaña que dice ***Opciones avanzadas***, buscar la sección que dice ***Rendimiento*** debemos presionar el botón ***Configuración*** y se nos abrirá la ventana ***Opciones de rendimiento***.
- Dentro de la Pestaña que dice ***Efectos visuales***, debemos seleccionamos la opción ***Personalizar*** y desmarcamos todas las opciones con excepción de ***Mostrar vistas en miniatura en lugar de iconos*** y ***Suavizar bordes para las fuentes de pantalla*** luego presionamos ***Aceptar***.
- Ahora nos vamos a la pestaña que dice ***Opciones avanzadas*** y la sección que dice ***Memoria virtual*** presionamos ***Cambiar*** para abrir la ventana ***Memoria virtual***.
- Desactivamos la opcion ***Administrar automáticamente el tamaño del archivo de paginación para todas las unidades***.
- Nos aseguramos que la unidad ***C:*** este seleccionada y seleccionamos la opción ***Tamaño personalizado***.
- En el campo ***Tamaño incial (MB)*** debemos poner el valor que resulta de sumar: *el tamaño de nuestra ram por mil + la mita de su tamaño por mil*, ejemplo en un equipo que tiene 2GB de Ram sería "*2000 + 1000 = 3000*", en este caso debemos poner ***3000***.
- En el campo ***Tamaño máximo (MB)*** debemos poner el doble del valor calculado en el paso anterior.
- Presionamos ***Aceptar*** y reiniciamos el sistema para que los cambios tomen efecto.

## Mejorar velocidad de arranque de Windows.

- Presionamos la combinación de teclas <kbd>Windows</kbd> + <kbd>R</kbd>, se nos abrirá una ventana que dice ***Ejecutar*** y escribimos ***msconfig*** y se nos abrirá la ventana de ***Configuración del sistema***.
- Nos vamos a la pestaña que dice ***Arranque***, y hacemos click en el botón ***Opciones avanzadas*** y se nos abrirá la ventana ***Opciones avanzadas de arranque***.
- Habilitamos la opción ***Número de procesadores*** y seleccionamos el número máximo disponible.
- Habilitamos la opción ***Cantidad máxima de memoria*** y se autocompletará con toda la Ram que tenemos disponible.
- Presionamos el botón ***Aceptar*** para aplicar los cambios y volver a la ventana anterior.
- En el valor de ***Tiempo de espera*** cambiamos de **30** segundos a **5** segundos.
- Presionamos el botón de ***Aceptar*** y reiniciamos la PC para que se apliquen los cambios.

## Optimizamos el disco principal

- Presionamos la combinación de teclas <kbd>Windows</kbd> + <kbd>E</kbd> para abrir el explorador de archivos.
- Seleccionamos ***Este equipo***, hacemos un click derecho al ***Disco Local (C:)*** y seleccionamos ***propiedades***, se nos abrirá la ventana ***Propiedades: Disco Local (C:)***.
- Desactivamos la opción ***Permitir que los archivos de esta unidad tengan el contenido indizado además de las propiedades de los archivos y presionamos el botón ***Aplicar***, se nos abrirá una ventana llamada ***Confirmar cambios de atributos***, con la opción ***Aplicar cambios a la unidad C:\ y a todas la subcarpetas y archivos*** presionamos el botón ***Aceptar***.
- Primero se abrirá una ventana donde nos pide que elevemos los permisos de administrador ponemos que si.
- Nos dará un error con algunos archivos, debemos elegir la opción ***omitir todos***.
- Esperamos que se modifiquen las propiedades de los archivos. El proceso puede tardar 10 minutos o más.

## Desactivar servicios de windows

- Presionamos la combinación de teclas <kbd>Windows</kbd> + <kbd>R</kbd>, se nos abrirá una ventana que dice ***Ejecutar*** y escribimos ***services.msc*** y se nos abrirá la ventana de ***Servicios***.
- Desactivamos los servicios que no vamos a usar. 

	- Windows Search.
	- Windows Update. (Deberemos habilitarlo cuando tengamos que actualizar el sistema).
	- Servicio orquestador de actualizaciones.


	- Administrador de mapas descargados.
	- Captura de SNMP.
	- Detección de hardware shell.
	- Dispositivo de Host UPnP.
	- Host del sistema de diagnóstico.
	- Servicio de transferencia inteligente en 2° plano.
	- Servicio de uso compartido del Reproductor de Windows Media.
	- SysMain (antes conocido Superfetch).
	- Telefonía.
	

> Para desactivar un servicio debemos hacer doble click sobre el que deseamos desactivar, presionamos el botón ***Detener*** si es que estuviera ejecutándose y luego seleccionamos la opción ***Deshabilitado***. Finalmente presionamos ***Aceptar***.

## Otras Optimizaciones
### Escritorio

- Quitar iconos del escritorio, click derecho en el escritorio > ***ver*** > ***Mostrar iconos del escritorio***.

### Barra de Tareas

- Quitar el cuadro búsqueda de la barra de tareas, para ello tenemos que hacer un click derecho sobre la barra de tareas, posicionamos el cursor sobre el menu ***Búsqueda*** y seleccionamos ***Oculto***.

- Para quitar el botón de cortana de la barra, debemos hacer un click derecho sobre la barra de tareas y desactivar la opción ***Mostrar botón de cortana***.

### Menú Inicio

- Desinstalar o desanclar todas las aplicaciones que nos aparecen dentro del menú inicio en el panel de la derecha, el objetivo es que no aparezcan ahi.
- Redimensionar el tamaño del menú inicio todo lo posible.

## Optimizar el almacenamiento.

- Abrimos ***Configuración*** , seleccionamos ***Sistema*** y por últiomo ***Almacenamiento***.
- Activamos ***Sensor de Almacenamiento*** y nos vamos a ***configuración del sensor de almacenamiento***.
- Nos dirigimos al final y presionamos ***Limpiar ahora*** y esperamos a que termine.
- Una vez que el paso anterior finalice volvemos a ***Almacenamiento***, seleccionamos la opción ***Optimizar unidades***.

## Impedir que las aplicaciones se ejecuten en segundo plano

- Abrimos ***Configuración*** , seleccionamos ***Sistema*** y por últiomo ***Almacenamiento***.
- Vamos a ***Privacidad*** y seleccionamos ***Aplicaciones en segundo plano***, deshabilitamos la opción para que las aplicaciones puedan ejecutarse en segundo plano.

## Eliminar archivos temporales 

- Presionamos la combinación de teclas <kbd>Windows</kbd> + <kbd>R</kbd>, se nos abrirá una ventana que dice ***Ejecutar***.
- Escribiremos***temp*** y se nos abrirá la ventana del explorador de la carpeta ***temp*** del sistema, ahora seleccionamos todo y lo borramos.
- Volvemos a abrir la ventana ***Ejecutar*** pero ahora escribiremos **%temp%*** y de nuevo seleccionaremos todo y lo borraremos.

## Eliminar eventos

- Abrimos el ***Menu Inicio*** y escribiremos ***visor de eventos***, una vez abierta la ventana buscamos la vista de árbol de la izquierd la entrada ***Registros de Windows*** tenemos que desplegar su contenido y hacemos un click derecho sobre la entrada ***Aplicación*** y seleccionamos ***Vaciar registro...***, ahora seleccionaremos ***Borrar***.
- Repetimos el paso anterior con todas las opciones excepto con la entrada ***Seguridad***.
