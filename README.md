# SNES VC Booster

# About

Simple customization on original project https://github.com/SuperrSonic/snes-vc-booster to allow patch directly from emunand channel root path. The snes virtual console game need to be installed on Emunand before running this.

More info on the application could be found on original repository: https://github.com/SuperrSonic/snes-vc-booster

# How to run

1) Backup your emunand channel root path first (in case something goes wrong).

2) Open powershell and change the current work directory to emunand root path.

3) Set the application executable path variable to point to the location of `sns_boost.exe` (specify absolute path):
```
$executablePath="<absolute-path>\sns_boost.exe"
```

4) Run the following command (this will apply only a subset of patches available - customize patches if needed):
```
Get-ChildItem -Path .\ -Filter *.app -Recurse -File -Name| ForEach-Object {
     & $executablePath -i "$_" --volume --no-dark --no-cc --gc-remap --verbose
}
