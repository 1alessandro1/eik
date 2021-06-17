# Update process

Knowing how to properly update your Android smartphone with a custom ROM is part of the minimum knowledge in the Android modding world.
There are different ways to update your smartphone, but they commonly share one thing: *backup your data before proceeding*. You're warned, and I won't take any responsibility for a bricked device or a nuclear war :P

Let's first make some considerations:

- Of course you wanna first unlock your bootloader (the procedure depends on the device)
- the update procedure can be different between each device (especially A/B devices)
- TWRP de-roots your smartphone
- Additional Magisk modules persists during the update process
- Additional GApps packages must be reflashed again

# Non-A/B devices

If you had a smartphone before 2019 you'll probably have a non-A/B device.

**Q:** What does this mean?
**A:** The partition layout of the flash space contains the following partitions:

| Partition Name | Description |
|----------------|-------------|
| boot           | Contains the Linux kernel and a minimal root filesystem (loaded into a RAM disk). It mounts system and other partitions and starts the runtime located on the system partition. |
| system         | Contains the operating system             |
| vendor         | Contains proprietary libraries developed by OEMs (Xiaomi, OnePlus, Google etc.)            |
| userdata       | Contains the user-data. This partition isn't touched at all during OTAs            |
| recovery       | Contains a second complete Linux system, including a kernel and a special recovery system (e.g. TWRP)            |
| misc           | Tiny partition used by recovery to stash some information away about what it is doing in case the device is restarted while the OTA package is being applied.             |

## How should I update the ROM then?

**Please note that this procedure is generally valid with every flashable zip ROM**

Let's suppose that you have Magisk actually working on your system and you want to update your favourite ROM (e.g. LineageOS, crDroid et simila). The steps you need to take to are the following:

1. Be sure that the recovery is working and eventually update it (see below this page how to update the recovery)
2. Flash the ROM zip package
3. If previously needed, flash GApps package
4. If needed flash Magisk

**Please note that, starting from Magisk v22, you can flash directly `Magisk.apk` file. For more infos check out [here](https://github.com/topjohnwu/Magisk/releases/tag/v22.0) and [here](https://topjohnwu.github.io/Magisk/install.html))**

5. Reboot your phone

Okay and what about A/B devices instead?

# A/B devices

```
A/B system updates, also known as seamless updates, ensure a workable booting system remains on the disk during an over-the-air (OTA) update. This approach reduces the likelihood of an inactive device after an update, which means fewer device replacements and device reflashes at repair and warranty centers.

A/B system updates use two sets of partitions referred to as slots (normally slot A and slot B). The system runs from the current slot while the partitions in the unused slot are not accessed by the running system during normal operation. This approach makes updates fault resistant by keeping the unused slot as a fallback: If an error occurs during or immediately after an update, the system can rollback to the old slot and continue to have a working system. To achieve this goal, no partition used by the current slot should be updated as part of the OTA update (including partitions for which there is only one copy).
```

Credits [source.android.com documentation](https://source.android.com/devices/tech/ota/ab)

Those kind of device probably require more attention, since when you flash the ROM package you're actually flashing it onto the inactive slot, and this may lead to confusion to many users.

Don't worry, pasta boi will help you.

Given that you already have a working recovery, you should take the following steps:

1. Flash the ROM zip file
2. Flash recovery ZIP installer (some ROMs may replace your recovery :P)
3. Reboot in recovery mode again
4. Additionally flash GApps
5. Additionally flash Magisk

### smol explanation

Let's suppose that you're on slot A and follow the update process. Below the explanation of each step:

1. Flashes the ROM zip file onto the inactive slot `B`
2. Usually recovery ZIP installers flash on both slots
3. r u rly asking me what it does? xD Nah okay, basically it changes underhood the active slot from `A` to `B`
4. It's really important that you flash GApps after the step before, since GApps flashes only on the currently active slot
5. Same for Magisk :P

# Updating Recovery

This is probably one of the easiest task to achieve in Android modding, unless you have a Lagsung (for weirdo people, "Samsung").

Take one of the following procedures depending on your device type:

## Non-A/B devices

1. Reboot your phone onto fastboot mode
2. Ensure that `fastboot boot recovery.img` actually works, where `recovery.img` is your recovery image (TWRP, OrangeFox, PastaBoiCustomRecoveryImage)
3. If step 2 is successful, reboot again onto fastboot mode
4. `fastboot flash recovery recovery.img` where `recovery.img` is your recovery image (TWRP, OrangeFox, PastaBoiCustomRecoveryImage)
5. `fastboot reboot recovery` or reboot manually your phone onto recovery mode

## A-B devices

1. Reboot your phone onto fastboot mode
2. Ensure that `fastboot boot recovery.img` actually works, where `recovery.img` is your recovery image (TWRP, OrangeFox, PastaBoiCustomRecoveryImage)

**!!! THE FOLLOWING PROCEDURE DE-ROOTS YOUR PHONE !!!**

3. Install the ZIP file for your device (TWRP actually gives it, dunno about other recovery images)
4. Reboot manually your phone onto recovery mode
