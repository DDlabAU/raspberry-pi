<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Guides til Raspberry Pi](#guides-til-raspberry-pi)
  - [Hvad er en Raspberry Pi](#hvad-er-en-raspberry-pi)
  - [Installation af Raspberry Pi](#installation-af-raspberry-pi)
    - [Download styresystem](#download-styresystem)
    - [Installere OS til SD-kortet](#installere-os-til-sd-kortet)
    - [Boot styresystem](#boot-styresystem)
    - [Opdatere styresystem](#opdatere-styresystem)
  - [Opsætning ved hjælp af terminal](#ops%C3%A6tning-ved-hj%C3%A6lp-af-terminal)
    - [Opsætning af WiFi](#ops%C3%A6tning-af-wifi)
    - [Opsætning af SSH](#ops%C3%A6tning-af-ssh)
      - [På Mac](#p%C3%A5-mac)
      - [På Windows](#p%C3%A5-windows)
      - [Static IP](#static-ip)
    - [Raspberry Pi instillinger](#raspberry-pi-instillinger)
  - [Raspberry Pi eksempler](#raspberry-pi-eksempler)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Hvad er en Raspberry Pi
[Raspberry Pi](https://www.raspberrypi.org/help/what-%20is-a-raspberry-pi/ "About Raspberry Pi") er et board som er en blanding mellem en computer og en micro controller (som Arduino).  Raspberry Pi's har et indbygget styrresystem på samme måde som din computer, men den har også GPIO'pins der kan tilsluttes knapper, LED'er, og mange andre ting, hvilket giver den en lang række applikationsmuligheder. På trods af boardets lille størrelse har den relativt meget processorkraft, og det kører et linux-styresystem hvor der er mulighed for at benytte sig af en traditionel GUI. Derudover har nyere Raspberry Pi boards wifi og bluetooth indbygget hvilket gør det muligt at tilgå den i en "headless mode" hvilket betyder at den kan fjernstyres.

DD Lab har flere forskellige Raspberry Pi modeller som alle er til udlån. De to nyeste og dem vi anbefaler er [Raspberry Pi 3](https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/) og [Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/). De er begge udstyret med on-board WiFi.

## Installation af Raspberry Pi
Ved siden af vores to 3D-printere har lavet en Pi-arbejdsstation bestående af en Raspberry Pi 3, en skærm, tastatur og mus.
Der kan man sætte et SD-kort i en Pi (eller sætte en anden Pi til) for at sætte sit system op. Detaljerne om dette står herunder.

### Download Styresystem
  
Der findes flere forskellige styresystemer til RP (Raspberry Pi), men et godt sted at starte er [Raspian](https://www.raspberrypi.org/downloads/raspbian/ "Raspian download page") og hvad denne guide tager udgangspunkt i.
Man kan også downloade [NOOB (New Out Of the Box Software)](https://www.raspberrypi.org/downloads/noobs/ "NOOB download page") som er anbefalet til nybegyndere og giver mulighed for at installere andre styresystemer.

### Installere OS til SD-kortet
Der findes mange måder at gøre et SD-kort klar til RP. Har man eksempel lyst til at være terminal-kriger kan man det. RPs egen guide kan findes [her](https://www.raspberrypi.org/documentation/installation/installing-images/ "flash and install").
Jeg kan anbefale at man bruger et 3. parts program for nemhedens skyld og [Etcher](https://etcher.io/ "Etcher webpage") er cross platform og nemt at gå til.

### Boot styresystem
Sæt SD-kortet i Pi-station ved siden af 3D-printerne og sæt strøm til RP'en.

Der er nu to muligheder.
Den ene er at bruge Pi'ens egen grafiske brugerflade og bruge tastatur. Vælges denne så kan man koble den på wifi, skifte kode, starte browseren osv, på samme hvis som man ville gøre med en almindelig computer.

Den anden er at køre headless, hvilket vil sige at Pi'en ikke åbner GUI'en men istedet systemets terminal.
Resten af denne guide vil fokusere på hvordan man bruger terminalen til at lave opsætningen færdig.

### Opdatere styresystem
For at sikre at Pi'en har de nyeste opdateringer kan man åbne terminalen  ved at trykke på ikonet i venstre top på ikonet med `>_`. Skriv derefter følgende:

```
sudo apt-get update
sudo apt-get upgrade
```
Det kan tage et godt stykke tid, så hav lidt tålmodighed.

## Opsætning ved hjælp af terminal
Hvis Pi'en åbner GUI'en, så kan terminalen findes ved at trykke på ikonet i venstre top.

### Opsætning af WiFi
Detaljeret guide kan findes [her](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md "WiFi setup"). Raspberry Pi kan forbindes til almindelige 2,4GHz WiFi, der er dog problemer med at komme på eduroam.

Skriv følgende i terminalen
```
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```
Nederst i filen der åbnes skal der skrives følgende
```
network={
    ssid="wifi navn"
    scan_ssid=1
    psk="wifi kode"
}
```
For at lukke filen trykkes der `Ctrl+x`, `Y` og så `Enter`.
Linjen `scan_ssid` kan undlades, men er anvendelig, hvis man vil forbinde til et gemt netværk.

Skriv dernæst `sudo reboot now` for at genstarte og ændringerne træder i kraft.

### Opsætning af SSH
Det kan være en kæmpe fordel at sætte  [SSH](https://www.raspberrypi.org/documentation/remote-access/ssh/ "guide til opsætning af SSH") adgang op. SSH er en måde at fjernstyre sin Pi på, fra en terminal på en anden computer. Pi's er gode til at bygge ind i prototyper eller fast installeret uden skærm. SSH gør det nemt at ændre og programmere Pi'en uden man skal have den sat til skærm og tastetur.

Man "tænder" for SSH ved at åbne Raspberry Pi's instillinger der åbnes ved at skrive følgende i terminalen
```
sudo raspi-config
```
Gå til `Interfacing Options`, `SSH`, vælg ja, tryk ok og så finish.

For at kunne interface Pi'en vha SSH skal man kende dens IP-adresse som kan findes ved at skrive følgende ind i terminalen
```
hostname -I
```

#### På Mac
kan man bruge den indbyggede terminal ved at skrive
```
ssh pi@<Indsæt IP-adresse>
```
Derefter skal man logge ind hvor brugeren er `pi` og koden er `raspberry`. Man kan ikke se koden når man skriver. Det anbefales man ændre login i `sudo raspi-config`

#### På Windows
skal man bruge et tredjepartsprogram og vi anbefaler programmet [PuTTY](https://www.putty.org/), hvor man skal bruge IP-adresse, bruger og kode til Pi'en. Hvis der kommer en advarsel når man tilslutter sig Pi'en skal man blot trykke `Yes` og dernæst kommer man videre til en Terminal der er magen til den på Mac og den som Pi'en selv har.

### Raspberry Pi instillinger
```
sudo raspi-config
```
Skifte adgangskode, bruger, ændre tastatur layout.

## Raspberry Pi eksempler

http://www.pimusicbox.com/

https://github.com/dtcooper/raspotify

https://support.hifiberry.com/hc/en-us/articles/205377651-Configuring-Linux-4-x-or-higher

https://github.com/DDlabAU/raspberryPiKiosk
