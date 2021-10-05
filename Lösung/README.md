# Werkstattauftrag W07 Webmin

## Autoren, Versionierung des Dokumentes

   • Autoren: Altin Maliqaj & Patrik Pribela
   
   • Mail: altin.maliqaj@edu.tbz.ch | patrik.pribela@edu.tbz.ch
- - -

## Einführung
In der folgenden Dokumentation ist die Installation, sowie Konfiguration samt allen Anforderungen von Webmin dokumentiert.
Alle Kommandos, welche im Terminal des Raspberry Pis ausgeführt werden müssen, sind in der folgenden [Abbildung](/img/cmd.png) einsehbar.

   ### Beschreibung: Welche Funktionen wird der Service erfüllen
   Webmin bietet eine graphische Oberfläche für Raspberry Pi Adminstratoren, welche das Betriebssystem gemäss Ihren wünschen konfigurieren möchten. Webmin arbeitet relativ einfach. Mittels GUI wählt man die gewünschte Konfiguration und im Hintergrund werden die textbasieren Konfigurationsdateien angepasst.
   ### Vorgesehener Zeitaufwand für die Realisierung
   Der Zeitaufwand beträgt unserer Schätzung nach 30 Minuten im Durchschnitt. Die Schätzung kann wegen Hardware-Build, Software-Version und Netzwerkanbindung abweichen.
   ### Stolpersteine
- - -
## Benötigte Hard- und Software
   ### Hardware (Materialliste, Funktionalität)
• Raspberry PI<br>
• Monitor + Peripherie (Maus und Tastatur)<br>
   ### Software (Anforderungen, Firmware, OS-Image, ergänzende SW-Packages, Abhängigkeiten, Funktionalität)
• Neuste OS Version von Raspberry PI inkl. Updates<br>
• Neuste Version von Webmin<br>

- - -
## Installationsanleitung (Lösungsweg)
### Raspberry Pi Betriebssystem updaten<br>
Nach dem Sie den Raspi mit SD Karte von der Lehrperson erhalten haben, führen Sie als erstes die Betriebssystem Updates aus. So können Sie dann jegliche veraltete Systemfehler meiden. Dies machen Sie mit folgendem Befehl im Terminal:<br>
sudo apt-get update<br>
sudo apt-get upgrade
### Paket: libnet-ssleay-perl installieren<br>
Als nächstes muss man eine Skriptsprache installieren, damit das Webmin später per SSL auf seinen Server zugreifen kann. Diese Sprache installiert man auch im Terminal mittels folgendem Befehl:<br>
sudo apt-get install libnet-ssleay-perllibio-socket-ssl-perl
### Webmin Version nachforschen
Da es verschiedene Webmin Versionen gibt, installiert man die aktuellste Versionen welche hier zu finden ist:<br>
https://sourceforge.net/projects/webadmin/files/webmin/<br>

In unserem Beispiel ist die aktuellste Version die 1.981 Version. Dies wird dann auch dementsprechend im Befehl angepasst:<br><br>
Ins Home Verzeichnis navigieren:<br>
cd<br><br>
Webmin vom Internet herunterladen:<br>
wget http://prdownloads.sourceforge.net/webadmin/webmin-1.981-minimal.tar.gz<br><br>
Die Datei nun entpacken:<br>
tar -zxvf webmin-1.881-minimal.tar.gz<br><br>
Nun im Verzeichnis das Setup ausführen:<br>
cd webmin-1.981<br>
sudo ./setup.sh
### Webmin installieren
Sämtliche Einstellungen können auf Default gesetzt und durchgeklickt werden. Beim Anmeldenamen kann man eines auswählen oder auch auslassen. Beim Auslassen wird dann einfach der Name "admin" generiert. Was jedoch wichtig ist, ist dass man ein Passwort festlegt.<br>
[Adminpasswort](/img/adminpasswort.png)

- - -
## Qualitätskontrolle (Prüfen der Funktionalität mit Ablauf von Kommandosund entsprechenden Outputs)
• Aktivität des Webmin Dienstes prüfen<br>
`service webmin status`<br>
• Erreichbarkeit des Web-Interface im Browser prüfen<br>
`https://"hostname":10000/`<br>
- - -
## Error-Handling
Falls die Installation am Ende nicht ordnungsgemäss funktioniert, kann dies mehrere Gründe haben. Weiter unten finden Sie die gängigsten Fehler aufgelistet.
### Allgemeine Schritte vor weiterem Debugging zwingend ausführen
• Raspberry Pi neu starten
• Prüfen, ob der Dienst der Anwendung läuft
• Netzwerkverbindung prüfen
• Restriktionen im Netzwerk ausschliessen
### Webmin vom gleichen Netz und anderem Gerät nicht erreichbar
Falls das Web-Interface aus dem selben Netzwerk von einem anderen Gerät nicht erreichbar ist gilt es zu prüfen, ob das Web-Interface vom *localhost* aus erreichbar ist. Falls dies der Fall ist, kann man davon ausgehen, dass über den die Kommunikation im Netzwerk Port 10000 nicht korrekt funktioniert. Hierbei ist ein Portscan hilfreich. Im Falle, dass auch hier das Web-Interface nicht erreichbar ist, kann man von einem Fehler der Anwendung ausgehen und eine neue Installation durchführen.
- - -
## Quellen