## Custom Fork v8
- Rename VERBOSE_LOGS to verboseLogs to better differentiate Advanced Settings from Build Fields or System Properties
- Improve replace list to also allow file paths replacing/hiding systemlessly
- Improve migration script and add optional verboseLogs entry to output
- Improve replace list to automatically comment out any overlay APK config.xml entries systemlessly
- Update default/example app replace list for more ROM spoof injection methods
- Fix retaining disabled ROM apps through module updates in some scenarios

## Custom Fork v7
- Fix non-/system ROM spoof injection app replacement
- Add missing XiaomiEUInject-Stub to the default/example replace list
- Improve code, scripts and logging
- Fix ROM spoof injection app replacement when using KernelSU and APatch
- Spoof init.svc.adbd to DroidGuard by default to further hide USB Debugging
- Improve hiding from detection by user apps

_[Previous changelogs](https://github.com/osm0sis/PlayIntegrityFork/releases)_
