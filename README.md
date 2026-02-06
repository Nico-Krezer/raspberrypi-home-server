# 🖥️ Virtualisierungs-Testumgebung (Windows & Ubuntu)

Dieses Projekt dokumentiert den Aufbau eines privaten Testnetzwerks zwischen einem Windows 11 Host-System und einer virtuellen Ubuntu-Maschine. Der Fokus lag auf der Netzwerkkonfiguration und der Optimierung des Datenaustauschs.

---

## 🎯 Zielsetzung
* Einrichtung einer stabilen, privaten Netzwerkverbindung zwischen Host und VM.
* Implementierung eines nahtlosen Datenaustauschs über gemeinsame Ordner.
* Systematisches Troubleshooting bei Konfigurationsproblemen.

---

## 🛠️ Komponenten
* **Virtualisierungs-Software:** Oracle VirtualBox.
* **Gast-System:** Ubuntu Desktop.
* **Host-System:** Windows 11.
* **Tools:** VirtualBox Guest Additions.

---

## ⚙️ Projektablauf & Realisierung

### 1. Netzwerk-Konfiguration (Host-only)
Die VM wurde auf den **Host-only Adapter** umgestellt, um ein privates Netzwerk zu schaffen:
* **Host-IP:** `192.168.56.1`
* **Ubuntu-VM IP:** `192.168.56.100` (statisch vergeben).
* **Verifizierung:** Erfolgreicher bidirektionaler Verbindungstest mittels **ping**-Befehl.

### 2. Troubleshooting: Fehlende Netzwerk-Treiber
Während der Einrichtung standen die Modi "Internes Netzwerk" und "Host-only Adapter" nicht zur Auswahl. 
* **Lösung:** Durchführung der **"Repair"-Funktion** des VirtualBox-Installers, um die fehlenden virtuellen Netzwerk-Treiber korrekt nachzuinstallieren.

### 3. Integrierter Datenaustausch
Für eine effiziente Arbeit wurden "Gemeinsame Ordner" eingerichtet:
* **Voraussetzung:** Erfolgreiche Installation der **VirtualBox Guest Additions**.
* **Rechteverwaltung:** Hinzufügen des Ubuntu-Benutzers zur Gruppe `vboxsf` (`sudo adduser $USER vboxsf`).
* **Ergebnis:** Automatischer Mount des Ordners unter `/media/sf_VM-Austausch` beim Systemstart.

---

## 💡 Learnings
Ich habe gelernt, wie man spezifische Virtualisierungs-Features nutzt, um eine performante Testumgebung zu schaffen. Besonders die Fehleranalyse bei fehlenden Treibern und das Management von Linux-Gruppenberechtigungen waren wichtige Bestandteile dieses Projekts.
