![RaspberryPi](images/RaspberryPi.jpg)

## Hvad er en Raspberry Pi
[Raspberry Pi](https://www.raspberrypi.org/help/what-%20is-a-raspberry-pi/ "About Raspberry Pi") er et board som er en blanding mellem en computer og en micro controller (som Arduino).  Raspberry Pi's har et indbygget styrresystem på samme måde som din computer, men den har også GPIO'pins der kan tilsluttes knapper, LED'er, og mange andre ting, hvilket giver den en lang række applikationsmuligheder. På trods af boardets lille størrelse har den relativt meget processorkraft, og det kører et linux-styresystem hvor der er mulighed for at benytte sig af en traditionel GUI. Derudover har nyere Raspberry Pi boards wifi og bluetooth indbygget hvilket gør det muligt at tilgå den i en "headless mode" hvilket betyder at den kan fjernstyres.

DD Lab har flere forskellige Raspberry Pi modeller som alle er til udlån. De to nyeste og dem vi anbefaler er [Raspberry Pi 3](https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/) og [Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/). De er begge udstyret med on-board WiFi.

## DD-Lab Guides

[Hurtig førstegangsopsætning af Raspberry Pi](/raspberry-pi-hurtig-start/README.md)

[SSH opsætning til Fjernstyring af Raspberry Pi](/raspberry-pi-ssh-fjernstyring/README.md)

[Guide til Raspberry Pi-Cam](/raspberry-pi-cam/README.md)

[Guide til at lave en Raspberry Pi TV Kiosk til at vise informationer](/raspberry-pi-kiosk)



### Raspberry Pi: Brugbare kommandoer & instillinger

#### Opdater og installer programmer og system
```
sudo apt-get update
sudo apt-get upgrade
```

#### Instillinger 
```
sudo raspi-config
```
Her kan du skifte adgangskode, brugernavn, ændre tastatur layout, udvide filsystem og lign.

## Raspberry Pi projekt eksempler

http://www.pimusicbox.com/

https://github.com/dtcooper/raspotify

https://support.hifiberry.com/hc/en-us/articles/205377651-Configuring-Linux-4-x-or-higher

https://github.com/DDlabAU/raspberryPiKiosk
