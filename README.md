# Moving to Linux
So you're moving to Linux. Either you want a fresh start, Microsoft fucked you over, or something else.

Linux is a completely different environment that Windows, so the experience isn't seamless. This repository attempts to detail everything I hit, and what I did in response, from installation all the way to near-daily use. This may or may not include things that I appreciated. Don't be dissuaded from using Linux based on what's written here; switching is definitely a plus if you have the time, knowledge, and patience.

And no, I'm not calling it GNU/Linux.

## Setup
I'm using an Acer TravelMate P249-G2-MG, a laptop that I've had for 5-ish years. Funnily enough, this laptop came pre-packaged with "Acer Linux", whatever that was. No clue what it actually was; 

For my OS of choice, I decided to go with Linux Mint for the following reasons:
* I wanted something Debian-based, since I had most experience dealing with Debian from system administration.
* Just Debian was a bit too little for me; I wanted little to no complicated customization.
* Something that felt *similar* to Windows would be good; though Cinnamon is not the best for this, it's pretty okay.
* I needed an OS that can just *work* for a wide variety of uses. Overall, I use this laptop for:
  * programming (usually done with JetBrains IDEs)
  * gaming (usually from Steam; the only games I play that aren't from Steam are Minecraft and Honkai: Star Rail)
  * productivity (usually through Microsoft Office, which my university pays for)
  * system administration (SSH, Docker, etc.)
  * web browsing (usually with Firefox, which makes this area more painless than others)
    * This unfortunately includes sandboxed web browsing, like with the Respondus Lockdown Browser, which just *doesn't* work on Linux *at all*.
  * virtualization (usually with VirtualBox; this is for both university work and sandboxing [SCM](https://en.wikipedia.org/wiki/Software_configuration_management) tests)
  * recording and streaming (usually with OBS Studio)
  * audio editing (usually with Audacity/Tenacity)
  * video editing (usually with Adobe Premiere)
  * graphic design (usually with Adobe Illustrator)

## .*fetch

```
                                     chlod@Chlods-Laptop
################  ################   -------------------
################  ################   OS: Windows 11 Pro x86_64
################  ################   Host: Acer TravelMate P249-G2-MG
################  ################   Kernel: 10.0.22631
################  ################   Uptime: 5 hours, 17 mins
################  ################   Packages: 168 (pacman)
################  ################   Shell: bash 5.2.15
                                     Resolution: 1366x768, 1366x768
################  ################   DE: Aero
################  ################   WM: DWM.exe
################  ################   CPU: Intel i7-7500U (4) @ 2.910GHz
################  ################   GPU: NVIDIA GeForce 940MX
################  ################   GPU: Intel(R) HD Graphics 620
################  ################   Memory: 13012MiB / 32636MiB
################  ################
```

```
             ...-:::::-...                 chlod@Chlods-Laptop 
          .-MMMMMMMMMMMMMMM-.              ------------------- 
      .-MMMM`..-:::::::-..`MMMM-.          OS: Linux Mint 21.3 x86_64 
    .:MMMM.:MMMMMMMMMMMMMMM:.MMMM:.        Host: TravelMate P249-G2-MG V1.18 
   -MMM-M---MMMMMMMMMMMMMMMMMMM.MMM-       Kernel: 6.5.0-41-generic 
 `:MMM:MM`  :MMMM:....::-...-MMMM:MMM:`    Uptime: 40 mins 
 :MMM:MMM`  :MM:`  ``    ``  `:MMM:MMM:    Packages: 2421 (dpkg), 22 (flatpak) 
.MMM.MMMM`  :MM.  -MM.  .MM-  `MMMM.MMM.   Shell: bash 5.1.16 
:MMM:MMMM`  :MM.  -MM-  .MM:  `MMMM-MMM:   Resolution: 1366x768, 1366x768 
:MMM:MMMM`  :MM.  -MM-  .MM:  `MMMM:MMM:   DE: Cinnamon 6.0.4 
:MMM:MMMM`  :MM.  -MM-  .MM:  `MMMM-MMM:   WM: Mutter (Muffin) 
.MMM.MMMM`  :MM:--:MM:--:MM:  `MMMM.MMM.   WM Theme: Mint-L-Dark-Blue (Mint-Y) 
 :MMM:MMM-  `-MMMMMMMMMMMM-`  -MMM-MMM:    Theme: Mint-L-Dark-Blue [GTK2/3] 
  :MMM:MMM:`                `:MMM:MMM:     Icons: Mint-L-Blue [GTK2/3] 
   .MMM.MMMM:--------------:MMMM.MMM.      Terminal: gnome-terminal 
     '-MMMM.-MMMMMMMMMMMMMMM-.MMMM-'       CPU: Intel i7-7500U (4) @ 3.500GHz 
       '.-MMMM``--:::::--``MMMM-.'         GPU: NVIDIA GeForce 940MX 
            '-MMMMMMMMMMMMM-'              GPU: Intel HD Graphics 620 
               ``-:::::-``                 Memory: 4484MiB / 31956MiB 
```

On a TravelMate P249-G2-MG, the BIOS is an Insyde V2.30.

## Index
1. [Dual Boot](/dual-boot/README.md) (and other installation notes)
2. [Flatpak](/flatpak)
3. Alt-Tab Menu
4. [Bluetooth](/bluetooth/)
5. Screenshots
6. [Emoji Picker](/emoji-picker)
7. Games and NTFS
8. Streaming and Recording with QSV

## Overall comments
* It would be nice to have something that syncs data from Windows to Linux. In particular, this includes wallpapers, Bluetooth keys, and a bunch of other things that is meant to make the experience of using peripherals with either OS seamless.
