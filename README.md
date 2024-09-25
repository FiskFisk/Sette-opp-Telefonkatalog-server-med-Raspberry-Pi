# Sette-opp-Telefonkatalog-server-med-Raspberry-Pi

## Sette opp Raspberry Pi og Oppsett Linux:
	Intro:
Denne guiden hjelper deg med og sette opp en Raspberry Pi og Linxus. Mye av dette kan du gjøre med GUI også, men denne guiden vill vise osen du gjør det med terminalen.

	Guide:
Sette den opp:
1.	Åpne boxen og bygg Raspberry pi-en. Følg denne turtorialen som viser osen du bygger en Raspberry Pi   https://www.youtube.com/watch?v=S9CYlpbSz-c.
2.	Koble til en mus, tastatur og kjerm.
3.	Koble til nettet ditt

Server-oppsett:
1.	press Ctrl + Alt + T på tastaturet ditt for og opne terminalen.(her skal du skrive kommandoene under)
2.	skriv "sudo apt update" i terminalen og trykk enter, (Dette vil finne oppdateringer)
3.	skriv derretter "sudo apt upgrade" (installere oppdateringer)

Sette opp en brannmur med UFW (skriv det under i terminalen):
1.	sudo apt intstall ufw (Installerer UFW “uncomplicated firewall”)
2.	sudo ufw enable (aktiverer brannmuren ved oppstarts)
3.	sudo ufw allow ssh ( tilater SSH-tilkoblinger gjennom brannmuren)
4.	Du kan sjekke statusen på brannmuren ved å skrive "sudo ufw status"

Slå på ssh:
1.	sudo apt install openssh-server (installerer SSH-serveren)
2.	sudp systemctl enable ssh (gjør at SSH slår seg på med oppstarts)
3.	sudo systemctl starts ssh (starter SSH her og nå)

Fin IPen din - tenges for og bruke SSH:
1. "ip a"
2. Hvis du har kablet nettverk så wil IP-adressen vises ved eth0: linje. Hvis du kun har trådløst vil IP-adressen vises ved wlan0: linje. IP-adressen vil vanligvis bli 10.2.3.x eller noe lingnende (x står for et nummer mellom 2 og 254)

Installering av Git, Python og MariaDB:
1. sudo apt install python3-pip
2. sudo apt install git
3. sudo apt install mariadb-server
4. sudo mysql_secure_installation

Sette opp en ny database-bruker og gi den riktig rettigheter:
1. Logg inn i MariaDB "sudo mariadb -u root"
2. Lag ny bruker "CREATE USER 'username'@'localhost' IDENTIFIED BY 'passowrd';"
3. Gi den nye brukeren rettigheter "GRANT ALL PRIVILEGES ON *.* TO 'username'@'localhost' IDENTIFIED BY 'password';"
4. Oppdater rettigheter "FLUSH PRIVILAGES;"

Nå kan du installere andre programvare som for eksempel VS CODE, en annen nettlserer, wireshark, nmap, ect:
1. Hvis du får trøbbel med VS Code, last ned .deb for arm64 fra https://code.visualstudio.com/docs/setup/linux Naviger til mappen du laster ned filen.
2. Skriv sudo apt install "./code" og trykk tab, så enter

Kjør "sudo apt update" og "sudo apt upgrade" igjen.

## Styr maskinen fra laptopen/pcen din med SSH:
Nå så kan du styre Pien fra laptopen din med SSH, f.eks. i CMD eller PowerShell. Hvis du vil koble til med ssh fra laptopen din:
1. Åpne Command Prompt på laptopen din med og for eksemepl søke det opp på windows seach baren.
2. Skriv "ssh brukernavn@ip" (bytt ut brukenavn og ip med dine)

PS: Skru av maskinen med "sudo shutdown now" og vent litt før du tar strømmen.
Hva er sudo? ("sudo" står for "superuser do" og gir deg rettigheter til å utføre kommandoer som krever admin-privileges.
