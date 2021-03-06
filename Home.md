# Default wine-mono
The default version of wine-mono in Proton version 6.3-1 (wine-mono version 6.1.1) will run the Elite Dangerous Launcher; however, you will need to create the 'evidencehere' directory manually. The following command (using protontricks) should work for most set-ups:

`protontricks -c 'mkdir ../../compatdata/359320/pfx/drive_c/users/steamuser/Local\ Settings/Application\ Data/Elite\ Dangerous\ Launcher_evidencehere' 359320`

Without creating this directory you will see the following error:

![](https://user-images.githubusercontent.com/8346438/112704443-b7168880-8eee-11eb-8bc3-d32c7e7c964c.png)

You may also see the following exception:

![image](https://user-images.githubusercontent.com/8346438/113377991-956f4280-93c1-11eb-857b-3cd1e2f08065.png)

But this can be safely ignored (by clicking 'Continue').

You can alternatively use a custom version of wine-mono (which no longer needs this directory).

# Install Custom Version
You install the custom version of wine-mono either:
1. [with protontricks](#with-protontricks); or
2. [manually](#manually)

But you must first download the msi. Either:
- [wine-mono version 6.1.99](https://github.com/madewokherd/wine-mono/suites/2561635479/artifacts/55812061) (this is the latest development version from the official wine-mono repository at the time of writing; specifically commit 90fd1a4. You can check for a more recent version [here](https://github.com/madewokherd/wine-mono/actions). Note that the download is a ZIP file with the MSI in it); or
- [wine-mono version 6.1.1_ED](https://github.com/redmcg/wine-mono/releases/download/wine-mono-6.1.1_ED/wine-mono-6.1.1_ED-x86.msi) (this is an older development version compiled by me with the distingishing version of 6.1.1_ED)

Note that if you were previously using dotnet, you should start with a clean prefix (by deleting or moving the existing one).

## with protontricks
There's four steps:
1. click 'Play' and let the game launch and fail;
2. `protontricks -c 'wine64 uninstaller' 359320`
3. Uninstall any existing version of 'Wine Mono Runtime' (by selecting it and clicking 'Remove')
4. Click 'Install...' and select wine-mono-6.1.1_ED-x86.msi (or wine-mono-6.1.99-x86.msi)

## manually
There's two steps:
1. Set your wine prefix (example: `export WINEPREFIX=_<path_to_steam>_/steamapps/compatdata/359320/pfx`); and
2. Run msiexec (example: `_<path_to_steam>_/steamapps/common/Proton\ 5.13/dist/bin/wine64 msiexec /i _<path_to_msi>_/wine-mono-6.1.1_ED-x86.msi` (or wine-mono-6.1.99-x86.msi)

# Known Issues
## Launcher Closing
The launcher does not always close properly; the window will close but it will keep running in the background. You need to press 'Close' in Steam to force it to close.

## Logging in
**This is fixed in wine-mono-5.1.1.1_ED and later**

You can not currently manually log-in. Clicking the log-in button causes the launcher to crash. To make use of this launcher you need to already be logged in either by:
1. linking your frontier account with your steam account (so log-in is automatic); or
2. logging in using dotnet (and then uninstalling dotnet and installing this... but, you know, if you've already got dotnet working ??\\_(???)_/??)