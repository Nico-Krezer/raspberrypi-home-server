# 🌐 Raspberry Pi Home Server & DNS-Sinkhole

[cite_start]Dieses Projekt beschreibt den Aufbau und die Konfiguration eines energieeffizienten "Always-On"-Servers auf Basis eines Raspberry Pi 4[cite: 87, 102]. [cite_start]Das Hauptziel ist die netzweite Filterung von Werbung und Tracking-Domains auf DNS-Ebene für alle Geräte im Haushalt[cite: 93, 99].

---

## 🎯 Zielsetzung
* [cite_start]**Headless-Betrieb:** Aufbau eines Servers ohne Monitor und Tastatur[cite: 98].
* [cite_start]**Zentrale Verwaltung:** Steuerung der Netzwerkdienste für alle Geräte im Heimnetz[cite: 24, 99].
* [cite_start]**Privatsphäre & Performance:** Verbesserung des Surf-Erlebnisses durch netzweite Werbeblockierung[cite: 25, 99].

---

## 🛠️ Verwendete Komponenten

### Hardware
* [cite_start]**Raspberry Pi 4 Model B** (4GB RAM)[cite: 102].
* [cite_start]**32GB microSD-Karte**[cite: 103].
* [cite_start]**Passives Kühlkörper-Set & Gehäuse** für stabilen Dauerbetrieb[cite: 104].

### Software
* [cite_start]**Betriebssystem:** Raspberry Pi OS (Linux)[cite: 106].
* [cite_start]**DNS-Filter:** Pi-hole (Server-Applikation)[cite: 108].
* [cite_start]**Administration:** OpenSSH für die Fernwartung via Windows PowerShell[cite: 109, 113].

---

## ⚙️ Projektablauf & Realisierung

### 1. Headless Setup
[cite_start]Das System wurde von Anfang an für den Betrieb ohne Peripheriegeräte konzipiert[cite: 98, 111]. [cite_start]WLAN und SSH wurden bereits bei der Image-Erstellung auf der microSD-Karte vorkonfiguriert[cite: 111].

### 2. Troubleshooting: Die SSH-Hürde
[cite_start]Beim Erstzugriff traten Probleme mit der **SSH-Syntax** und der **Benutzer-Authentifizierung** auf[cite: 113]. [cite_start]Durch systematisches Testen in der PowerShell konnte ich die Verbindung erfolgreich herstellen und die Systemaktualisierungen sowie die Pi-hole-Installation durchführen[cite: 113, 114].

### 3. Netzwerk-Automatisierung (DHCP-Integration)
Um die Lösung auf ein professionelles Level zu heben, wurde die Konfiguration von manuellen Client-Einträgen auf eine **zentrale Automatisierung** umgestellt:
* [cite_start]**Statische IP:** Dem Raspberry Pi wurde die feste Adresse `192.168.2.102` zugewiesen[cite: 115].
* **Router-Konfiguration:** Die IP des Pi-hole wurde direkt im Router als primärer DNS-Server hinterlegt.
* **LAN & WLAN Support:** Dadurch profitieren nun automatisch alle Geräte – egal ob per LAN-Kabel oder Funk verbunden – von der Filterung.

---

## 📊 Verifizierung & Erfolg
[cite_start]Der Erfolg des Projekts lässt sich direkt im **Pi-hole Dashboard** ablesen[cite: 117]: 
* [cite_start]Die Statistiken zeigen deutlich die Anzahl der blockierten DNS-Anfragen (**"Queries Blocked"**)[cite: 117].
* [cite_start]Der reguläre Internetverkehr wird weiterhin korrekt und ungehindert verarbeitet[cite: 117].

---

## 💡 Learnings
[cite_start]Dieses Projekt war mein intensiver Einstieg in die **Linux-Administration über die Kommandozeile**[cite: 123]. [cite_start]Ich habe gelernt, wie man Systeme ohne grafische Oberfläche verwaltet, Netzwerkprobleme analysiert und wie wichtig die korrekte Syntax bei verschlüsselten Verbindungen (SSH) ist[cite: 124, 125].
