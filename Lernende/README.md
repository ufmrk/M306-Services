# Werkstattauftrag W07 Webmin

## Autoren, Versionierung des Dokumentes

   • Autoren: Altin Maliqaj & Patrik Pribela
   
   • Mail: altin.maliqaj@edu.tbz.ch | patrik.pribela@edu.tbz.ch

   • Version: 2.0 (Edition für Lernende)
- - -
## Inhaltsverzeichnis
- [Werkstattauftrag W07 Webmin](#werkstattauftrag-w07-webmin)
  - [Autoren, Versionierung des Dokumentes](#autoren-versionierung-des-dokumentes)
  - [Inhaltsverzeichnis](#inhaltsverzeichnis)
  - [- OpenSource Lizenz](#--opensource-lizenz)
  - [Einfuehrung](#einfuehrung)
    - [Beschreibung: Welche Funktionen wird der Service erfuellen](#beschreibung-welche-funktionen-wird-der-service-erfuellen)
    - [Vorgesehener Zeitaufwand für die Realisierung](#vorgesehener-zeitaufwand-für-die-realisierung)
    - [Stolpersteine](#stolpersteine)
  - [Benoetigte Hard- und Software](#benoetigte-hard--und-software)
    - [Hardware (Materialliste, Funktionalitaet)](#hardware-materialliste-funktionalitaet)
    - [Software (Anforderungen, Firmware, OS-Image, ergaenzende SW-Packages, Abhängigkeiten, Funktionalitaet)](#software-anforderungen-firmware-os-image-ergaenzende-sw-packages-abhängigkeiten-funktionalitaet)
  - [Installationsanleitung (Didaktisch reduzierte Anleitung. Lernende sollen eigene Lösungswege realisieren)](#installationsanleitung-didaktisch-reduzierte-anleitung-lernende-sollen-eigene-lösungswege-realisieren)
    - [Hilfestellung (Tipps, Quellen...)](#hilfestellung-tipps-quellen)
  - [Qualitaetskontrolle (Pruefen der Funktionalitaet mit Ablauf von Kommandos und entsprechenden Outputs)](#qualitaetskontrolle-pruefen-der-funktionalitaet-mit-ablauf-von-kommandos-und-entsprechenden-outputs)
  - [Error-Handling](#error-handling)
    - [Allgemeine Schritte vor weiterem Debugging zwingend ausführen](#allgemeine-schritte-vor-weiterem-debugging-zwingend-ausführen)
    - [Webmin vom gleichen Netz und anderem Gerät nicht erreichbar](#webmin-vom-gleichen-netz-und-anderem-gerät-nicht-erreichbar)
  - [Quellen](#quellen)
  - [OpenSource Lizenz](#opensource-lizenz)
---
## Einfuehrung
In der folgenden Dokumentation ist die Installation, sowie Konfiguration samt allen Anforderungen von Webmin dokumentiert.
Alle Kommandos, welche im Terminal des Raspberry Pis ausgeführt werden müssen, sind in der folgenden [Abbildung](/img/cmd.png) einsehbar.

   ### Beschreibung: Welche Funktionen wird der Service erfuellen
   Webmin bietet eine graphische Oberfläche für Raspberry Pi Adminstratoren, welche das Betriebssystem gemäss Ihren wünschen konfigurieren möchten. Webmin arbeitet relativ einfach. Mittels GUI wählt man die gewünschte Konfiguration und im Hintergrund werden die textbasieren Konfigurationsdateien angepasst.
   ### Vorgesehener Zeitaufwand für die Realisierung
   Der Zeitaufwand beträgt unserer Schätzung nach 30 Minuten im Durchschnitt. Die Schätzung kann wegen Hardware-Build, Software-Version und Netzwerkanbindung abweichen.
   ### Stolpersteine
   Bei folgendem Projekt können mehrere **Stolpersteine** aufkommen, welche uns an einer erfolgreichen Umsetzung hindern können oder diese zumindest erschweren können. Um den gägnigsten Stolpersteinen aus dem Weg gehen zu können, wurden die gängigsten **Stolpersteine** aufgelistet.<br><br>
   **• Veraltete Version des Raspberry Pi**<br>
   Falls sich der Raspberry Pi nicht aktualisieren lässt und/oder die Hardware veraltet ist, kann (muss nicht!) es vorkommen, dass es zu Problemen bezüglich Kompatibilität führt. Wir empfehlen in einem solchen Fall eine virtuelle Maschine zu erstellen und das Raspbian OS aufzusetzen.<br>
   **• Restriktionen des (TBZ) Netzwerks**<br>
   Da öffentliche Netzwerke oft viele Sicherheitsmassnahmen eingepflegt erhalten, besteht die Möglichkeit, dass immer wieder Ports, welche essentiell für eine Anwendung sind, blockiert werden. Es gilt die Empfehlung bei Home Office Möglichkeit diese zu nutzen und aus dem Heimnetzwerk aus zu arbeiten.<br>
   - - -
## Benoetigte Hard- und Software
   ### Hardware (Materialliste, Funktionalitaet)
   • Raspberry PI<br>
   • Monitor + Peripherie (Maus und Tastatur)<br>
   • ggf. Netzwerkperipherie (Kabel, Switch)
   ### Software (Anforderungen, Firmware, OS-Image, ergaenzende SW-Packages, Abhängigkeiten, Funktionalitaet)
   • Neuste OS Version von Raspberry PI inkl. Updates<br>
   • Neuste Version von Webmin<br>
- - -
## Installationsanleitung (Didaktisch reduzierte Anleitung. Lernende sollen eigene Lösungswege realisieren)
• Paketliste aktualisieren<br>
• Geeignete Webmin version auswählen mit folgender [Quelle](https://sourceforge.net/projects/webadmin/files/webmin/)<br>
• Webmin Paket herunterladen und entpacken<br>
• Mittels Setup-Skript installieren
### Hilfestellung (Tipps, Quellen...)
In diesem Abschnitt stellen wir diverse Quellen zur Verfügung, welche als Hilfe bei der Installation gebraucht werden können.

[Beispiele zu Tar Kommandos](https://www.tecmint.com/18-tar-command-examples-in-linux/)<br>
[Webmin Versionierung](https://sourceforge.net/projects/webadmin/files/webmin/)<br>
[Webmin Wiki](http://doxfer.webmin.com/Webmin/Main_Page)
- - -
## Qualitaetskontrolle (Pruefen der Funktionalitaet mit Ablauf von Kommandos und entsprechenden Outputs)
• Aktivität des Webmin Dienstes prüfen<br>
`service webmin status`<br>
• Erreichbarkeit des Web-Interface im Browser prüfen<br>
`https://"hostname":10000/`<br>
- - -
## Error-Handling
Falls die Installation am Ende nicht ordnungsgemäss funktioniert, kann dies mehrere Gründe haben. Weiter unten finden Sie die gängigsten Fehler aufgelistet.
### Allgemeine Schritte vor weiterem Debugging zwingend ausführen
• Raspberry Pi neu starten<br>
• Prüfen, ob der Dienst der Anwendung läuft<br>
• Netzwerkverbindung prüfen<br>
• Restriktionen im Netzwerk ausschliessen
### Webmin vom gleichen Netz und anderem Gerät nicht erreichbar
Falls das Web-Interface aus dem selben Netzwerk von einem anderen Gerät nicht erreichbar ist gilt es zu prüfen, ob das Web-Interface vom *localhost* aus erreichbar ist. Falls dies der Fall ist, kann man davon ausgehen, dass über den die Kommunikation im Netzwerk Port 10000 nicht korrekt funktioniert. Hierbei ist ein Portscan hilfreich. Im Falle, dass auch hier das Web-Interface nicht erreichbar ist, kann man von einem Fehler der Anwendung ausgehen und eine neue Installation durchführen.
- - -
## Quellen
https://www.tecmint.com/18-tar-command-examples-in-linux/<br>
https://sourceforge.net/projects/webadmin/files/webmin/
http://doxfer.webmin.com/Webmin/Main_Page
- - -
## OpenSource Lizenz
![copyright](https://camo.githubusercontent.com/bf63a077023c34e5c61916eea81a068b4e44c86d51c08b8db9d2335a0b9af3b6/68747470733a2f2f692e6372656174697665636f6d6d6f6e732e6f72672f6c2f62792d6e632d73612f332e302f63682f38387833312e706e67)

Dieses Werk ist lizenziert unter einer [Creative Commons Namensnennung - Nicht-kommerziell - Weitergabe unter gleichen Bedingungen 3.0 Schweiz Lizenz](http://creativecommons.org/licenses/by-nc-sa/3.0/ch/)
