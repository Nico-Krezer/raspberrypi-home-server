# 🌐 Raspberry Pi Home Server & DNS-Sinkhole

Dieses Projekt beschreibt den Aufbau und die Konfiguration eines energieeffizienten "Always-On"-Servers auf Basis eines Raspberry Pi 4. Das Hauptziel ist die netzweite Filterung von Werbung und Tracking-Domains auf DNS-Ebene für alle Geräte im Haushalt.

---

## 🎯 Zielsetzung
* **Headless-Betrieb:** Aufbau eines Servers ohne Monitor und Tastatur.
* **Zentrale Verwaltung:** Steuerung der Netzwerkdienste für alle Geräte im Heimnetz.
* **Privatsphäre & Performance:** Verbesserung des Surf-Erlebnisses durch netzweite Werbeblockierung.

---

## 🛠️ Verwendete Komponenten

### Hardware
* **Raspberry Pi 4 Model B (4GB RAM)**
* **32GB microSD-Karte**
* **Passives Kühlkörper-Set & Gehäuse** für stabilen Dauerbetrieb

### Software
* **Betriebssystem:** Raspberry Pi OS (Linux)
* **DNS-Filter:** Pi-hole (Server-Applikation)
* **Administration:** OpenSSH für die Fernwartung via Windows PowerShell

---

## ⚙️ Projektablauf & Realisierung

### 1. Headless Setup
Das System wurde von Anfang an für den Betrieb ohne Peripheriegeräte konzipiert. WLAN und SSH wurden bereits bei der Image-Erstellung auf der microSD-Karte vorkonfiguriert.

### 2. Troubleshooting: Die SSH-Hürde
Beim Erstzugriff traten Probleme mit der SSH-Syntax und der Benutzer-Authentifizierung auf. Durch systematisches Testen in der PowerShell konnte ich die Verbindung erfolgreich herstellen und die Systemaktualisierungen sowie die Pi-hole-Installation durchführen.

### 3. Netzwerk-Automatisierung (DHCP-Integration)
Um die Lösung auf ein professionelles Level zu heben, wurde die Konfiguration von manuellen Client-Einträgen auf eine **zentrale Automatisierung** umgestellt:
* **Statische IP:** Dem Raspberry Pi wurde die feste Adresse `192.168.2.102` zugewiesen.
* **Router-Konfiguration:** Die IP des Pi-hole wurde direkt im Router als primärer DNS-Server hinterlegt.
* **LAN & WLAN Support:** Dadurch profitieren nun automatisch alle Geräte – egal ob per LAN-Kabel oder Funk verbunden – von der Filterung.

---

## 📊 Verifizierung & Erfolg
Der Erfolg des Projekts lässt sich direkt im **Pi-hole Dashboard** ablesen:
* Die Statistiken zeigen deutlich die Anzahl der blockierten DNS-Anfragen (**"Queries Blocked"**).
* Der reguläre Internetverkehr wird weiterhin korrekt und ungehindert verarbeitet.

---

## 💡 Learnings
Dieses Projekt war mein intensiver Einstieg in die **Linux-Administration über die Kommandozeile**. Ich habe gelernt, wie man Systeme ohne grafische Oberfläche verwaltet, Netzwerkprobleme analysiert und wie wichtig die korrekte Syntax bei verschlüsselten Verbindungen (SSH) ist.
