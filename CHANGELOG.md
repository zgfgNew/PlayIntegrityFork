## Custom Fork v10

- Work around Shamiko 1.1 bug causing DenyList app hangs
- Keep killgms script in Scripts-only mode for testing use
- Add missing global props and fix all tags and type props
- Use newer resetprop if possible, falling back to custom function
- Add ROM signature spoofing to Advanced Settings, off by default
- Add granular spoofing Advanced Settings for use with Tricky Store
- Improve migrate and autopif scripts to retain Advanced Settings values
- Improve autopif script to catch Magisk Canary busybox wget regression
- Fix bootloop on some Xiaomi devices

## Custom Fork v9
- Improve migrate script formatting edge cases
- Add migrate script manual option to override all values using fingerprint values
- Add opt-in Scripts-only mode for Android <10
- Add autopif script to allow extracting latest Xiaomi.eu custom.pif.json values
- Add killgms script to allow manual DroidGuard process killing

_[Previous changelogs](https://github.com/osm0sis/PlayIntegrityFork/releases)_
