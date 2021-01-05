# Integrar CMDer con Windows Terminal

Para poder integrar CMDer a Windows Terminal debemos:

**Paso 1.** Abrir Windows Terminal
**Paso 2.** Abrir la configuración de Windows terminal con la combinación de teclas <kbd>Ctrl</kbd> + <kbd>,</kbd>.

<details>
  <summary>Nos mostrará algo parecido a lo siguiente: </summary>
  
```
"defaultProfile": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
  
  // A profile specifies a command to execute paired with information about how it should look and feel.
  // Each one of them will appear in the 'New Tab' dropdown,
  // and can be invoked from the commandline with `wt.exe -p xxx`
  // To learn more about profiles, visit https://aka.ms/terminal-profile-settings
  "profiles": {
    "defaults": {
      // Put settings here that you want to apply to all profiles.
    },
    "list": [
      {
        // Make changes here to the powershell.exe profile.
        "guid": "{61c54bbd-c2c6-5271-96e7-009a87ff44bf}",
        "name": "Windows PowerShell",
        "commandline": "powershell.exe",
        "hidden": false
      },
      {
        // Make changes here to the cmd.exe profile.
        "guid": "{0caa0dad-35be-5f56-a8ff-afceeeaa6101}",
        "name": "Command Prompt",
        "commandline": "cmd.exe",
        "hidden": false
      },
      {
        "guid": "{b453ae62-4e3d-5e58-b989-0a998ec441b8}",
        "name": "Azure Cloud Shell",
        "source": "Windows.Terminal.Azure",
        "hidden": false
      }
    ]
  },
  ```
</details>

**Paso 3.** Generamos un nuevo `guid` para el perfil que vamos a agregar con el siguiente comando dentro de la PowerShell de Windows:

```
PS > New-Guid

Guid
----
7d31e0d-c304-4ff7-8gdf-b0fb613a7410

```

**Paso 4.** Agregamos el perfil a la lista de perfiles que ya existe, poniendo como `guid` el valor que generamos en el punto anterior.

Podemos copiar el siguiente codigo:

```
{
  "guid": "{7d31e0d-c304-4ff7-8gdf-b0fb613a7410}",
  "name": "Cmder",
  "commandline": "cmd.exe /k %CMDER_ROOT%\\vendor\\init.bat",
  "startingDirectory": "%USERPROFILE%\\Documents", 
  "icon": "%CMDER_ROOT%\\icons\\cmder.ico",
  "background": "#053428",
  "padding": "15",
  "fontFace": "Cascadia Code",
  "fontSize": 10,
	"useAcrylic": true, 
	"acrylicOpacity": 0.88,
}
```

**Paso 5.** Por último solo debemos poner el `guid` del perfil que corresponde a CMDer como default:

``` 
"defaultProfile": "{7d31e0d-c304-4ff7-8gdf-b0fb613a7410}",
``` 


## Referencias

- https://medium.com/talpor/windows-terminal-cmder-%EF%B8%8F-573e6890d143.
- https://github.com/cmderdev/cmder/wiki.
- https://docs.microsoft.com/es-es/windows/terminal/customize-settings/global-settings.
- https://docs.microsoft.com/es-ES/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-7.1

