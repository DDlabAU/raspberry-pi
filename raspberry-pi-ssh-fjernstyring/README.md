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
