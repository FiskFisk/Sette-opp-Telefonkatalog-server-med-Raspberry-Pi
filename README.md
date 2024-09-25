# Sette-opp-Telefonkatalog-server-med-Raspberry-Pi

## Sette opp Raspberry Pi og Oppsett Linux:
### Intro:
Denne guiden hjelper deg med og sette opp en Raspberry Pi og Linxus. Mye av dette kan du gjøre med GUI også, men denne guiden vill vise osen du gjør det med terminalen.

- Oppsett av Raspberry Pi
- Oppdatering av systemet
- Sette opp en brannmur med UFW
- Sette opp SSH
- Fin IPen din - tenges for og bruke SSH
- Installering av Git, Python og MariaDB
- Sette opp en ny database-bruker og gi den riktig rettigheter
- Installere andre programvare
- Styr maskinen fra laptopen/pcen din med SSH
- Logge inn på serveren (Pi) ghennom cmd i Windows


### Guide:

### Oppsett av Raspberry Pi:
1. Koble sammen komponentene:
	* Åpne boksen: Pakk ut Raspberry Pi, koble til tastatur, mus, skjerm og nettverkskabel (om du bruker kablet nett).
	* Følg denne videoen: Hvis du er usikker på hvordan du monterer Raspberry Pi, kan du følge denne videoen: YouTube video.
2. Starte Raspberry Pi:
	* Sett i strømmen: Når alle komponentene er koblet til, sett strømmen til Raspberry Pi.
	* Oppdater operativsystemet: Åpne terminalen med Ctrl + Alt + T. Dette åpner et tekstvindu der du kan skrive kommandoer.

### Oppdatering av systemet:
1. Oppdater pakkelisten:
	* Skriv "sudo apt update" i terminalen og trykk Enter.
		Forklaring: Dette oppdaterer listen over tilgjengelige programvarepakker og sørger for at du har den nyeste informasjonen.
2. Installer oppdateringer:
	* Skriv deretter "sudo apt upgrade" og trykk Enter.
		* Forklaring: Dette installerer de nyeste versjonene av programvare som allerede er installert på systemet ditt.

### Sette opp en brannmur med UFW:
1. Installer UFW:
	* Skriv "sudo apt install ufw" og trykk Enter. Dette installerer en enkel brannmur.
2. Aktiver brannmuren:
	* Skriv "sudo ufw enable". Dette aktiverer brannmuren hver gang Raspberry Pi starter opp.
3.Tillat SSH-tilkobling:
	*Skriv "sudo ufw allow ssh". Dette gjør at du kan koble til Raspberry Pi fra en annen maskin.
4. Sjekk statusen:
	*For å bekrefte at brannmuren kjører, skriv "sudo ufw status".

### Sette opp SSH:
1. Installer SSH-serveren:
	* Skriv "sudo apt install openssh-server" for å installere SSH-serveren som lar deg koble til Raspberry Pi eksternt.
2. Aktiver SSH ved oppstart:
	* Skriv "sudo systemctl enable ssh" for å sørge for at SSH alltid er aktivert når Raspberry Pi starter.
3. Start SSH-serveren nå:
	* Skriv "sudo systemctl start ssh" for å starte SSH-serveren umiddelbart.

### Fin IP-en din - tenges for og bruke SSH:
1. "ip a"
2. Hvis du har kablet nettverk så wil IP-adressen vises ved eth0: linje. Hvis du kun har trådløst vil IP-adressen vises ved wlan0: linje. IP-adressen vil vanligvis bli 10.2.3.x eller noe lingnende (x står for et nummer mellom 2 og 254)

### Installering av Git, Python og MariaDB:
1. sudo apt install python3-pip
2. sudo apt install git
3. sudo apt install mariadb-server
4. sudo mysql_secure_installation

### Sette opp en ny database-bruker og gi den riktig rettigheter:
1. Logg inn i MariaDB "sudo mariadb -u root"
2. Lag ny bruker "CREATE USER 'username'@'localhost' IDENTIFIED BY 'passowrd';"
3. Gi den nye brukeren rettigheter "GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' IDENTIFIED BY 'password';"
4. Oppdater rettigheter "FLUSH PRIVILAGES;"

### Nå kan du installere andre programvare som for eksempel VS CODE, en annen nettlserer, wireshark, nmap, ect:
1. I Linux operativsystem installerer man programmer i terminalen med denne komandoen: "brukernavn@maskinnavn :~$ sudo apt install [programnavn]
1. Hvis du får trøbbel med VS Code, last ned .deb for arm64 fra https://code.visualstudio.com/docs/setup/linux Naviger til mappen du laster ned filen.
2. Skriv sudo apt install "./code" og trykk tab, så enter

Kjør "sudo apt update" og "sudo apt upgrade" igjen.

## Styr maskinen fra laptopen/pcen din med SSH:
Nå så kan du styre Pien fra laptopen din med SSH, f.eks. i CMD eller PowerShell. Hvis du vil koble til med ssh fra laptopen din:
1. Åpne Command Prompt på laptopen din med og for eksemepl søke det opp på windows seach baren.
2. Skriv "ssh brukernavn@ip" (bytt ut brukenavn og ip med dine)

PS: Skru av maskinen med "sudo shutdown now" og vent litt før du tar strømmen.

Hva er sudo? ("sudo" står for "superuser do" og gir deg rettigheter til å utføre kommandoer som krever admin-privileges.

#Telefonkatalog med Pi og database

For og logge in på brukeren in på PIen kan du skrive "mariadb -u [brukernavn] -p"

## Logge inn på serveren (Pi) ghennom cmd i Windows
1. Åpne command Prompt (cmd) og kjør (skriv): "ssh [brukernavn]@[ip-adresse]" bytt ut brukernanvet og ip-adressen til din Pi og press enter.
```
Microsoft Windows [Version 10.0.22631.4112]
(c) Microsoft Corporation. All rights reserved.

C:\Users\navn>ssh pi@172.29.51.19
pi@172.29.51.19's password:
```
Første gang du logger på med en ny maskin får du et sprøsmål, dette kan du svare "Yes" på.

Når du er logget inn vi terminalen se slik ut:
```
Linux raspberrypi 5.10.103-v7l+ #1529 SMP Tue Mar 8 12:24:00 GMT 2022 armv7l
The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.
Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Wed Sep 4 14:35:08 2024 from 10.2.1.89
pi@raspberrypi:~ $
```
Nå er har du connectet laptoppen/pcen din og raspberry Pi-en.

## Last ned (kolen) prosjektet fra GitHub
lag en katelog som heter kode og hent/klon projectet fra GitHub.
* pwd (print working directory)
* mkdir (make directory)
* cd (change directory)
* ls (list, vis alt i katalogen)
* cat (concatenate, vis innholdet i en fil)

```
pi@raspberrypi:~ $ pwd
/home/pi
pi@raspberrypi:~ $ mkdir kode
pi@raspberrypi:~ $ cd kode/
pi@raspberrypi:~/kode $ git clone
https://github.com/LektorRichvoldsen/telefonkatalog_og_database
Cloning into 'telefonkatalog_og_database'...
remote: Enumerating objects: 19, done.
remote: Counting objects: 100% (19/19), done.
remote: Compressing objects: 100% (17/17), done.
remote: Total 19 (delta 1), reused 1 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (19/19), done.
pi@raspberrypi:~/kode $ ls
telefonkatalog_og_database
pi@raspberrypi:~/kode $ cd telefonkatalog_og_database/
pi@raspberrypi:~/kode/telefonkatalog_og_database $ ls
python README.md sql
pi@raspberrypi:~/kode/telefonkatalog_og_database $ cd sql/
pi@raspberrypi:~/kode/telefonkatalog_og_database/sql $ ls
1_lag_database.sql 2_lag_tabell.sql 3_lag_testdata.sql 4_select_data.sql 
readme_sql.md
pi@raspberrypi:~/kode/telefonkatalog_og_database/sql $ cat readme_sql.md
I denne katalogen er det fire sql-script.
De kan kjøres ved kopiere koden inn i terminalvinduet til MySQL/MariaDB.
Scriptene må kjøres i rekkefølgen angitt av
tallene.pi@raspberrypi:~/kode/telefonkatalog_og_database/sql $
pi@raspberrypi:~ $ sudo apt install [programnavn]
```
## Lag database
logg inn i MariaDB og skriv/lim in koden fra de tre første sql-filene.
```
CREATE DATABASE telefonkatalog;
```
```
USE telefonkatalog;
CREATE TABLE person (
 id int NOT NULL AUTO_INCREMENT,
 fornavn VARCHAR(255) NOT NULL,
 etternavn VARCHAR(255) NOT NULL,
 telefonnummer CHAR(8),
 PRIMARY KEY (id)
);
```
```
INSERT INTO person (fornavn, etternavn, telefonnummer)
VALUES ('Erik', 'Perik', '12345678');
INSERT INTO person (fornavn, etternavn, telefonnummer)
VALUES ('Lise', 'Pise', '22334455');
INSERT INTO person (fornavn, etternavn, telefonnummer)
VALUES ('Testus', 'Jensen', '11114444');
INSERT INTO person (fornavn, etternavn, telefonnummer)
VALUES ('Knut', 'Donald', '31415926');
```
Test databasen med disse komandoene:
```
SELECT * FROM person;

SELECT fornavn, telefonnummer FROM person;

SELECT * FROM person WHERE fornavn = "Erik";

SELECT telefonnummer FROM person WHERE fornavn = "Lise" AND etternavn = "Pise";
```
##Koble Python-koden til databasen
I filene fra GitHub er det en Python-katalog. Hent filen telefonkatalog_oppdater_sql.py og lagre den på
laptopen (ikke på Pi-en).

I Python-koden er det flere steder der man skal koble til databasen. De ser slik ut:
```
mydb = mysql.connector.connect(
	host="172.29.51.19",
	user="test",
	password="1234",
	database="telefonkatalog"
)
```

##Teste prosjektet
Kjør Python-koden telefonkatalog_oppdater_sql.py fra laptopen din, og sjekk om personene fra databasen
dukker opp.

