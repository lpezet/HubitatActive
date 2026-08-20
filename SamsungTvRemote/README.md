# Hubitat Samsung TV Remote (2018 Tizen fork)
Unofficial fork of [David Gutheinz's Samsung TV Remote driver](https://github.com/DaveGut/HubitatActive/tree/master/SamsungTvRemote), created and authored by David Gutheinz.  This fork is not published or supported by him — please raise fork issues here, not on his repo or community thread.

Fork changes:
- A poll that returns HTTP 200 without a `device.PowerState` field is treated as powered on, so 2018 Tizen models are no longer reported as off.
- DIAL-based streaming app detection, which needs no SmartThings account.  Two attributes are added:
  - `streamingApp` — the DIAL name of the running app, or `none`
  - `inMovieApp` — `true` while one of the configured apps is running, `false` otherwise

  Three preferences drive it: **Streaming App Polling Interval** (off/1/5/10/30 minutes, default 1), **Movie app DIAL names** (comma separated, default `Netflix,PrimeVideo,Hulu,Disney`), and **DIAL Port** (`8080` for legacy models, `8001` for Tizen).  Each poll asks the TV about each named app and takes the one reporting `<state>running</state>`; events fire only when a value actually changes, so `inMovieApp` stays quiet while you switch between two movie apps.  The **dialPoll** command runs a poll on demand — use it with debug logging on to confirm your DIAL names and port.
- The driver namespace is `lpezet` rather than `davegut`, so it installs alongside the original instead of taking over its driver slot.  A device already running the original **will not switch by itself**: open the device, set **Type** to "Samsung TV Remote" under the `lpezet` namespace, hit Save Device, then **Save Preferences**.  Attributes and device history survive the switch; check that the TV IP and any SmartThings settings carried over.
- `version()` reports `2.3.9.2`, matching `packageManifest.json`, so the version in the device label matches the HPM package version.

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