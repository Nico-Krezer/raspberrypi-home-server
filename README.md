# 🌐 Raspberry Pi Home Server & DNS-Sinkhole

[cite_start]Dieses Projekt dokumentiert den Aufbau eines energieeffizienten "Always-On"-Heimservers auf Basis eines Raspberry Pi 4. Ziel ist die netzweite Filterung von Werbung und Tracking-Domains auf DNS-Ebene für alle Geräte im Haushalt[cite: 56, 68].

---

## 🎯 Zielsetzung
* [cite_start]**Headless-Betrieb:** Konfiguration und Verwaltung ohne Monitor/Tastatur[cite: 67].
* [cite_start]**Zentrale Verwaltung:** Steuerung der Netzwerkdienste für das gesamte Heimnetz[cite: 68].
* [cite_start]**Performance:** Verbesserung der Netzwerksicherheit durch Reduzierung von unerwünschtem Traffic[cite: 68].

---

## 🛠️ Verwendete Komponenten

### Hardware
* [cite_start]**Raspberry Pi 4 Model B (4GB RAM)** [cite: 71]
* [cite_start]**32GB microSD-Karte** [cite: 72]
* [cite_start]**Passives Kühlkörper-Set & Gehäuse** für lautlosen Dauerbetrieb [cite: 73]

### Software
* [cite_start]**Betriebssystem:** Raspberry Pi OS (Linux) [cite: 75]
* [cite_start]**DNS-Filter:** Pi-hole (Server-Applikation) [cite: 77]
* [cite_start]**Administration:** OpenSSH für die Fernwartung via Windows PowerShell [cite: 78, 82]

---

## ⚙️ Projektablauf & Realisierung

### 1. Headless Setup & SSH
[cite_start]Die Hardware wurde montiert und das OS für den Betrieb ohne Peripherie vorkonfiguriert[cite: 80]. Der Erstzugriff erfolgte via SSH. 
* [cite_start]**Troubleshooting:** Probleme mit der SSH-Syntax und Authentifizierung wurden durch systematisches Testing behoben[cite: 82].

### 2. Netzwerk-Automatisierung (DHCP-Integration)
Um eine nahtlose Integration zu erreichen, wurde das System auf zentrale Steuerung umgestellt:
* [cite_start]**Statische IP:** Der Pi wurde fest auf `192.168.2.102` konfiguriert[cite: 84].
* **Router-Integration:** Die IP des Pi-hole wurde im Router als primärer DNS-Server hinterlegt.
* **LAN & WLAN Support:** Alle Geräte (kabellos oder per LAN-Kabel) profitieren nun automatisch ohne manuelle Einzelkonfiguration von der Filterung.

---

## 📊 Verifizierung & Erfolg
[cite_start]Der Erfolg ist direkt im Pi-hole Dashboard sichtbar[cite: 86]. [cite_start]Die Block-Statistiken zeigen die gefilterten Anfragen in Echtzeit, während der restliche Datenverkehr stabil bleibt[cite: 86].

---

## 💡 Learnings
[cite_start]Dieses Projekt war mein Einstieg in die **Linux-Administration via Kommandozeile**[cite: 92]. [cite_start]Ich habe gelernt, wie man Systeme "headless" verwaltet, Netzwerkprobleme (DNS/IP) analysiert und wie kritisch die korrekte Syntax bei verschlüsselten Verbindungen ist[cite: 93].
