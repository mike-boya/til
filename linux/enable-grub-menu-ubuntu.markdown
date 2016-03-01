# Unhide the GRUB boot menu on Ubuntu

Last night I needed to boot into single-user mode on one of my servers and was having a difficult time getting the GRUB menu to show up. The following steps summarize unhiding the GRUB menu.

This was on Ubuntu 14.04 LTS.

```bash
$ sudo vi /etc/default/grub
```
Comment out this line to show the GRUB menu on boot:

```bash
#GRUB_HIDDEN_TIMEOUT=0
```
Finally, run this command to apply the change:

```bash
sudo update-grub
```
I prefer the menu to appear on boot but simply uncomment the line and run the command to hide the menu.
