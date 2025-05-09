# Dactyl Manuform wireless

This tutorial based on last dactyl manuform (almost the same with the [original dactyl manuform 5x6](https://github.com/abstracthat/dactyl-manuform) I've built before.
So it won't include hardware wiring details.

One thing changed is that I decided to build a wireless one to fit my iMac.
So I have to change control board and firmware and add a battery.

## Control Board

I chosed [nice! nano](https://nicekeyboards.com/nice-nano) because it's a popular solution and compatible with the last control board (they have the same pin definition).

There isn't too much to care about at this part, except the way to get into bootloader is to connect the GND and the RST twice quickly.

To flash firmware into nice! nano, use usb cable to connect it to computer then copy .uf2 file into the file system appeared when it's in bootloader.

## Battery

Still not much to care, pick a popular chargable battery online, wire the red wire to B+ pin on nice! nano and black wire to B-, that's all. 

I chose 2000mah battery, according to the [prediction](https://zmk.dev/power-profiler), left keyboard could work 3 months while the right one near a year.

## Firmware

[ZMK](https://zmk.dev/) is made for this. 

To say it briefly:

1. Find a repo, here is a [5x6 layout one](https://github.com/IoakeimSogiakas/dactyl_manuform_5x6-ZMK).
2. Fork it on your Github account. Click **Action**(on top with *Code*, *Pull request*, etc.) to enable it.
3. Change the keymap to your satisfaction, here is a good [web app](https://nickcoutsos.github.io/keymap-editor/) for it, or you could edit on your local computer.
4. For the web, save it. For local edit just push commit. Then with **Github Action's** help it will automatically starting compiling firmware for you.
5. Download the firmware.zip in Github Action, unzip it. Flash the *\_\_left__.uf2* to your left nice! nano, the right one to your right nice! nano.

That's all! Check if it is working. Later when you want to change keymap you could use [ZMK Studio](https://zmk.studio/), you don't need those flashing steps again.

By the way, I recreate a shell to make more space: [my shell](https://ryanis.cool/dactyl/#manuform).
