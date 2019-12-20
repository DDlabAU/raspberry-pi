
## Ting du skal bruge:
1x RaspberryPi 3 (Tidligere modeller kan også fungere)

1x Strømforsyning

1x RaspberryPi Camera Module V2

1x Skærm (Med HDMI indgang) + HDMI kabel


## 1. Se opsætning af RaspberryPi
[Her!](https://github.com/DDlabAU/raspberry-pi/blob/Omstrukturering/raspberry-pi-hurtig-start/README.md)

## 2. Kør RaspberryPi Camera igennem terminal

Man kan benytte sig af kommandoerne:

#### Raspistill

Skriver man 'raspistill' kommer de muligheder man har med kommandoen vist i terminalen. 
Et eksempel er:

'raspistill -o billede1.jpg'

Med denne kommando har man mulighed for at tage et billede direkte fra terminalen og gemme det. -o beslutter output formatet

### Uddybende guide:
https://www.raspberrypi.org/documentation/usage/camera/raspicam/raspistill.md

#### Raspivid

Skrives der 'raspivid', kommer der ligesom med billeder, kommandoer frem i terminalen

Her kan man teste med 'raspivid -t 20000 -o test.mp4'

'-t' er tidsintervallet den skal optage i, i millisekunder, og '-o' er igen outputformatet

## 3. Køre RaspberryPi Camera igennem Processing

For at downloade Processing til en Raspberry, kan du åbner terminalen og skrive følgende:

curl https://processing.org/download/install-arm.sh | sudo sh

Når download er færdig, er det sandsyneligt at du bliver nødt til at ændre i indstillingerne så du kan tilgå kameraet.

Skriv i terminalen: 

'raspiconfig' 
til interface - Serial ->no til login shell ->yes til enable

Alternativt kan du hente et image med Processing Pre-installed i Rasbian

[Processing Pi Image!](https://pi.processing.org/download/)
