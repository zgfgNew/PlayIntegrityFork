## Custom Fork v6
- Improve migration script to be more portable, e.g. for desktop use
- Add custom function to hack global props without increasing the change counter
- Add missing Xiaomi, Realme and SELinux global props
- Add customizable example.app_replace.list file to replace conflicting custom ROM apps
- Improve VERBOSE_LOGS to be any json entry, and dump full Build fields at 100
- Change DroidGuard prop spoof hooking method to Dobby for now

## Custom Fork v5
- Allow spoofing literally any system property, supporting * lead wildcard to match multiple
- Remove all backwards compat cruft and deprecated entries
- Add log levels with VERBOSE_LOGS last json entry of 0, 1, 2, 3 or 100
- Spoof sys.usb.state to DroidGuard by default to hide USB Debugging
- Update example json for properties
- Add migration script to automatically upgrade old custom.pif.json during install/update (may also be run manually)

_[Previous changelogs](https://github.com/osm0sis/PlayIntegrityFork/releases)_
