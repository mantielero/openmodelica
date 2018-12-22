# OpenModelica

## BaseApp
The `sci.openmodelica.BaseApp` contains the main dependencies for OpenModelica (right now a minimum set, not all).

To build it and install it:
```bash
flatpak-builder --install app sci.openmodelica.BaseApp.json
```

## Omedit
It contains everything needed to run OMEdit. It depends on BaseApp.


To build it and install it:
```bash
flatpak-builder --install app sci.openmodelica.Omedit.json
```

TODO: right now Omedit won't compile. The reason is that it depends on a huge file which contains the libraries and that I cannot upload to github. The solution is to create small packages per library.




