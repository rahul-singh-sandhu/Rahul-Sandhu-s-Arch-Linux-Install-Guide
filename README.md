# Rahul Sandhu's Arch Linux Install Guide
A guide for how I like to setup Arch Linux
## Requirements
1) USB Flash Drive 4Gb or more
2) An x86-64 or i686 based PC
3) Basic Terminal Knowledge
4) Some time and patience
## Creating a bootable USB
First, go to archlinux.org/download/, scroll down to HTTP Direct Downloads, and choose a mirror server thats closest to your location. Then, right click on the file named **archlinux-yyyy.mm.dd-x86_64.iso**, and click copy link. Next, enter a terminal and type **wget** followed by pasting the link you copied. If you are on Windows or macOS, you can download a tool called balenaEtcher to create the bootable USB.
![image](https://user-images.githubusercontent.com/90906486/172376617-0f20356d-def8-4b05-91e2-3099596e3b7e.png)
Simply select the file you downloaded earlier, select your USB drive and click Flash.

For Linux users, you can use dd. Simply open a terminal and type lsblk. Now look for the disk that has the same size as your USB drive and is mounted at run/media/$USER/.... Note down the name on the left hand side. In my case it is sdg. Then, type sudo dd **if=path/to/archiso of=/dev/youusbdrivelocation bs-1M status=progress**. In my case, that would be **sudo dd if=~/archlinux-2022.06.01-x86_64.iso of=/dev/sdg bs=1M status=progress**.

Lets break down this command. The **dd** is used to copy the file. The **if=** is used to specifiy the file location. The **of=** specifies the location of the drive to be copied to. **The bs=1M** tells dd to copy at 1M at a time. Finally, the **status=progress** shows how much data has been copied.

After that, plug the USB drive into the computer you want to install Arch Linux on, and move on to the next step.
## Booting into the USB and connecting to the internet.
