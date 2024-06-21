# Dual Boot
For my Linux setup, I'm dual booting Windows and Linux. This is because I still rely on a lot of things that requires Windows that can't run under a VM. Most notably, this includes games that run with EasyAntiCheat. Also, I want to have as little as possible downtime on doing work when I need to, and ditching Windows entirely when I still have a lot of workflows and files on it just doesn't make that much sense.

## Issues encountered
### Linux Mint installer could not find my NVMe drive
For some reason, the Linux Mint installer could not find my main operating system drive (where Windows is installed) when selecting the partition to install to. Instead, it only showed my *old* OS drive (a SATA SSD) and no other option. Obviously, I wasn't installing there.

This was occuring even though the menu directly prior to that correctly identified that my laptop had Windows Boot Manager on it (at the last partition of my NVMe drive, since I had to recreate it after accidentally destroying the EFI partition on the SATA SSD).

I tried multiple things for this, including:
* Ensuring that Secure Boot and Fast Startup (in Windows' Power Options) were disabled
* Checked GParted to ensure that the drive could be detected
* Mounted the Windows NTFS partition to ensure that it's writable

Eventually, I just gave up and disconnected the SATA SSD for the duration of the install. This was a bit of a pain in the ass, since getting to my SSD involved unscrewing part of my laptop and taking out the SSD + the SATA connector which it's hooked on to. After this, the installer correctly detected the NVMe drive as the target installation drive, and I didn't have to manually configure partitions.

### fdisk popups during installation
This is more of a nitpick, but the average user would not know what `/dev/nvme0n1` is. Throwing raw fdisk messages as popups probably isn't the best idea. Funnily enough, a day before I installed Mint, I watched a video from Bog called "[The Linux Experience](https://youtu.be/8WkcLwXCFJQ?t=29)" which is more-or-less a documentary about his Linux install process. Within the first minute, he describes how the partition configuration screen completely wiped his own NVMe drive. Some improvement in UI is probably in order here.

### GRUB was not found by my OS
I installed Mint with Secure Boot disabled since Secure Boot was causing read issues with the flash drive I was using. In retrospect, I believe this is probably because I `xkill`ed the installer midway after it went unresponsive after trying to enroll an MOK when I tried to install with Secure Boot enabled. Disabling Secure Boot likely cleared this custom configuration, and made the flash drive readable again.

After installation, however, I found that I kept getting thrown into Windows no matter what I tried. In addition, no boot option for Linux was showing up on my Boot Selection (F12) menu. `efibootmgr` also failed to show me the EFI entry for Mint, just the one on the flash drive. It was only after I tried the following that I was able to boot with GRUB, and finally Mint:

1. Enter the BIOS settings
2. Enable Secure Boot
3. Go to Security and select "Select an UEFI file as trusted for executing"
4. Navigate to and find `EFI/ubuntu/shimx64.efi`
5. Save and reboot

Upon boot, I was presented with Secure Boot options, and since I installed Mint without configuring Secure Boot, I just selected "Continue boot" and waited for Mint to boot up. Finally, Mint booted successfully for the first time.

Once finished, I installed drivers I needed (NVIDIA's proprietary drivers, because there's no way I'm gaming on nouveau) which gave me a dialog to set up a Secure Boot password. After installing, I restarted and selected "Enroll MOK" instead of "Continue boot", typed in my password, and it let me in.

Since enrolling the MOK, I haven't been asked for a password while booting up. But Mint *does* boot with the proprietary drivers installed and I haven't had issues with drivers since.