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
The `org.openmodelica.BaseApp` contains the main dependencies for OpenModelica (right now a minimum set, not all).

To build it and install it for the current user:
```bash
$ flatpak-builder --user --install app org.openmodelica.BaseApp.yml
```

To build it and install it for all users:
```bash
$ sudo flatpak-builder --install app org.openmodelica.BaseApp.yml
```

> It might be needed to add `--force-clean` if you need to execute it twice for some reason.

## Omedit
It contains everything needed to run OMEdit. It depends on BaseApp. 

To build it and install it for the current user:
```bash
$ flatpak-builder --user --install app org.openmodelica.OMEdit.yml
```

To build it and install it for all the users:
```bash
$ sudo flatpak-builder --install app sci.openmodelica.Omedit.yml
```
## Bundles
It is possible to store both packages in single files once compiled. If we have installed both packages for the current user, we can do:
```bash
$ flatpak build-bundle ~/.local/share/flatpak/repo BaseApp.flatpak org.openmodelica.BaseApp
```
and:
```bash
$ flatpak build-bundle ~/.local/share/flatpak/repo OMEdit.flatpak org.openmodelica.OMEdit
```

This will create the following couple of files. I have created the two following files (no warranty about them; I am also a newbie):

 - [BaseApp.flatpak](https://mega.nz/#!ENE1XaBD!xRrBsMxsm8011ISZ5iZzi7LhIPgwYnDwmavnPSYI9-g): 33Mb
 - [OMEdit.flatpak](https://mega.nz/#!cMdx2YZY!Raw4KsWpt3QWu-GELm9S6j6BfkmFb8Fu8sBSkhSEYj8): 452Mb

Installing from these files doesn't require to compile.

### Installing from bundle files (To be checked)
If you have the bundle files, you can install from them by just doing:
```bash
$ flatpak install --user BaseApp.flatpak
$ flatpak install --user OMEdit.flatpak
```

## TODO

- [ ] To update the openjdk dependency.
- [ ] To include more icons.
- [ ] To include it in flathub.
