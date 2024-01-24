# Play Integrity Fork
*PIF forked to be more futureproof and develop more methodically*

[![GitHub release (latest by date)](https://img.shields.io/github/v/release/osm0sis/PlayIntegrityFork?label=Release&color=blue&style=flat)](https://github.com/osm0sis/PlayIntegrityFork/releases/latest)
[![GitHub Release Date](https://img.shields.io/github/release-date/osm0sis/PlayIntegrityFork?label=Release%20Date&color=brightgreen&style=flat)](https://github.com/osm0sis/PlayIntegrityFork/releases)
[![GitHub Releases](https://img.shields.io/github/downloads/osm0sis/PlayIntegrityFork/latest/total?label=Downloads%20%28Latest%20Release%29&color=blue&style=flat)](https://github.com/osm0sis/PlayIntegrityFork/releases/latest)
[![GitHub All Releases](https://img.shields.io/github/downloads/osm0sis/PlayIntegrityFork/total?label=Total%20Downloads%20%28All%20Releases%29&color=brightgreen&style=flat)](https://github.com/osm0sis/PlayIntegrityFork/releases)

A Zygisk module which fixes "ctsProfileMatch" (SafetyNet) and "MEETS_DEVICE_INTEGRITY" (Play Integrity).

To use this module you must have one of the following:

- [Magisk](https://github.com/topjohnwu/Magisk) with Zygisk (and, if not also using Shamiko, Enforce DenyList) enabled
- [KernelSU](https://github.com/tiann/KernelSU) with [ZygiskNext](https://github.com/Dr-TSNG/ZygiskNext) module installed
- [APatch](https://github.com/bmax121/APatch) with [ZygiskNext MOD](https://github.com/Yervant7/ZygiskNext) module installed

## About module

It injects a classes.dex file to modify a few fields in the android.os.Build class. Also, it creates a hook in the native code to modify system properties. These are spoofed only to Google Play Services' DroidGuard (SafetyNet/Play Integrity) service.

The purpose of the module is to avoid hardware attestation.

## About 'custom.pif.json' file

You can fill out the included template [example.pif.json](https://raw.githubusercontent.com/osm0sis/PlayIntegrityFork/main/module/example.pif.json) from the module directory then rename it to custom.pif.json to spoof custom values to the GMS unstable process. It will be used instead of any included pif.json (none included currently).

As a general rule you can't use values from recent devices due to them only being allowed with full hardware backed attestation.

Older formatted custom.pif.json files from cross-forks and previous releases will be automatically migrated to the latest format.

A migration may also be performed manually with `sh migrate.sh` and custom.pif.json in the same directory, or from a file explorer app that supports script execution.

<details>
<summary>Resources</summary>

- [How-To Guide - Info to help find build.prop files, then create and use a custom.pif.json](https://xdaforums.com/t/module-play-integrity-fix-safetynet-fix.4607985/post-89189572)
- [gen_pif_custom.sh - Script to generate a custom.pif.json from device dump build.prop files](https://xdaforums.com/t/tools-zips-scripts-osm0sis-odds-and-ends-multiple-devices-platforms.2239421/post-89173470)
- [UI Workflow Guide - Build, edit and test custom.pif.json using PixelFlasher on PC](https://xdaforums.com/t/module-play-integrity-fix-safetynet-fix.4607985/post-89189970)

</details>

## About 'custom.app_replace.list' file

You can customize the included default [example.app_replace.list](https://raw.githubusercontent.com/osm0sis/PlayIntegrityFork/main/module/example.app_replace.list) from the module directory then rename it to custom.app_replace.list to systemlessly replace any additional conflicting custom ROM spoof injection app paths to disable them.

## Troubleshooting

### Failing BASIC verdict

If you are failing basicIntegrity (SafetyNet) or MEETS_BASIC_INTEGRITY (Play Integrity) something is wrong in your setup. Recommended steps in order to find the problem:

- Disable all modules except this one
- Try a different (ideally known working) custom.pif.json

Some modules which modify system can trigger DroidGuard detection, never hook GMS processes.

### Failing DEVICE verdict (on KernelSU/APatch)

- Disable ZygiskNext
- Reboot
- Enable ZygiskNext

### Play Protect/Store Certification and Google Wallet Tap To Pay Setup Security Requirements

Follow these steps:

- Reflash the module in your root manager app
- Clear Google Wallet cache (if you have it)
- Clear Google Play Store cache and data
- Clear Google Play Services (com.google.android.gms) cache and data (Optionally skip clearing data and wait some time, ~24h, for it to resolve on its own)
- Reboot

Note: Clearing Google Play Services app ***data*** will then require you to reset any WearOS devices paired to your device.

### Read module logs

You can read module logs using one of these commands directly after boot:

`adb shell "logcat | grep 'PIF/'"` or `su -c "logcat | grep 'PIF/'"`

Add a "VERBOSE_LOGS" entry with a value of "0", "1", "2", "3" or "100" to your custom.pif.json to enable higher logging levels; "100" will dump all Build fields, and all the system properties that DroidGuard is checking.

## Can this module pass MEETS_STRONG_INTEGRITY?

No.

## About Play Integrity, SafetyNet is deprecated

You can read more
here: [Play Integrity API Info - XDA Forums](https://xdaforums.com/t/info-play-integrity-api-replacement-for-safetynet.4479337/)

## Credits

Module scripts were adapted from those of kdrag0n/Displax's Universal SafetyNet Fix (USNF) module, please see the commit history of [Displax's USNF Fork](https://github.com/Displax/safetynet-fix/tree/dev/magisk) for proper attribution.
