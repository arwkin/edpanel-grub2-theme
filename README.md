# edpanel-grub2-theme
## Elite Dangerous Role Panel Theme for the GRUB2 boot loader
Created by [Arwkin](https://github.com/arwkin)

![edpanel screenshot 1](edpanel1.jpg?raw=true "Screenshot example 1")
![edpanel screenshot 2](edpanel2.jpg?raw=true "Screenshot example 2")
![edpanel screenshot 3](edpanel3.jpg?raw=true "Screenshot example 3")
**Note:** These instructions have been tested with Linux Mint and Antergos.

#### Preparation
Determine if your video card can display 1920x1080 in GRUB.
1. Reboot and wait for the GRUB screen to appear.
2. Press "c" to open the command line.
3. Type `vbeinfo` to see supported resolutions.
4. Look for 1920x1080. If this resolution is present, continue with the installation. This theme is not recommended with lower resolutions.

#### Install

1. Copy the folder **edpanel** to */boot/grub/themes*
```
sudo mkdir -p /boot/grub/themes
sudo cp -a edpanel /boot/grub/themes
```

2. Add the following lines to **/etc/default/grub** (Replace or comment out any duplicate entries)
```
GRUB_THEME="/boot/grub/themes/edpanel/theme.txt"
GRUB_GFXMODE="1920x1080"
```
3. Update the grub.cfg file.This may be different depending on your Linux distro. For example:
`sudo update-grub`
**or**
`sudo grub-mkconfig -o /boot/grub/grub.cfg`


#### Uninstall
1. Remove the **edpanel** directory to permanently remove all of the files.
`sudo rm -rf /boot/grub/themes/edpanel`
2. Remove or comment out lines beginning with **GRUB_THEME** and **GFXMODE** in **/etc/default/grub**

#### Other
- Grub menu items may be renamed directly (by advanced users) or by using a tool such as [Grub-Customizer](https://git.launchpad.net/grub-customizer) by Daniel Richter.
- Two ED themed icons can be used in place of normal OS icons. **pilots-fed.png** and **ed-mat-grade5.png**  menuentry example:
```
menuentry "Modify High Grade Firmware" --class ed-mat-grade5 'uefi-firmware' {
  fwsetup
}
```

#### Credits
- Screen capture image is from the game Elite Dangerous by [Frontier Developments](http://frontier.co.uk/) o7
- Original Euro Caps font by [Tom Oetken](https://www.fonts4free.net/fonts-by-tom-oetken.html)
- Original OS icons by [Vimix](http://vinceliuice.deviantart.com/art/Grub-themes-vimix-0-1-532580485)
- Other ED themed icons which can be used as OS icons sourced from [Elite Dangerous Assets](https://edassets.org)


____________________________________________________________________________
