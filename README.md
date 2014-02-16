docker-cyanogenmod
==================

Create a [Docker] based environment to build [CyanogenMod].

This Dockerfile will create a docker container which is based on Ubuntu 12.04.
It will install the "repo" utility and any other build dependencies which are required to compile CyanogenMod.

The main working directory is a shared folder on the host system, so the Docker container will can be removed at any time.

**NOTE:** Remember that CyanogenMod is a huge project. It will consume a large amount of disk space (~80 GB) and it can easily take hours to build.

### How to build

```
git clone https://github.com/stucki/docker-cyanogenmod.git
cd docker-cyanogenmod
./build.sh
```

### How to run

```
cd docker-cyanogenmod
./run.sh
```

The container uses "screen" to run the shell. This means that you will be able to open additional shells using [screen keyboard shortcuts][Screen_Shortcuts].

### How to build CyanogenMod for your device

```
repo init -u git://github.com/CyanogenMod/android.git -b cm-11.0
repo sync
source build/envsetup.sh
breakfast <device codename>   # example: breakfast grouper
brunch <device codename>      # example: brunch grouper
```

### Links

For further information, check the following links:

* [CyanogenMod Building Basics][Cyanogenmod_Building_Basics]
* [Learning to Build CyanogenMod][Learning_to_Build_CM]
* [Build Instructions for Google Nexus 5][CyanogenMod_Build_Nexus5] (example device, search the wiki for other devices)

==================

[Docker]:                      https://www.docker.io/
[CyanogenMod]:                 http://www.cyanogenmod.org/
[Screen_Shortcuts]:            http://www.pixelbeat.org/lkdb/screen.html
[CyanogenMod_Building_Basics]: http://wiki.cyanogenmod.org/w/Doc:_Building_Basics
[Learning_to_Build_CM]:        http://wiki.cyanogenmod.org/w/Development#Learning_To_Build_CM
[CyanogenMod_Build_Nexus5]:    http://wiki.cyanogenmod.org/w/Build_for_hammerhead

