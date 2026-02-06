# raspberrypi-home-server
Dieses Projekt beschreibt den Aufbau und die Konfiguration eines energieeffizienten "Always-On"-Servers auf Basis eines Raspberry Pi 4. 
Das Hauptziel ist die netzweite Filterung von Werbung und Tracking-Domains auf DNS-Ebene

Zielsetzung:
  Aufbau eines Servers für den "Headless"-Betrieb (Betrieb ohne Monitor und Tastatur).
  Zentrale Verwaltung von Netzwerkdiensten für alle Geräte im Heimnetz.
  Verbesserung der Privatsphäre durch netzweite Werbeblockierung

Verwendete Komponenten:
  Hardware 
    Raspberry Pi 4 Model B (4GB RAM).
    32GB microSD-Karte.
    Passives Kühlkörper-Set & Gehäuse für stabilen Dauerbetrieb.
  Software 
    Betriebssystem: Raspberry Pi OS (Linux).
    DNS-Filter: Pi-hole (Server-Applikation).
    Administration: OpenSSH für die Fernwartung via Windows PowerShell.
Projektablauf & Realisierung
  Headless Setup
    Das System wurde von Anfang an für den Betrieb ohne Peripheriegeräte konzipiert. WLAN und SSH wurden bereits bei der Image-Erstellung auf der microSD-Karte vorkonfiguriert.
  Netzwerk-Konfiguration
    Damit der Pi-hole zuverlässig funktioniert, wurde dem Server eine feste IP-Adresse zugewiesen. Die DNS-Einstellungen der Clients (z. B. Windows-Host) wurden angepasst, um den gesamten Datenverkehr über den Raspberry Pi zu leiten.
  Troubleshooting: Die SSH-Hürde
    Beim Erstzugriff traten Probleme mit der SSH-Syntax und der Benutzer-Authentifizierung auf. Durch systematisches Testen in der PowerShell konnte ich die Verbindung erfolgreich herstellen und die Systemaktualisierungen sowie die Pi-hole-Installation durchführen.
Verifizierung & Erfolg
  Der Erfolg des Projekts lässt sich direkt im Pi-hole Dashboard ablesen: Die Statistiken zeigen deutlich die Anzahl der blockierten DNS-Anfragen ("Queries Blocked"), während der reguläre Internetverkehr ungehindert fließt.
