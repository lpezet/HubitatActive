# Hubitat Samsung TV Remote (2018 Tizen fork)
Unofficial fork of [David Gutheinz's Samsung TV Remote driver](https://github.com/DaveGut/HubitatActive/tree/master/SamsungTvRemote), created and authored by David Gutheinz.  This fork is not published or supported by him — please raise fork issues here, not on his repo or community thread.

Fork change: a poll that returns HTTP 200 without a `device.PowerState` field is treated as powered on, so 2018 Tizen models are no longer reported as off.

This driver provide integration of the Samsung TV Remote Control functions with the Hubitat.  Additionally, it provides an option to connect to the SmartThings Cloud for addition functions and information not otherwise available. 

### Release Notes
https://github.com/DaveGut/HubitatActive/blob/master/SamsungTvRemote/Docs/ReleaseNotes.pdf

### Driver location
https://github.com/lpezet/HubitatActive/edit/master/SamsungTvRemote/SamsungTVRemote.groovy

### Installation:  
https://github.com/lpezet/HubitatActive/blob/master/SamsungTvRemote/Docs/Installation.pdf

### Update from previous version using HPM:
After completing update via HPM, do a SAVE PREFERENCES.  Otherwise there will be a spew of log errors.

### Manual Update:
- Replace existing code with new code and Save
- After completing update, do a SAVE PREFERENCES.  Otherwise there will be a spew of log errors.


### Preference and State Descriptions: 
https://github.com/lpezet/HubitatActive/blob/master/SamsungTvRemote/Docs/Prefs-States.pdf

### Commands data: 
https://github.com/lpezet/HubitatActive/blob/master/SamsungTvRemote/Docs/Commands.pdf

### Note on Button Interface: 
https://github.com/lpezet/HubitatActive/blob/master/SamsungTvRemote/Docs/ButtonInterface.pdf

### Samsung App List (reference only): 
https://github.com/lpezet/HubitatActive/blob/master/SamsungTvRemote/Docs/SamsungAppList.pdf

### Samsung Remote Key List (reference only):
https://github.com/lpezet/HubitatActive/blob/master/SamsungTvRemote/Docs/SamsungKeyList.pdf