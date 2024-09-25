# Sette-opp-Telefonkatalog-server-med-Raspberry-Pi

Sette opp Raspberry Pi og Oppsett Linux:
	Intro:
Denne guiden hjelper deg med og sette opp en Raspberry Pi og Linxus. Mye av dette kan du gjøre med GUI også, men denne guiden vill vise osen du gjør det med terminalen.

	Guide:
Sette den opp:
1.	Åpne boxen og bygg Raspberry pi-en. Følg denne turtorialen som viser osen du bygger en Raspberry Pi   https://www.youtube.com/watch?v=S9CYlpbSz-c.
2.	Koble til en mus, tastatur og kjerm.
3.	Koble til nettet ditt

Server-oppsett
1.	press Ctrl + Alt + T på tastaturet ditt for og opne terminalen.(her skal du skrive kommandoene under)
2.	skriv «sudo apt update» i terminalen og trykk enter, (Dette vil finne oppdateringer)
3.	skriv derretter «sudo apt upgrade» (installere oppdateringer)

Sette opp en brannmur med UFW (skriv det under i terminalen)
1.	sudo apt intstall ufw (Installerer UFW “uncomplicated firewall”)
2.	sudo ufw enable (aktiverer brannmuren ved oppstarts)
3.	sudo ufw allow ssh ( tilater SSH-tilkoblinger gjennom brannmuren)
4.	Du kan sjekke statusen på brannmuren ved å skrive «sudo ufw status» 

Slå på ssh
1.	sudo apt install openssh-server (installerer SSH-serveren)
2.	sudp systemctl enable ssh (gjør at SSH slår seg på med oppstarts)
3.	sudo systemctl starts ssh (starter SSH her og nå)
