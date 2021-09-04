### `.nanodroid-apps`

I'm a simple person and just use those applications:

- NewPipe - a FOSS YouTube client
- OAndBackupX - a FOSS backup utility
- OpenKeyChain - an OpenPGP implementation for Android
- Termux - a terminal emulator, probably the best I've ever used


### `.nanodroid-setup`

I've tweaked a little bit after finding the best combination for microG settings, but basically I use those:

- `nanodroid_microg=1` - installs microG GmsCore, GsfProxy, DroidGuard Helper and Nominatim Geocoder Backend
- `nanodroid_nlpbackend=1100` - Installs  Déjà Vu  and Mozilla uNlp backends  to install
- `nanodroid_mapsv1=1` - installs Maps v1 API support
- `nanodroid_play=01` - installs Fake Store
- `nanodroid_fdroid=1` - install official F-Droid client (alongside priviledged extension)
- `nanodroid_apps=1` - install all applications listed in .nanodroid-apps file
- `nanodroid_overlay=0` - use NanoDroid-Overlay
- `nanodroid_bash=1` - installs GNU Bash
- `nanodroid_init="10_sqlite 20_fstrim 30_logcat 40_external_sd 50_logscleaner"` - this setting is a list of init scripts, each listed item will be installed, possible values
- `nanodroid_gsync=1` - installs Google Sync Adapters
- `nanodroid_swipe=1` - installs Swipe libraries
- `nanodroid_forcesystem=0` - auto detects installation mode (in my case Magisk)
- `nanodroid_utils="findfs findmnt hexdump lessecho lesskey lsblk lscpu lsipc lslocks lsns ncal whereis"` - installs some utils

# Magisk Modules

For those who don't know yet what is Magisk, do you remember your old buddy SuperSU? It's a replacement that doesn't edit /system partition, which otherwise, will cause problems with other applications (see SafetyNet).

---

**Q:** Oh yes, what do you think about SafetyNet? Do you think that it'll protect the device from external tampering?

**A:** Well, my opinion about SafetyNet is really simple: having a locked/unlocked bootloader doesn't mean that your data will be still safe on the phone. Everyone can be easily hacked, and SafetyNet can't guarantee that.
In some cases, like mine, it's safer having Magisk + microG rather than using the stock ROM. Everything is under control and I don't have to worry about "am I using a safe device?".

Btw, those are the modules I use with Magisk:

- NanoDroid - microG stuff
- Systemless Hosts - Let's you edit hosts file without tampering the fs. Useful with AdAway ^^
- [GSync Adapters for Magisk by dreamwhite](https://github.com/dreamwhite/gsync_adapters_for_magisk/) - I still need the Google sync adapters so I made a quick magisk module. Feel free to contribute on it ^^
- [Advanced Charging Controller (ACC)](https://github.com/Magisk-Modules-Repo/acc), actually I'm using it since at the time of writing crDroid 7.5 on fajita has a broken Smart Charging feature that I had to disable. In any way, this module is perfect for my needs ^^

