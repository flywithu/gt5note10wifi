# Manifest for building LineageOS 18.1 for s5neolte

`s5neolte` is the codename for the Samsung Galaxy SM-P550

Some extremely basic instructions:
- Make a new directory for LineageOS sources and enter it:
```
mkdir lineage-18.1
cd lineage-18.1
```

- Initialize repo in this directory with the LineageOS android.git repository:
```
repo init -u https://github.com/LineageOS/android.git -b lineage-18.1 --git-lfs
```

- Clone this repository to .repo/local_manifests for roomservice.xml containing the repositories needed to build for these devices:
```
git clone https://github.com/flywithu/gt5note10wifi -b lineage-18.1 .repo/local_manifests
```

- Sync all of the repositories in manifests (including LineageOS manifests):
```
repo sync --force-sync --no-tags --no-clone-bundle -c
```

- Finally, build as you like. For example, for a recovery-installable package:
```
. build/envsetup.sh
lunch lineage_gt510wifi-userdebug
mka otapackage
```
