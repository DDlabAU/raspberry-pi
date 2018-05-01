# Guides til Raspberry Pi

## Hvad er en Raspberry Pi
[Raspberry Pi](https://www.raspberrypi.org/help/what-%20is-a-raspberry-pi/ "About Raspberry Pi") er en ting mellem en computer og en micro controller (som Arduino), der har en lang række applikationsmuligheder. Den har en tilsvarende formfaktor med en Arduino Uno og boardets GPIO'er kan tilsluttes knapper, LED'er og mange andre ting. På trods af dens størrelse kører den linux-styresystem hvor der er mulighed for at benytte sig af en traditionel GUI. Man kan også bruge den "headless mode" hvor bruges ved at skrive tekst og kode i dens terminal.

På denne side har vi samlet en del eksempler og guides til hvad en Raspberry Pi kan bruges til, men der er langt flere brugsscenarier. Mere inspiration kan findes på [Instructables](https://www.instructables.com/technology/raspberry-pi/) eller [Hackaday](https://hackaday.io/search?term=raspberry%20pi&tag=raspberry%2520pi&component=Raspberry%2520Pi).

DD Lab flere modeller som alle er til udlån. De to nyeste og dem vi anbefaler er [Raspberry Pi 3](https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/) og [Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/). De er begge udstyret med on-board WiFi.

## Installation af Raspberry Pi
Ved siden af vores to 3D-printere har lavet en Pi-arbejdsstation bestående af en Raspberry Pi 3, en skærm, tastatur og mus.
Der kan man sætte et SD-kort i en Pi (eller sætte en anden Pi til) for at sætte sit system op. Detaljerne om dette står herunder.

### Download styresystem
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

## Opsætning ved hjælp af terminal
Hvis Pi'en åbner GUI'en, så kan terminalen findes ved at trykke på ikonet i venstre top.

### Opsætning af WiFi
Detaljeret guide kan findes [her](https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md "WiFi setup"). Raspberry Pi kan forbindes til almindelige 2,4GHz WiFi, der er dog problemer med at komme på eduroam.

Skriv følgende i terminalen
```
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
```
reboot
dernæst gøre SSH tilgængelig
https://www.raspberrypi.org/documentation/remote-access/ssh/
192.168.0.105
	Windows PuTTY
		sådan
	Mac terminal
		sådan
