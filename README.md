CM9 Build Instructions
=======================
```
mkdir cm9
cd cm9
repo init -u git://github.com/CyanogenMod/android.git -b ics
```

Modify your `.repo/local_manifest.xml` as follows:

```xml
<?xml version="1.0" encoding="UTF-8"?>
  <manifest>
    <project name="TeamChopsticks/hercskytools" path="hercskytools" remote="github" revision="ics" />
  </manifest>
```

```
repo sync
vendor/cm/get-prebuilts
```

Auto Apply Patches
==================
This script will remove any topic branches named auto, then apply all patches under topic branch auto.

```
hercskytools/cm9-skyrocket-apply.sh #if not working with the kernel & skyrocket
hercskytools/cm9-skyrocket-3.0-apply.sh #if working with the kernel & skyrocket
hercskytools/cm9-hercules-apply.sh #if working with hercules
```

Build
=====

```
. build/envsetup.sh
breakfast cm_skyrocket-userdebug #if building for skyrocket
breakfast cm_hercules-userdebug #if building for hercules
mka bacon
```
