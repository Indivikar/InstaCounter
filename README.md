# InstaCounter

# Stückliste

| Nr. | Menge |         Bauteil                 |                    Links                    |                                                      Daten & Bemerkungen                                                                                                                       |
|:---:| :---: |---------------------------------|                    :---:                    |                                                      :---:                                                                                                                        |
|  1  |   1   | AZ-Delivery ESP32 Dev Kit C V4  | [Link](https://www.amazon.de/dp/B07Z83MF5W?th=1) | [Datenblatt](https://cdn.shopify.com/s/files/1/1509/1638/files/ESP32_devKitCV4_datasheet.pdf?v=1675936435)                                                                        |
|  2  |   2   | 4-Ziffern 7-Segment Display     | [Link](https://www.amazon.de/dp/B00SLYARJQ?th=1) | [Herstellerseite](https://www.adafruit.com/product/881)                                                                                                                           |
|  3  |   1   | Lochrasterplatten Set           | [Link](https://www.amazon.de/dp/B08TMMZPWT) |                                                                                                                                                                                    |
|  4  |   1   | Micro USB Kabel                 | [Link](https://www.amazon.de/dp/B0BBG1CMGY) |        USB Kabel für das ESP32 Entwicklerboard, ACHTUNG - das Kabel muss ein grossen Querschnitt haben                                                                                                                                                                         |


# Arduino IDE Einstellungen
Ich habe zum programmieren der ESP32 die [Arduino IDE 2](https://www.arduino.cc/en/software#future-version-of-the-arduino-ide) genutzt, nach der Installation der Arduino IDE
müssen noch ein paar einstellungen vorgenommen werden.

### ESP32 (mit CP2102) Treiber installieren
1. Den [ESP32-Treiber](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers?tab=downloads) (CP210x Universal Windows Driver) runterladen und entpacken
2. Den ESP32 mit einem USB-Kabel an den Rechner anschliessen
3. Den Geräte-Manager öffnen (Windows-Taste + X > Geräte-Manager)
4. In der Liste, unter "Anschlüsse (COM & LPT)" sollte der ESP32 mit einer Warnung stehen
5. Rechts-Klick > Treiber aktualisieren > Auf meinem Computer nach Treibern suchen
6. Durchsuchen... > [den Ordner mit Treiber auswählen] > Weiter
7. Nach der Installation sollte die Warnung im Geräte-Manager weg sein und können fortfahren

### ESP32 in der Arduino IDE installieren
1. Gehe in der Arduino IDE 2.0 zu Datei > Einstellungen
2. Kopiere die folgende Zeile und füge sie in das Feld „Zusätzlicher Boardverwalter-URLs“ ein und bestätige mit OK
`https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json`
3. Gehe in der Arduino IDE 2.0 zu Werkzeuge > Board > Board-Verwaltung
4. In der Liste nach "esp32 von Espressif" suchen und installieren

### Arduino IDE Konfiguration für den ESP32
Die Konfiguration kann unter dem Menü-Punkt `Werkzeuge` vorgenommen werden.
- Board:              `ESP32 Dev Module`
- CPU Frequency:      `240MHz (WiFi/BT)`
- Core Debug Level:   `None`
- Flash Frequency:    `80MHz`
- Flash Mode:         `QIO`
- Flash Size:         `4MB (32Mb)`
- Partition Scheme:   `Default 4MB with spiffs (1.2MB APP/1.5MB SPIFFS)`
- PSRAM:              `Disable`
- Upload Speed:       `921600`

## Bibliotheken die noch installiert werden müssen
| Nr. | Import                  |                    Name                     | Version |     Bemerkungen   |
|:---:| :---:                   |---------------------------------------------|  :---:  |        :---:      |
|  1  | ArduinoJson.h           | ArduinoJson von Benoit                      | v6.20.1 |                   |
|  2  | Adafruit_GFX.h          | Adafruit GFX Library von Adafruit           | v1.11.5 |                   |
|  3  | Adafruit_LEDBackpack.h  | Adafruit LED Backpack Library von Adafruit  | v1.3.2  |                   |

# Schaltung

### ESP32 mit 2x 7-Segment Display
![alt text](https://github.com/Indivikar/mateCounter/blob/main/fritzing/Display_7_Seg_Schema.png?raw=true)
