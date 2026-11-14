# bitDroid source

bitDroid is LineageOS 24 (Android 17) with its own look, apps and features on top. This repo
holds the manifest that swaps the changed LineageOS repos for the bitDroid versions.

## Build it for your device

You need a LineageOS 24 build setup (see the LineageOS build guide for your device first).

```bash
mkdir -p ~/android/lineage && cd ~/android/lineage
repo init -u https://github.com/LineageOS/android.git -b lineage-24.0 --git-lfs
git clone https://github.com/bitDroidOS/local_manifests .repo/local_manifests
repo sync -c -j8
source build/envsetup.sh
breakfast <your device>      # e.g. frankel, rango
m bacon
```

The ROM zip lands in `out/target/product/<device>/bitDroid-*.zip`.

## Notes

- Sign your builds with your own keys. Builds from other people aren't official bitDroid
  builds; set `LINEAGE_BUILDTYPE=UNOFFICIAL` before building them.
- bitHome, bitKeys, bitMessages, bitDialer, AlexLMP and Hachigram ship as prebuilt apps in
  vendor/lineage.
- Google apps aren't included in the build. Flash a GApps package after the ROM.

## Community

- Community: https://t.me/bitDroidCommunity
- Announcements: https://t.me/bitDroidNews

Made by Alex Desrosier.
