## Custom Fork v10

- Work around Shamiko 1.1 bug causing DenyList app hangs
- Keep killgms script in Scripts-only mode for testing use
- Add missing global props and fix all tags and type props
- Use newer resetprop if possible, falling back to custom function
- Add ROM signature spoofing to Advanced Settings, off by default
- Add granular spoofing Advanced Settings for use with Tricky Store
- Improve migrate and autopif scripts to retain Advanced Settings values
- Improve autopif script to catch Magisk Canary busybox wget regression

## Custom Fork v9
- Improve migrate script handling of some formatting edge cases
- Add migrate script manual option to override all values using the fingerprint values
- Add an opt-in scripts-only-mode for Android <10 ROMs
- Add autopif script to allow extracting the latest Xiaomi.eu custom.pif.json values
- Add killgms script to allow manual DroidGuard process killing

_[Previous changelogs](https://github.com/osm0sis/PlayIntegrityFork/releases)_
