# Installing and configuring oh-my-push on Windows

For best results use the [Windows Terminal](https://www.microsoft.com/store/productId/9N0DX20HK701).

Official [oh-my-push]("https://ohmyposh.dev/docs/installation/windows") documentation

## Installation

First Install the module for Windows PowerShell:

```shell
winget install oh-my-posh
```
or
```shell
Set-ExecutionPolicy Bypass -Scope Process -Force; Invoke-Expression ((New-Object System.Net.WebClient).DownloadString('https://ohmyposh.dev/install.ps1'))
```

Now oh-my-posh binary should be installed here `C:\Users\%UserName%\AppData\Local\Programs\oh-my-posh\bin\oh-my-posh.exe`

If it's not added automatically to your PATH, just add it manually and reload your terminal. (Computer Restart may be required)

Themes should also be installed here `C:\Users\%UserName%\AppData\Local\oh-my-posh\themes`

If it's not you can try this command to get them:

```shell
Get-PoshThemes
```

or Download the theme folder from the official [Github](https://github.com/jandedobbeleer/oh-my-posh) page.

## Apply Oh-my-posh to your shell

Open your shell profile:

```shell
code $PROFILE
```

paste this default config:

```shell
Import-Module oh-my-posh
oh-my-posh init pwsh --config C:\Users\Utilisateur\AppData\Local\oh-my-posh\themes/agnoster.omp.json | Invoke-Expression
```

You can change your theme by changing theme name and reloading your PROFILE with `. $PROFILE`

Available themes preview can be found [here](https://ohmyposh.dev/docs/themes) 

Or you can create you own one and load it from your PROFILE.

## Load Fonts

You may see weird symbol appear in your terminal after installing oh-my-push, it means that you need to import some fonts.

Download: [this fonts](https://github.com/powerline/fonts)

unzip file then, open the font directory on (Admin) powershell and run:

```shell
Set-ExecutionPolicy Bypass; .\install.ps1
```

Config your Terminal to use `Source Code Pro for Powerline` as default font.

## Command Autocomplete

```shell
Install-Module PSReadLine -Force
Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
```





