[Tilbage til Forsiden](https://github.com/DDlabAU/raspberry-pi/tree/Omstrukturering)

Der er taget udgangspunkt i denne [guide](https://medium.com/stories-from-upstatement/how-to-build-a-web-kiosk-with-a-raspberry-pi-some-cables-and-a-tv-3dc2724acaa1 "raspberry pi kiosk mode"), men med et par modifikationer.

## How to Make the Kiosk

### Installer chromium browser
Det nye Raspian kommer med chromium, så derfor behøves det ikke at installeres.
Hvis man vil være sikker på at det er installeret kan man køre følgende kommando: `sudo apt-get install chromium-bsu`

### Remove the mouse cursor when it is not in use
`sudo apt-get install x11-xserver-utils unclutter`

### Make Chromium autostart when the desktop has loaded
```
cd .config/lxsession/LXDE-pi/
sudo nano autostart
```
Skriv følgende i filen:
```
chromium-browser -kiosk -incognito http://github.com/ddlabau

@lxpanel --profile LXDE-pi
@pcmanfm --desktop --profile LXDE-pi
@xscreensaver -no-splash
@point-rpi

@xset s noblank
@xset s off
@xset -dpms
@unclutter -idle 0.1 -root
```
tryk derefter `Ctrl`+`x` og derefter `Y`, `Enter` for at gemme.

### Turn off powersave/sleep

Run *sudo nano /etc/lghtdm/lighdm.conf* from a terminal window to edit *lightdm.conf*
```
sudo nano /etc/lightdm/lightdm.conf
```
Edit this line `#xserver-command=X`  
Change it to `xserver-command= X -s 0 -dpms`  
Close the nano editor with *CTRL+X* and save the file when asked


### Install two plugins in Iceweasel
installer plugin som i chrome
auto refresh
http://64px.com/auto-refresh/ifooldnmmcmlbdennkpdnlnbgbmfalko
eller easy auto refresh
https://chrome.google.com/webstore/detail/easy-auto-refresh/aabcgdmkeabbnleenpncegpcngjpnjkc
Hvis det skal virke med kiosk så skal man enable plugin'et i incognito mode.


Reboot and you are done

## Resources
- https://gist.github.com/radavis/5e94651a89da5e16c613
- http://www.instructables.com/id/Raspberry-Pi-Wall-Mounted-Google-Calendar/?ALLSTEPS
- http://wiki.linuxwall.info/doku.php/en:ressources:astuces:lxde_debian_autostart
- http://crunchbang.org/forums/viewtopic.php?id=18090


[Tilbage til Forsiden](https://github.com/DDlabAU/raspberry-pi/tree/Omstrukturering)
