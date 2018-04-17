# Guides til Raspberry Pi

## Indledende

Vi har i DD Lab flere modeller

## Basis setup af Raspberry Pi

### Download styresystem
Der findes flere forskellige styresystemer til RP (Raspberry Pi), men et godt sted at starte er [Raspian](https://www.raspberrypi.org/downloads/raspbian/).
Man kan også downloade [NOOB (New Out Of the Box Software)](https://www.raspberrypi.org/downloads/noobs/) som er anbefalet til nybegyndere og giver mulighed for at installere andre styresystemer.

### Installere OS til SD-kortet
Der findes mange måder at gøre et SD-kort klar til RP. Har man eksempel lyst til at være terminal-kriger kan man det (selvom der er rig mulighed for at at lege med sin Matrix inspireret konsol når RP er oppe at køre)
Jeg kan anbefale at man bruger et 3. parts program for nemhedens skyld og [Etcher](https://etcher.io/) er cross platform og nemt at gå til.

step 3
Sæt SD kort og pi til vores Pi-station ved siden af 3D-printerne.

Step 4
Der er nu to muligheder.
Den ene er at bruge den grafiske brugerflade og beholde den ved Pi-stationen eller sætte til en anden mus, tastatur og skærm.

Den anden er at køre headles og bruge SSH til at skrive til den fra egen computer
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
