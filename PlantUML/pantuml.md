# PlantUML
PlantUML es un proyecto open source que nos permite escribir rápidamente distintos tipos de diagramas:

- Diagramas de Secuencia
- Diagramas de Casos de uso
- Diagramas de Clases
- Diagramas de Objetos
- Diagramas de Actividades
- Diagramas de Componentes
- Diagramas de Despliegue
- Diagramas de Estados
- Timing diagram

## Dependencias
- Java
- Graphviz

## Instalación
### Windows

1. Descarga e instalar [Java][2].
2. Descargar e instalar [Graphviz][3].
    - Cuando instales Graphviz es recomendable agregarlo a las variables del sistema.
    - Una vez instalado ahora debemos ejecutar el comando `dot -c`.
    - Abrimos `cmd.exe` con la opción **Ejecutar como Administrador** y nos movemos al directorio `C:\Program Files\Graphviz 2.44.1\bin` una vez ahi escribimos el comando `dot -c`.
  
   ![graphviz][5]

## Agregar extensión a Visual Studio Code

[Extensión de PlantUML para VSCode][6].

```
Name: PlantUML
Id: jebbs.plantuml
Description: Rich PlantUML support for Visual Studio Code.
Version: 2.14.1
Publisher: jebbs
VS Marketplace Link: https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml
```


## Referencias

- [Sitio Oficial][1].
- [Descarga Java][2].
- [Descarga Graphviz][3].
- [Instalación de Graphviz][4].
- [Imagen de graphviz][5].

[1]: https://plantuml.com/es/
[2]: https://www.java.com/en/download/
[3]: https://www2.graphviz.org/Packages/stable/windows/10/cmake/Release/x64/graphviz-install-2.44.1-win64.exe
[4]: https://plantuml.com/es/graphviz-dot
[6]: https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml
[5]: https://s.plantuml.com/img/dotc.png
