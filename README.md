# Modbus_TCP

## 📡 Modbus TCP Mapping

Register-Dokumentation für Xtherma Wärmepumpen.

### Nutzung

- **Rechte:** Block 0-99: Lesen & Schreiben (je alle 30 min), Block 100 - 199 nur lesen
- **Port:** 502  
- **Slave-ID:** 1  
- **Optimales Pollingintervall:** >60 Sekunden  

---
### Changelog

21.07.2025: Schreibrechte für Einstellungen (0-99)
14.07.2025: Ergänzen SG-Ready (60 - 63) und EnWG §14a (65)

---

### 🔌 General System State (Einstellungen)

| Register | Nummer | Description                                | Mapping                                            | Value Range |
|----------|--------|--------------------------------------------|----------------------------------------------------|-------------|
| 0        | 001    | Wärmepumpe ein-/ausgeschaltet              | 0 = Aus, 1 = Ein                                   |             |
| 1        | 002    | Betriebsmodus                              | 0 = Standby, 1 = Heizbetrieb, 2 = Kühlbetrieb, 3 = WW-Betrieb, 4 = Automatik |             |
| 2        | 003    | Warmwasser-Sofort-Funktion aktiviert       | 0 = Aus, 1 = Ein                                   |             |

---

### 🔥 Heizkurve 1 (Einstellungen)

| Register | Nummer | Description                          | Mapping           | Value Range | Unit |
|----------|--------|--------------------------------------|-------------------|-------------|------|
| 10       | 310    | Heizkurve 1 aktiviert                | 0 = Aus, 1 = Ein  |             |      |
| 11       | 311    | Außentemperatur niedrig (P1)         |                   | -20 bis 25  | °C   |
| 12       | 312    | Außentemperatur hoch (P2)            |                   | -9 bis 25   | °C   |
| 13       | 315    | Heiztemperatur hoch (P1)             |                   | 20 bis 75   | °C   |
| 14       | 316    | Heiztemperatur niedrig (P2)          |                   | 20 bis 75   | °C   |
| 15       | 320    | Konstante Heiztemperatur (Sollwert)  |                   | 20 bis 75   | °C   |

---

### ❄️ Kühlkurve 1 (Einstellungen)

| Register | Nummer | Description                          | Mapping           | Value Range | Unit |
|----------|--------|--------------------------------------|-------------------|-------------|------|
| 20       | 350    | Kühlkurve 1 aktiviert                | 0 = Aus, 1 = Ein  |             |      |
| 21       | 351    | Außentemperatur niedrig (P1)         |                   | 16 bis 32   | °C   |
| 22       | 352    | Außentemperatur hoch (P2)            |                   | 29 bis 45   | °C   |
| 23       | 355    | Kühltemperatur hoch (P1)             |                   | 7 bis 30    | °C   |
| 24       | 356    | Kühltemperatur niedrig (P2)          |                   | 7 bis 30    | °C   |
| 25       | 360    | Konstante Kühltemperatur (Sollwert)  |                   | 7 bis 30    | °C   |

---

### 🔥 Heizkurve 2 (Einstellungen)

| Register | Nummer | Description                          | Mapping           | Value Range | Unit |
|----------|--------|--------------------------------------|-------------------|-------------|------|
| 30       | 410    | Heizkurve 2 aktiviert                | 0 = Aus, 1 = Ein  |             |      |
| 31       | 411    | Außentemperatur niedrig (P1)         |                   | -20 bis 25  | °C   |
| 32       | 412    | Außentemperatur hoch (P2)            |                   | -9 bis 25   | °C   |
| 33       | 415    | Heiztemperatur hoch (P1)             |                   | 20 bis 75   | °C   |
| 34       | 416    | Heiztemperatur niedrig (P2)          |                   | 20 bis 75   | °C   |
| 35       | 420    | Konstante Heiztemperatur (Sollwert)  |                   | 20 bis 75   | °C   |

---

### ❄️ Kühlkurve 2 (Einstellungen)

| Register | Nummer | Description                          | Mapping           | Value Range | Unit |
|----------|--------|--------------------------------------|-------------------|-------------|------|
| 40       | 450    | Kühlkurve 2 aktiviert                | 0 = Aus, 1 = Ein  |             |      |
| 41       | 451    | Außentemperatur niedrig (P1)         |                   | 16 bis 32   | °C   |
| 42       | 452    | Außentemperatur hoch (P2)            |                   | 29 bis 45   | °C   |
| 43       | 455    | Kühltemperatur hoch (P1)             |                   | 7 bis 30    | °C   |
| 44       | 456    | Kühltemperatur niedrig (P2)          |                   | 7 bis 30    | °C   |
| 45       | 560    | Konstante Kühltemperatur (Sollwert)  |                   | 7 bis 30    | °C   |

---

### 🚿 Warmwasser (Einstellungen)

| Register | Nummer | Description                 | Mapping | Value Range | Unit |
|----------|--------|-----------------------------|---------|-------------|------|
| 50       | 501    | Warmwasser Sollwert         |         | 25 bis 75   | °C   |
| 51       | 522    | Warmhalten Sollwert         |         | 30 bis 55   | °C   |

---

### ⚡ Vernetzung

| Register | Nummer | Description                 | Mapping | Value Range | Unit |
|----------|--------|-----------------------------|---------|-------------|------|
| 60       | -      | SG-Ready aktivieren                            | 0 = Kein Eingriff, 1 = Normalbetrieb 2 = Sperre, 3 = Temperaturen anheben | -   | -   |
| 61       | 811    | SG Ready Heiztemperatur anheben um (ΔT)        |         | 0 bis 30   | K   |
| 62       | 812    | SG Ready Warmwassertemperatur anheben um (ΔT)  |         | 0 bis 30   | K   |
| 63       | 813    | SG Ready Kühltemperatur senken um (ΔT)         |         | 0 bis 30   | K   |
| 65       | -      | §14a EnWG manuell aktivieren                   | 0 = Aus, 1 = Ein  |  |      |

---

### ⚡ Überschuss-Regelung (beta-Version)

| Register | Nummer | Description                 | Mapping | Value Range | Unit |
|----------|--------|-----------------------------|---------|-------------|------|
| 70       | -    | Überschuss-Regelung aktivieren                              | 0 = Deaktiviert, 1 = Aktiviert| -   | -   |
| 71       | -    | Verfügbarer Überschuss        |         | 0 bis 100.000   | W   |



---


### 🔌 Allgemeines (Betriebswerte)

| Register | Key  | Description                               | Mapping                                                                   | Value Range | Unit |
|----------|------|-------------------------------------------|----------------------------------------------------------------------------|-------------|------|
| 100      | controller_v | Software Version                          | 240 = 2.40                                                            |             |      |
| 101      | mode         | Betriebsmodus                             | 1 = Standby, 2 = Heizbetrieb, 3 = Kühlbetrieb, 4 = Warmwasser         |             |      |
| 102      | error     | Anlage auf Grund Fehler gestoppt          | 1 = kein Fehler, 0 = Fehler                                              |             |      |
| 103      | 14a     | §14a EnWG Status                          | 0 = Aus, 1 = Ein                                                           |             |      |
| 104      | sg     | SG-Ready Status                           | 0 = Aus, 1 = Normal, 2 = Sperre, 3 = Temperaturen anheben, 4 = Anlaufbefehl |             |      |
| 105      | evu     | EVU Status                                | 0 = Aus, 1 = Ein                                                           |             |      |

Hinweis: Error berücksichtigt folgende Meldungen: P16, F20, S14, S13, S05, S08, F01, F02, F03, F04, F05, F06, F07, F08, F10, F11, F12, P11, E01, E02, E03, E04, E05, E06, E07, E08.

---

### 🔥 Sollwerte (Betriebswerte)
Die Sollwerte berücksichtigen die zum aktuellen Zeitpunkt vorliegende Sollwerte, welche z.B. durch SG-Ready beeinflusst werden können.

| Register | Key  | Description                        | Mapping     | Value Range | Unit |
|----------|------|------------------------------------|-------------|-------------|------|
| 110      | h_target     | Sollwert Heizbetrieb               | Wert / 10   |             | °C   |
| 111      | h1_target     | Sollwert Heizen 1                  | Wert / 10   |             | °C   |
| 112      | h2_target     | Sollwert Heizen 2                  | Wert / 10   |             | °C   |
| 113      | c_target     | Sollwert Kühlbetrieb               | Wert / 10   |             | °C   |
| 114      | c1_target     | Sollwert Kühlen 1                  | Wert / 10   |             | °C   |
| 115      | c2_target     | Sollwert Kühlen 2                  | Wert / 10   |             | °C   |
| 116      | hw_target     | Sollwert Warmwasserbereitung      | Wert   |             | °C   |

---

### 🌡️ Fühlerwerte (Betriebswerte)
Die Fühlerwerte sind die anliegenden Temperaturfühler der Wärmepumpe.

| Register | Key  | Description                      | Mapping   | Value Range | Unit |
|----------|------|----------------------------------|-----------|-------------|------|
| 120      | tk   | TK Heiz-/Kühltemperatur          | Wert / 10 |             | °C   |
| 121      | tk1  | TK1 Kreis 1 Temperatur           | Wert / 10 |             | °C   |
| 122      | tk1  | TK2 Kreis 2 Temperatur           | Wert / 10 |             | °C   |
| 123      | tw   | TW Warmwassertemperatur          | Wert / 10 |             | °C   |
| 124      | tr   | TR Raumtemperatur                | Wert / 10 |             | °C   |
| 125      | trl  | TRL Rücklauftemperatur           | Wert / 10 |             | °C   |
| 126      | tvl  | TVL Vorlauftemperatur            | Wert / 10 |             | °C   |

---

### 💧 Pumpen und Aktoren (Betriebswerte)

| Register | Key  | Description                                      | Mapping           | Value Range   | Unit   |
|----------|------|--------------------------------------------------|-------------------|----------------|--------|
| 130      | v    | V - Volumenstrom                                 | Wert / 10         |                | l/min  |
| 131      | pk   | PK - Umwälzpumpe eingeschaltet                   |                   | 0 = Aus, 1 = Ein |       |
| 132      | pkl  | PK - Umwälzpumpe Leistung                        | Wert / 10         | 0 – 100        | %      |
| 133      | pk1  | PK1 - Umwälzpumpe Kreis 1 eingeschaltet          | 0 = Aus, 1 = Ein  |                |        |
| 134      | pk2  | PK2 - Umwälzpumpe Kreis 2 eingeschaltet          | 0 = Aus, 1 = Ein  |                |        |
| 135      | pww  | PWW - Zirkulationspumpe Warmwasser eingeschaltet | 0 = Aus, 1 = Ein  |                |        |
| 136      | vf   | VF - Verdichterfrequenz                          |                   | 0 – 90         | Hz     |
| 137      | ld1  | LD1 - Lüfter 1 Drehzahl                          |                   | 0 – 999        | rpm    |
| 138      | ld2  | LD2 - Lüfter 2 Drehzahl                          |                   | 0 – 999        | rpm    |
---

### 🌡️ Außentemperaturen (Betriebswerte)

| Register | Key  | Description                           | Mapping     | Value Range | Unit |
|----------|------|---------------------------------------|-------------|-------------|------|
| 140      | ta   | TA - Außentemperatur                  | Wert / 10   |             | °C   |
| 141      | ta1  | TA1 - Außentemperatur Mittelwert 1h   | Wert / 10   |             | °C   |
| 142      | ta4  | TA4 - Außentemperatur Mittelwert 4h   | Wert / 10   |             | °C   |
| 143      | ta8  | TA8 - Außentemperatur Mittelwert 8h   | Wert / 10   |             | °C   |
| 144      | ta24 | TA24 - Außentemperatur Mittelwert 24h | Wert / 10   |             | °C   |

---

### 🔌 Leistung Live (Betriebswerte)

| Register | Key  | Description                                          | Mapping     | Value Range | Unit |
|----------|------|------------------------------------------------------|-------------|-------------|------|
| 170      | out_hp | Leistungsabgabe Wärmepumpe (thermisch)              | Wert * 10   |             | W   |
| 171      | in_hp  | Leistungsaufnahme Wärmepumpe (elektrisch)           | Wert * 10   |             | W   |
| 172      | efficiency_hp     | Leistungszahl Wärmepumpe                            | Wert / 100  |             | –    |
| 173      | efficiency_total  | Leistungszahl Gesamtsystem (inkl. Zusatzheizung)    | Wert / 100  |             | –    |
| 174      | out_backup        | Leistungsabgabe Zusatz-/Notheizung (thermisch)      | Wert * 10   |             | W   |
| 175      | in_backup         | Leistungsaufnahme Zusatz-/Notheizung (elektrisch)   | Wert * 10   |             | W   |
| 176      | out_total        | Leistungsabgabe Gesamtsystem (thermisch)      | Wert * 10   |             | W   |
| 177      | in_total         | Leistungsaufnahme Gesamtsystem (elektrisch)   | Wert * 10   |             | W   |

---

### ⚡ Tag Energiewerte (Betriebswerte)

| Register | Key  | Description                                                          | Mapping     | Value Range | Unit |
|----------|------|----------------------------------------------------------------------|-------------|-------------|------|
| 180      | day_hp_out_h     | Tag Heizbetrieb thermische Leistungsabgabe                           | Wert / 100  |             | kWh  |
| 181      | day_hp_in_h    | Tag Heizbetrieb elektrische Leistungsaufnahme                        | Wert / 100  |             | kWh  |
| 182      | day_hp_out_c     | Tag Kühlbetrieb thermische Leistungsabgabe                           | Wert / 100  |             | kWh  |
| 183      | day_hp_in_c     | Tag Kühlbetrieb elektrische Leistungsaufnahme                        | Wert / 100  |             | kWh  |
| 184      | day_hp_out_hw     | Tag Warmwasserbetrieb thermische Leistungsabgabe                     | Wert / 100  |             | kWh  |
| 185      | day_hp_in_hw     | Tag Warmwasserbetrieb elektrische Leistungsaufnahme                  | Wert / 100  |             | kWh  |
| 186      | day_backup3_out_h     | Tag Heizbetrieb Zusatzheizung Stufe 1 (3 kW) therm. Leistungsabgabe  | Wert / 100  |             | kWh  |
| 187      | day_backup3_in_h     | Tag Heizbetrieb Zusatzheizung Stufe 1 (3 kW) elektr. Leistungsaufnahme | Wert / 100  |             | kWh  |
| 188      | day_backup3_out_hw     | Tag WW-Betrieb Zusatzheizung Stufe 1 (3 kW) therm. Leistungsabgabe   | Wert / 100  |             | kWh  |
| 189      | day_backup3_in_hw     | Tag WW-Betrieb Zusatzheizung Stufe 1 (3 kW) elektr. Leistungsaufnahme | Wert / 100  |             | kWh  |
| 190      | day_backup6_out_h     | Tag Heizbetrieb Zusatzheizung Stufe 2 (6 kW) therm. Leistungsabgabe  | Wert / 100  |             | kWh  |
| 191      | day_backup6_in_h     | Tag Heizbetrieb Zusatzheizung Stufe 2 (6 kW) elektr. Leistungsaufnahme | Wert / 100 |             | kWh  |
| 192      | day_backup6_out_hw     | Tag WW-Betrieb Zusatzheizung Stufe 2 (6 kW) therm. Leistungsabgabe   | Wert / 100  |             | kWh  |
| 193      | day_backup6_in_hw     | Tag WW-Betrieb Zusatzheizung Stufe 2 (6 kW) elektr. Leistungsaufnahme | Wert / 100  |             | kWh  |

