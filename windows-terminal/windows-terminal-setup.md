# Windows Terminal Notes
Configuration notes for [windows terminal](https://www.microsoft.com/en-us/p/windows-terminal-preview/9n0dx20hk701?activetab=pivot:overviewtab).

## Hardlink Config
Create a hardlink to the application configuration allowing the config to be placed under version control, example using cmd `mklink /H %LocalAppData%\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe\LocalState\settings.json C:\repos\notes\windows-terminal\settings.json`

## Colour theme
Create snazzy colour theme based off [hyper-snazzy](https://github.com/sindresorhus/hyper-snazzy). 
Go to settings via the down array in the title bar. 
In the `schemes` array add a new item,  
```json
{
    "name": "snazzy",
    "foreground": "#eff0eb",
    "background": "#282a36",
    "black": "#282a36",
    "red": "#ff5c57",
    "green": "#5af78e",
    "yellow": "#f3f99d",
    "blue": "#57c7ff",
    "purple": "#ff6ac1",
    "cyan": "#9aedfe",
    "white": "#f1f1f0",
    "brightBlack": "#686868",
    "brightRed": "#ff5c57",
    "brightGreen": "#5af78e",
    "brightYellow": "#f3f99d",
    "brightBlue": "#57c7ff",
    "brightPurple": "#ff6ac1",
    "brightCyan": "#9aedfe",
    "brightWhite": "#eff0eb"
}
```  
Now set WSL profile to use this by adding this line to the profile `"colorScheme": "snazzy"`. Powershell can also use this by repeating the above for the powershell entry.

## Font
Cascadia code PL front from microsoft [cascadia-font](https://github.com/microsoft/cascadia-code).  
Set WSL to use this font by adding this line to the profile `"fontFace": "Cascadia Code PL"`.

