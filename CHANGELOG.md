## Custom Fork v7
- Fix non-/system ROM spoof injection app replacement
- Add missing XiaomiEUInject-Stub to the default/example replace list
- Improve code, scripts and logging
- Fix ROM spoof injection app replacement when using KernelSU and APatch
- Spoof init.svc.adbd to DroidGuard by default to further hide USB Debugging
- Improve hiding from detection by user apps

## Custom Fork v6
- Improve migration script to be more portable, e.g. for desktop use
- Add custom function to hack global props without increasing the change counter
- Add missing Xiaomi, Realme and SELinux global props
- Add customizable example.app_replace.list file to replace conflicting custom ROM apps
- Improve VERBOSE_LOGS to be any json entry, and dump full Build fields at 100
- Change DroidGuard prop spoof hooking method to Dobby for now

_[Previous changelogs](https://github.com/osm0sis/PlayIntegrityFork/releases)_
