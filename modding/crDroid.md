# Installing crDroid 7.3 on OnePlus 6T

# Description of OnePlus 6T (fajita)

The OnePlus 6T (codenamed _"fajita"_) is a flagship smartphone from OnePlus.
It was released in November 2018.

| Basic                   | Spec Sheet                                                                                                                     |
| -----------------------:|:------------------------------------------------------------------------------------------------------------------------------ |
| CPU                     | Octa-core (4x2.8 GHz Kryo 385 Gold & 4x1.7 GHz Kryo 385 Silver)                                                                |
| Chipset                 | Qualcomm SDM845 Snapdragon 845                                                                                                 |
| GPU                     | Adreno 630                                                                                                                     |
| Memory                  | 6/8 GB RAM                                                                                                                     |
| Shipped Android Version | 9                                                                                                                              |
| Storage                 | 64/128/256 GB                                                                                                                  |
| Battery                 | Non-removable Li-Po 3700 mAh battery                                                                                           |
| Display                 | Optic AMOLED, 1080 x 2340 pixels, 19:9 ratio (~402 ppi density)                                                                |
| Camera (Back)           | Dual: 16 MP (f/1.7, 27mm, 1/2.6", 1.22µm, gyro-EIS, OIS) + 20 MP (16 MP effective, f/1.7, 1/2.8", 1.0µm), PDAF, dual-LED flash |
| Camera (Front)          | 16 MP (f/2.0, 25mm, 1/3", 1.0µm), gyro-EIS, Auto HDR, 1080p                                                                    |

Copyright 2018 - The LineageOS Project.

![OnePlus 6T](https://image01.oneplus.net/shop/201811/05/1366/0556b8f8752296ee50fe06cb5c700541.jpg)

## Let's start our journey


I'm too lazy to describe every step so basically connect your phone to your PC (which must have adb and fastboot installed):

1. first of all upgrade to the latest version of OxygenOS, as vendor stuff may change from each major version
2. Enable Developer options
3. Enable "OEM Unlock"
4. Reboot your phone in "bootloader mode" using `adb reboot fastboot`
5. !!! WIPES YOUR DATA !!! `fastboot unlock` and follow the instructions on screen
6. Boot the phone and don't add any kind of lock screen

### Download stuff

- [crDroid 7.3](https://crdroid.net/fajita)
- [TWRP](https://eu.dl.twrp.me/fajita/) download both ZIP and IMG file
- [Magisk](https://github.com/topjohnwu/Magisk/releases/latest)
- [nanodroid package](https://downloads.nanolx.org/NanoDroid/Stable)


### Install stuff

First of all, after unlocking your bootloader reboot back the phone into fastboot mode using `adb reboot fastboot`, then boot TWRP img file:

```
fastboot boot twrp.img
```
 
(replace `twrp.img` with the path to your TWRP img file dude)

Open install menu and follow the below instructions:

1. Open `Advanced/ADB Sideload`, swipe on `Swipe to start` and write `adb sideload crDroid.zip` (again, replace `crDroid.zip` with the path to the ROM zip)
2. Since, at the time of writing, crDroid hasn't yet implemented default TWRP, you'll have to flash it manually. Repeat the step 1 but sideload this time `twrp-installer.zip`
3. Reboot the phone in recovery mode (as this phone has A/B partition layout), and this time flash first Magisk, then nanodroid package.

After doing so, you'll have a fully working crDroid + microG + Magisk installation ^^

I definitely need to improve this guide since a monkey would write better than me rn lmao

