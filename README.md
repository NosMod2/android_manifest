Nitrogen OS Maintenance Release 2 Manifest
====================

Create dirs, and install soft, libs
-----------------------------------

    sudo su
    apt-get update
    apt-get install openjdk-8-jdk
    apt-get install repo git-core gnupg flex bison gperf build-essential zip curl zlib1g-dev gcc-multilib g++-multilib libc6-dev-i386 lib32ncurses5-dev x11proto-core-dev libx11-dev lib32z-dev libgl1-mesa-dev libxml2-utils xsltproc unzip
    exit

Create nitrogen folder
----------------------

    mkdir ~/nosmod
    cd ~/nosmod

GIT config (nickname, e-mail)
-----------------------------

    git config --global user.email "mail@domain.com"
    git config --global user.name "login"

To initialize your local repository use
---------------------------------------

    repo init -u https://github.com/NOSMod/android_manifest.git -b p

Then to sync up:
----------------

    repo sync -c -f -j8 --force-sync --no-clone-bundle --no-tags

Build command is
----------------
    . build/envsetup.sh
    lunch aosp_$device-userdebug
    make otapackage -j8

Official supported Devices
-----------------
