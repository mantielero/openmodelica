# OpenModelica
## Prerrequisites
The flathub remote should be added first:
```
flatpak remote-add flathub https://flathub.org/repo/flathub.flatpakrepo
```

and then install the following for x86_64 architecture:

```
flatpak install flathub org.kde.Sdk/x86_64/5.11 
flatpak install flathub org.freedesktop.Sdk.Extension.openjdk9/x86_64/1.6
flatpak install flathub org.freedesktop.Sdk.Extension.gfortran-62/x86_64/1.6
```

## BaseApp
The `sci.openmodelica.BaseApp` contains the main dependencies for OpenModelica (right now a minimum set, not all).

To build it and install it for the current user:
```bash
$ flatpak-builder --user --install app sci.openmodelica.BaseApp.yml
```

To build it and install it for all users:
```bash
$ sudo flatpak-builder --install app sci.openmodelica.BaseApp.yml
```

> It might be needed to add `--force-clean` if you need to execute it twice for some reason.

## Omedit
It contains everything needed to run OMEdit. It depends on BaseApp. 

To build it and install it for the current user:
```bash
$ flatpak-builder --user --install app sci.openmodelica.Omedit.yml
```

To build it and install it for all the users:
```bash
$ sudo flatpak-builder --install app sci.openmodelica.Omedit.yml
```

## TODO

- [ ] To update the openjdk dependency.
- [ ] To include more icons.
- [ ] To include it in flathub.
