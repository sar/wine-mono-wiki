# Install
With Proton version 5.13, you can use a custom version of wine-mono instead of dotnet.

You can install:
1. [with protontricks](#with-protontricks); or
2. [manually](#manually)

But with both options you must [download](https://github.com/redmcg/wine-mono/releases/download/wine-mono-5.1.1_ED/wine-mono-5.1.1_ED-x86.msi) the install msi. You should also start with a clean prefix (by deleting or moving the existing one).

## with protontricks
There's two steps:
1. click 'Play' and let the game launch and fail;
2. `protontricks -c 'msiexec /i _<path_to_msi>_/wine-mono-5.1.1_ED-x86.msi' 359320`

## manually
There's two steps:
1. Set your wine prefix (example: `export WINEPREFIX=_<path_to_steam>_/steamapps/compatdata/359320/pfx`); and
2. Run msiexec (example: `_<path_to_steam>_/steamapps/common/Proton\ 5.13/dist/bin/wine64 msiexec /i _<path_to_msi>_/wine-mono-5.1.1_ED-x86.msi`

# Known Issues
The launcher does not close properly; the window will close but it will keep running in the background. You need to press 'Close' in Steam to force it to close.