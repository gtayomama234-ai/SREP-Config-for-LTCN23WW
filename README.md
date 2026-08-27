# Lenovo IdeaPad Slim 3 15IRU8 — SREP BIOS Unlock

This is my working **SREP (Smokeless Runtime EFI Patcher) configuration** for unlocking hidden BIOS menus on the **Lenovo IdeaPad Slim 3 15IRU8**.

I originally made this because a lot of the advanced H2O BIOS menus are present in the firmware but hidden from the normal BIOS interface.

## What this unlocks

After applying the config, I was able to access the hidden **Advanced** menus, including things like:

* CPU Configuration
* PCIe Configuration
* Power-related settings
* Debug Settings
* Boot Configuration
* Overclocking Settings
* Other hidden submenus

There are **a lot** of them.

## Confirmed working

I tested the `Active E-Cores` setting.

The original setting was:

`Active E-Cores → All`

I changed it to:

`Active E-Cores → 1`

After booting Windows, Task Manager showed:

`3 cores / 5 logical processors`

I then changed it back to:

`Active E-Cores → All`

and Windows returned to:

`6 cores / 8 logical processors`

So the unlocked menus aren't just cosmetic — at least some of the settings are actually functional.

## Files

The repository contains:

* `SREP_Config` — the SREP configuration
* `BOOTX64.EFI` — SREP EFI executable

Put the files on your EFI/SREP setup as required by your SREP installation.

## Compatibility

### Tested on

**Lenovo IdeaPad Slim 3 15IRU8**

This was tested on my own machine and firmware.

**Do not assume this works on every Lenovo laptop or every BIOS version.**

The patch patterns are firmware-specific. A different BIOS revision may use different data, GUIDs, or structures.

## Important warning

This is **firmware modification**.

Changing hidden BIOS settings can cause instability, configuration problems, or potentially prevent the system from booting.

I strongly recommend:

* Keep a recovery method available.
* Don't blindly enable random advanced settings.
* Change one setting at a time.
* Record the original value before changing anything.
* Don't assume an option is safe just because it appears in the menu.
* Make sure you know how to undo the changes before experimenting.

I am **not responsible for damage, data loss, or a non-booting system** caused by using these files.

## About SREP

This configuration was made for **SREP 0.1.4c (Smokeless Runtime EFI Patcher)**.

The original SREP project/source being archived is one of the reasons I'm publishing the working configuration here so that people working with the same firmware don't have to start completely from scratch.

## Why I made this

I spent a ridiculous amount of time digging through the H2O firmware, PE32 images, IDA output, IFR information, and SREP patch syntax before getting this working.

Hopefully this saves someone else from having to spend the same amount of time doing it. 😭

If you have the **same IdeaPad Slim 3 15IRU8** and try this, feel free to report whether it works for you.

---

**Tested:** Lenovo IdeaPad Slim 3 15IRU8
**SREP:** 0.1.4c
**Status:** Working / tested
