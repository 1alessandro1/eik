# My NANKURUNAISA ROBBE MA STAI PRDENN A CAP experience

# MA SHPIEGATE MA COME E' SUCCESSO [source](https://www.youtube.com/watch?v=Cw5v9gyLz9c)

My modding experience started with a HTC HD2 on 2012, when my dad started discovering XDA-Developers forum and introduced me to that new world.
I was just a lil boi (just 11yo) but started having confidence with those stuff: ClockworkMod was my first recovery. I still remember the orange-themed UI, feelz :'(

Anyways this experience with the HTC HD2 didn't lasted too much sadly.
This phone had one issue since it's launch date: the touch screen was made of smashed potatoes and broke easily.

Where is the phone now? Idk, I was so fucking dumb and flushed it in the toilet lmao

![](https://i.pinimg.com/originals/f1/23/05/f1230501d33cb2c6055b2d6ea221a22d.jpg)

Going back to today, about 1 year ago I met a wonderful (obese lmao, no wait it's Ug0ne lmao lmao) person, @MaWalla (mawallera goes brrrrrrr), who helped me switching from OxygenOS (aka HorrendousOS) to crDroid, a ROM based on LineageOS (rust in pieces CyanogenMod).

He firstly started as a normal user of crDroid, but after a few months, due to the fact that the original maintainer broke the phone, has become the new ROM maintainer.
What to say about him? He's probably one of the best person I've ever met and I like especially one thing: HE LIKES GATINIS A A A .

Here a picture of a gatinos (a small cat. singular is gatinos, plural is gatinis):

![](https://i.pinimg.com/originals/35/de/21/35de21312b830288966469a6e35717ad.jpg)

# WAKEY WAKEY IT'S TIME FO SCHUL, CMMON MEN IZ TAIM FO SCHUL

Anyways, I don't even know what I'm doing with my life rn but just wanted to do a readme.md brrrrrr

Ah yes, now I remember: I just wanted to show you my dotfiles for nanodroid.
For those who don't yet know what is Nanodroid, basically it's part of microG project,

> A free-as-in-freedom re-implementation of Google’s proprietary Android user space apps and libraries.

Below a stupid explanation of my nanodroid dotfiles.
If you wanna use them, simply download/clone the repository and put the `.nanodroid*` files in `/sdcard`

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

# Applications that I suggest

Below a stupid list of applications that I've installed and found useful:

- AppManager - Let's you inspect stuff of applications like permissions and much more!
- Aria2App - Can I call it "JDownloader FOSS alternative" or you'll kill me? I discovered it thanks to a friend (@1alessandro1 goes brrrr) and I'm using it sometimes while downloading hentais (no FBI AGENT DON'T PLX AJKSHKJASH)
- ehm I was writing stuff please don't interrupt me agent
- Aurora Store (called AuwowaStowe by Ug0ne. Check out [wamawwo](https://github.com/dreamwhite/wamawwo)), it's a replacement for Google Play Store and works pretty flawlessly. You can download even paid apps, but please note that in-app purchases aren't working and license verification can't be done by microG :p
- Exodus - helps you to know which trackers and permissions are embedded in your apps
- F-Droid - does this even require an explanation? kkk, it's a FOSS store and is the main store where I download stuff
- Fake Contacts - This one is really useful and applies the "poison your data" concept to avoid Big Brother companies doing analysis on your contacts.
- ForgetMeNot - this app is for memorizing stuff using the "flash card" concept. Really useful tbf
- HERE WeGo - Google Maps replacement and works pretty fine ^^
- NetGuard - non-root firewall that let's you block internet traffic coming from applications. Personally I use it for blocking GBoard traffic since it may share data (who knows, better stay safe)
- NewPipe - A privacy-based YouTube client ^^
- OAndBackupX - You remember TitaniumBackup? I haven't yet used it too much but I like it
- Push Notification Tester - Useful for checking if GCM registering works or not
- SD Maid - Useful for cleaning the phone from caches and stuff. See it as a BleachBit alternative for Android. For those who are wondering "Is SD Maid Pro license working even if I have microG?" the answer is "YES!"
- UntrackMe - This one is a recent app I found during a binge-watching. It removes tracking information from social media links like tweets, Instagram posts and so on
- Warden - a FOSS application that lets you disable trackers and loggers ^^
- YouTube Vanced, an alternative YouTube client for those who don't wanna leave YouTube 
