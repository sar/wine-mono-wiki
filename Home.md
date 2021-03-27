# Install
With Proton version 5.13, you can use:
* a custom version of wine-mono; or
* the official wine-mono release (6.1 or later)

instead of dotnet.

You can install either of these:
1. [with protontricks](#with-protontricks); or
2. [manually](#manually)

But with both options you must the install msi. Below are links to download the:
1. [custom msi](https://github.com/redmcg/wine-mono/releases/download/wine-mono-5.1.1.2_ED/wine-mono-5.1.1.2_ED-x86.msi); or
2. [official msi](https://github.com/madewokherd/wine-mono/releases/download/wine-mono-6.1.0/wine-mono-6.1.0-x86.msi)

Note that the official msi currently requires the manual creation of the 'evidencehere' directory. Otherwise you will get the following error:

![](https://user-images.githubusercontent.com/8346438/112704443-b7168880-8eee-11eb-8bc3-d32c7e7c964c.png)

Note that if you were previously using dotnet, you should start with a clean prefix (by deleting or moving the existing one).

## with protontricks
There's four steps:
1. click 'Play' and let the game launch and fail;
2. `protontricks -c 'wine64 uninstaller' 359320`
3. Uninstall any existing version of 'Wine Mono Runtime' (by selecting it and clicking 'Remove')
4. Click 'Install...' and select wine-mono-5.1.1.2_ED-x86.msi (or wine-mono-6.1.0-x86.msi)

## manually
There's two steps:
1. Set your wine prefix (example: `export WINEPREFIX=_<path_to_steam>_/steamapps/compatdata/359320/pfx`); and
2. Run msiexec (example: `_<path_to_steam>_/steamapps/common/Proton\ 5.13/dist/bin/wine64 msiexec /i _<path_to_msi>_/wine-mono-5.1.1.2_ED-x86.msi` (or wine-mono-6.1.0-x86.msi)

# Known Issues
## Launcher Closing
The launcher does not always close properly; the window will close but it will keep running in the background. You need to press 'Close' in Steam to force it to close.

## Logging in
**This should be fixed in wine-mono-5.1.1.1_ED**

You can not currently manually log-in. Clicking the log-in button causes the launcher to crash. To make use of this launcher you need to already be logged in either by:
1. linking your frontier account with your steam account (so log-in is automatic); or
2. logging in using dotnet (and then uninstalling dotnet and installing this... but, you know, if you've already got dotnet working ¯\\_(ツ)_/¯)