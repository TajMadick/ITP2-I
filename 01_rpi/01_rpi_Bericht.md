# Arbeitsbericht
 
**Fach: ITP2-I**
 
**Name: Mate Szvercseg und Alexander Schauer**
 
**Klasse: 4AHITS**
 
**Datum: 02.10.2026**
 
**Aufgabenstellung: [01_rpi](https://github.com/HTL-Braunau-probst/ITPI-4/blob/main/0101_rpi.md)**

## Vorbereitung
 - Rasperberrypie Image Herunterladen
 ![alt text](images/image.png)


##  Start

**Aufgabenstellung:**
- Konfiguriere ein passendes Tastaturlayout
- Konfiguriere so, dass der RPi die IP Adresse per DHCP bezieht.
- Setze einen eindeutigen Hostnamen.
- Sicherheitsmaßnahme: Es soll kein Login mit Default Login Daten möglich sein.
- Auf den RPi soll per SSH zugegriffen werden können. Konfiguriere weiters Login per SSH keys.


**Was haben wir gemacht?**  

im Imager
- Raspberry Pi 3 Board auswählen 
- RPI OS 64 Bit auswählen
- Speichermedium: Internal SD-Card medium
- Hostname auswählen, unser Hostname: Berta
- **Lokalisierung:** 
  - Hauptstadt: Vienna 
  - Zeitzone: Europe/Vienna 
  - Tastatur Layout: AT
- Benutzername: berta
- Passwort: berta123
- WLAN: Überspringen -> Wir verwenden LAN
- SSH: Aktivieren -> Passwort zu authentifizierung verwenden
- Rasberry Pi Connect: nicht aktivieren
- Image: schreiben

![alt text](images/image1.png)

Lan Kabel einstecken und in Terminal ```ip addr``` eingeben

Falsches Lan Kabel verwendet, deswegen kein internet verbindung (20 min Fehlersuche, ohne KI) 

![alt text](images/image2.jpeg)

## Remote Desktop

**Aufgabenstellung:**
- Teste die Erreichbarkeit des RPi im Schulnetz per ping und ssh.
- Arbeite nun weiter mit einer Kali VM auf einem Schulrechner. Teste auch hier die Verbindung zum RPi.
- Konfiguriere Remote Desktop: Es soll von der Kali VM aus die GUI des RPi dargestellt werden können. Das Ziel dabei ist in weiterer Folge auf die eigenen Tastatur und Monitor am RPi verzichten zu können.

**Was haben wir gemacht:**
- Rasperry Pi gepingt
![alt text](images/image3.png)
- Rasperry Pi per ssh 
![alt text](images/image4.png)
- Rpi von Kali (VmWare) pingen
![alt text](images/image%20(1).png)
- auf Kali ssh Verbindung zu Rpi erstellen ```ssh berta@10.200.83.121```
-  dann auf berta remote Steuerung und Konfiguration erlauben durch ```sudo raspi config ```
![alt text](images/Média%20(13).jpg)
- Download VNC Server auf Kali
![alt text](images/Média%20(12).jpg)
![alt text](images/Média%20(10).jpg)
- alles auf oke
  ![alt text](images/Média%20(9).jpg)
- bei VNC server den IP des RPis eingeben
  ![alt text](images/Média%20(8).jpg)
- als nächste Berta und als Passwort: berta123
![alt ext](images/Média%20(7).jpg)

![alt text](images/Média%20(15).jpg)
- Runter zu -> about raspi-config
![alt text](images/Média%20(14).jpg)
![alt text](images/Média%20(16).jpg)
- enterdrucken dann geht der Remote Steuerung.
  


## Remote Development
**Aufgabenstellung:**  
Konfiguriere Visual Studio Code (sollte bei Kali schon installiert sein – zum Test code in der shell eingeben) zum remote development auf dem Raspberry Pi. Dabei verwendet man VS Code unter Kali als Editor, ist aber per SSH mit dem RPi verbunden und editiert die Dateien dort, das in VS Code integrierte Terminal ist ebenfalls mit dem RPi verbunden.

Folge z.B. dem Tutorial unter Visual Studio Code: Remote development over SSH. Hinweis: Azure ist nicht notwendig weil wir einen RPi als remote machine haben.

Bringe den im Totorial beschriebenen Node JS express Server zu laufen.

- Auf Kali Vs Code starten
- Remote ssh extension auf das Vs code installieren
  ![alt text](images/image%20(4).png)
- als nächste Vs code neustarten 
- links unten auf das symbol clicken
-   ![alt text](images/image%20(5).png)
- dann "connect to host" auswählen
![alt text](images/image%20(6).png) 
- ```configure host```
  ![alt text](images/Bild%20(4).png)
- enter clicken
- Daten des Rpi im configuration einschreiben
![alt text](images/Bild%20(5).png)
- config speicher und zu machen
- wieder links unten auf das Symbol clicken
- connect to Host -> den IP des RPis auswählen -> enter
- Passwort von berta eingeben
 ![alt text](images/image%20(7).png)
- Juhu es funktioniert
![alt text](images/image%20(8).png) 


  
