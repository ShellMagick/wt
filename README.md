# ShellMagick Windows Terminal customizations

## Assumptions

This README makes the following assumptions:

- You have a Windows Terminal at your disposal (either installed in your system or have downloaded a portable version)
- You have the environment variable `PROJECT_BASE` set (e.g., `PROJECT_BASE=C:\Projects`)
- You have the environment variable `WT_BASE` set, pointing to your clone of this repository (e.g., as in `WT_BASE=%PROJECT_BASE%\git\shellmagick\wt`)

## How to "relocate" the settings

Officially there is no way to relocate the settings of Windows Terminal, let it be installed or portable version.

However, unofficially, creating an NTFS link works. In case you are using the installed version, you can simply

- navigate to `%LocalAppData%\Packages\Microsoft.WindowsTerminal_8wekyb3d8bbwe`
- delete the directory `LocalState`
- create a link `mklink /D LocalState "%PROJECTS_BASE%\git\shellmagick\wt\LocalState"`

## Contents of this repository

The main contents of this repository is a "default" [`settings.json`](./LocalState/settings.json), which contains default profiles for:

- Windows CMD
- Cygwin
- MinGW
- PowerShell
- _Planned_: WSL2

All profiles have the following additional settings:

- custom, high-quality icons, generated from official SVG files. See the [README of the icons submodule](./icons/README.md) for further details
- leveraging additional color schemes, which have been copied either from https://windowsterminalthemes.dev/ or from https://github.com/wuqs-net/base16-windows-terminal
- having custom-made, example backgrounds set. See the [README of the backgrounds submodule](./backgrounds/README.md) for further details, how these **_example_** backgrounds have been created
    - in case you want to use your own backgrounds, you can simply exchange the submodule to your own, or even delete the submodule in your clone of this repository
    - you have to make sure that the corresponding backgrounds are in the `backgrounds/dst` repository, see the expected filenames in the [`settings.json`](./LocalState/settings.json)

Further customization are inbound.
