# Bluetooth
I use a multitude of Bluetooth devices but in particular, I most frequently use Audio Technica  ATH-M20xBT Bluetooth Headphones and a PS4 DualShock Controller. Occasionally, I'll also use QCY T13 earbuds when my headphones run out of battery; I primarily use these earbuds on my phone instead.

All these devices connnect and disconnect at will, meaning I need them to work every single time and I don't want to spend time messing with them.

## Issues encountered
### Differing Bluetooth keys per OS
Running two operating systems under the same set of devices is bound to cause some issues. There are specifically issues with Bluetooth, with unfortunately relies on a key that gets stored on the computer post-pairing. For a single OS, this isn't an issue. But when dual-booting, Windows and Mint will conflict when attempting to pair the device on both OSes, as each OS will retain a different key locally, causing the Bluetooth device to communicate with one OS incorrectly.

The best solution is to just pull the keys from Windows and import them into Linux. The inverse is also possible, but editing the Windows registry from Linux feels incredibly dangerous, compared to just editing a file on `/var/lib/bluetooth`. This [Gist](https://gist.github.com/diffficult/574eb4807a7c61284dfe901f04382087) goes into detail on how to do exactly that, but a scripted version would help immensely (to be run when a device is paired to for the first time, or at some point before/during/after the pairing process).

### No auto-connection on startup
When I reboot my laptop on Windows, I usually get reconnected to my headphones as soon as it hits the lock screen. This isn't the case for Mint, unfortunately, and I have to manually reconnect to the headphones on startup. This is a bit of an annoyance that takes out a few seconds of my life, but this gets particularly annoying when I'm switching OSes and have to reboot multiple times in succession.