# Guides til Raspberry Pi

## Hvad er en Raspberry Pi
[Raspberry Pi](https://www.raspberrypi.org/help/what-%20is-a-raspberry-pi/ "About Raspberry Pi") er en ting mellem en computer og en micro controller (som Arduino), der har en lang række applikationsmuligheder. Den har en tilsvarende formfaktor med en Arduino Uno og boardets GPIO'er kan tilsluttes knapper, LED'er og mange andre ting. På trods af dens størrelse kører den linux-styresystem hvor der er mulighed for at benytte sig af en traditionel GUI. Man kan også bruge den "headless mode" hvor bruges ved at skrive tekst og kode i dens terminal.

På denne side har vi samlet en del eksempler og guides til hvad en Raspberry Pi kan bruges til, men der er langt flere brugsscenarier. Mere inspiration kan findes på [Instructables](https://www.instructables.com/technology/raspberry-pi/) eller [Hackaday](https://hackaday.io/search?term=raspberry%20pi&tag=raspberry%2520pi&component=Raspberry%2520Pi).

DD Lab flere modeller som alle er til udlån. De to nyeste og dem vi anbefaler er [Raspberry Pi 3](https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/) og [Raspberry Pi Zero W](https://www.raspberrypi.org/products/raspberry-pi-zero-w/). De er begge udstyret med on-board WiFi.

## Basis setup af Raspberry Pi
Ved siden af vores to 3D-printere har lavet en Pi-arbejdsstation bestående af en Raspberry Pi 3, en skærm, tastatur og mus. 

### Download styresystem
Der findes flere forskellige styresystemer til RP (Raspberry Pi), men et godt sted at starte er [Raspian](https://www.raspberrypi.org/downloads/raspbian/ "Raspian download page").
Man kan også downloade [NOOB (New Out Of the Box Software)](https://www.raspberrypi.org/downloads/noobs/ "NOOB download page") som er anbefalet til nybegyndere og giver mulighed for at installere andre styresystemer.

### Installere OS til SD-kortet
Der findes mange måder at gøre et SD-kort klar til RP. Har man eksempel lyst til at være terminal-kriger kan man det (selvom der er rig mulighed for at at lege med sin Matrix inspireret konsol når RP er oppe at køre)
Jeg kan anbefale at man bruger et 3. parts program for nemhedens skyld og [Etcher](https://etcher.io/ "Etcher webpage") er cross platform og nemt at gå til.

step 3
Sæt SD kort og pi til vores Pi-station ved siden af 3D-printerne.

Step 4
Der er nu to muligheder.
Den ene er at bruge den grafiske brugerflade og beholde den ved Pi-stationen eller sætte til en anden mus, tastatur og skærm.

Den anden er at køre headless og bruge SSH til at skrive til den fra egen computer
først på wifi
https://www.raspberrypi.org/documentation/configuration/wireless/wireless-cli.md
reboot
dernæst gøre SSH tilgængelig
https://www.raspberrypi.org/documentation/remote-access/ssh/
192.168.0.105
	Windows PuTTY
		sådan
	Mac terminal
		sådan
