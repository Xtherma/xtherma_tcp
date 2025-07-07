# Modbus_TCP

## 📡 Modbus TCP Mapping

Register-Dokumentation für Xtherma Wärmpepumpen.

###  Nutzung

Port: 502

Slave-ID: 1

Das optimale Pollingintervall beträgt >60 Sekunden. 


### 🔌 General System State (Einstellungen)

| Register | Description                                                | Mapping          | Value Range         |
|-------|------------------------------------------------------------|------------------|---------------------|
| 0     | 001 Wärmepumpe ein-/ausgeschaltet                              |                  | 0 = Aus, 1 = Ein    |
| 1     | 002 Betriebsmodus                                              |                  | 0=Standby, Heiz-, Kühl-, WW-Betrieb, 4=Automatik |
| 2     | 003 Warmwasser-Sofort-Funktion aktiviert                       |                  | 0 = Aus, 1 = Ein    |

### 🔥 Heizkurve 1 (Einstellungen)

| Register | Description                                                 | Mapping          | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 10    | 310 Heizkurve 1 aktiviert                                       |                  | 0 = Aus, 1 = Ein    |
| 11    | 311 Außentemperatur niedrig (P1)                                |                  | -20 bis 25°C        |
| 12    | 312 Außentemperatur hoch (P2)                                   |                  | -9 bis 25°C         |
| 13    | 315 Heiztemperatur hoch (P1)                                    |                  | 20 bis 75°C         |
| 14    | 316 Heiztemperatur niedrig (P2)                                 |                  | 20 bis 75°C         |
| 15    | 320 Konstante Heiztemperatur (Sollwert)                         |                  | 20 bis 75°C         |

### ❄️ Kühlkurve 1 (Einstellungen)

| Register | Description                                                 | Mapping         | Value Range         |
|-------|-------------------------------------------------------------|-----------------|---------------------|
| 20    | 350 Kühlkurve 1 aktiviert                                       |                 | 0 = Aus, 1 = Ein    |
| 21    | 351 Außentemperatur niedrig (P1)                                |                 | 16 bis 32°C         |
| 22    | 352 Außentemperatur hoch (P2)                                   |                 | 29 bis 37°C         |
| 23    | 355 Kühltemperatur hoch (P1)                                    |                 | 7 bis 30°C          |
| 24    | 356 Kühltemperatur niedrig (P2)                                 |                 | 7 bis 30°C          |
| 25    | 360 Konstante Kühltemperatur (Sollwert)                         |                 | 7 bis 30°C          |

### 🔥 Heizkurve 2 (Einstellungen)

| Register | Description                                                 | Mapping           | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 30    | 410 Heizkurve 2 aktiviert                                       |                  | 0 = Aus, 1 = Ein    |
| 31    | 411 Außentemperatur niedrig (P1)                                |                  | 16 bis 32°C         |
| 32    | 412 Außentemperatur hoch (P2)                                   |                  | 29 bis 37°C         |
| 33    | 415 Heiztemperatur hoch (P1)                                    |                  | 7 bis 30°C          |
| 34    | 416 Heiztemperatur niedrig (P2)                                 |                  | 7 bis 30°C          |
| 35    | 420 Konstante Heiztemperatur (Sollwert)                         |                  | 7 bis 30°C          |


### ❄️ Kühlkurve 2 (Einstellungen)

| Register | Description                                                 | Mapping          | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 40    | 450 Kühlkurve 2 aktiviert                                       |                  | 0 = Aus, 1 = Ein    |
| 41    | 451 Außentemperatur niedrig (P1)                                |                  | -20 bis 25°C        |
| 42    | 452 Außentemperatur hoch (P2)                                   |                  | -20 bis 25°C        |
| 43    | 455 Kühltemperatur hoch (P1)                                    |                  | 20 bis 75°C         |
| 44    | 456 Kühltemperatur niedrig (P2)                                 |                  | 20 bis 75°C         |
| 45    | 560 Konstante Kühltemperatur (Sollwert)                         |                  | 20 bis 75°C         |

### 🚿 Warmwasser (Einstellungen)

| Register | Description                                                 | Mapping          | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 50    | 501 Warmwasser Sollwert                                         |                  | 25 bis 75°C         |
| 51    | 522 Warmhalten Sollwert                                         |                  | 30 bis 55°C         |

### 🔌 Vernetzung

| Register | Description                                              | Mapping           | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 100   | Software Version                                            |                  | 240 = 2.40          |
| 101   | Betriebsmodus                                               |                  | Standby,Heizbetrieb,Kühlbetrieb,Warmwasser,Automatik |
| 102   | Anlage auf Grund Fehler gestoppt                            |                  | 1=kein Fehler, 0= Fehler    |
| 103   | §14a EnWG Status                                            |                  | 0 = Aus, 1 = Ein    |
| 104   | SG-Ready Status                                             |                  | 0 = Aus, 1 = Ein    |
| 105   | EVU Status                                                  |                  | 0 = Aus, 1 = Ein    |


### 🔥 Heizen Statuswerte

| Register | Description                                              | Mapping           | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 110   | Sollwert Heizbetrieb                                        |   Wert/10        |    -    °C |         
| 111   | Sollwert Heizen 1                                           |   Wert/10        |    -    °C |
| 112   | Sollwert Heizen 2                                           |   Wert/10        |    -    °C |
| 113   | Sollwert Kühlbetrieb                                        |   Wert/10        |    -    °C |
| 114   | Sollwert Kühlen 1                                           |   Wert/10        |    -    °C |
| 115   | Sollwert Kühlen 2                                           |   Wert/10        |    -    °C |
| 116   | Sollwert Warmwasserbereitung                                |   Wert/10        |    -    °C |

### 🔥 Heizen Regelwerte

| Register | Description                                              | Mapping           | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 120   | TK Heiz-/ Kühltemperatur                                    |   Wert/10        |    -    °C |
| 121   | TK1 Kreis 1 Temperatur                                      |   Wert/10        |    -    °C |
| 122   | TK2 Kreis 2 Temperatur                                      |   Wert/10        |    -    °C |
| 123   | TW Warmwassertemperatur                                     |   Wert/10        |    -    °C |


### 💧 Hydraulikkreis

| Register | Description                                              | Mapping           | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 130   | V -  Volumenstrom                                                |   Wert/10        |    -       |         
| 131   | PK - Umwälzpumpe eingeschaltet                                   |                  |    0 = Aus, 1 = Ein      |
| 132   | PK - Umwälzpumpe Leistung                                        |   Wert/10        |    0-100       |
| 133   | PK1 - Umwälzpumpe Kreis 1 eingeschaltet                          |                  |    0 = Aus, 1 = Ein      |
| 134   | PK2 - Umwälzpumpe Kreis 2 eingeschaltet                          |                  |    0 = Aus, 1 = Ein      |
| 135   | PWW - Zirkulationspumpe Warmwasser eingeschaltet                 |   Wert/10        |    0 = Aus, 1 = Ein      |
| 136   | VF - Verdichter Frequenz                                         |                  |    0-90 Hz   |
| 137   | LD1 - Lüfter 1 Drehzahl                                          |                  |    0-999 rpm  |
| 138   | LD2 - Lüfter 2 Drehzahl                                          |                  |    0-999 rpm  |


### 🌡️ Temperaturen

| Register | Description                                              | Mapping           | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 140   | TA -  Außentemperatur                                       |   Wert/10       |    -    °C |
| 141   | TA1 - Außentemperatur Mittelwert 1h                         |   Wert/10       |    -    °C |
| 142   | TA4   - Außentemperatur Mittelwert 4h                       |   Wert/10       |    -    °C |
| 143   | TA8 - Außentemperatur Mittelwert 8h                         |   Wert/10       |    -    °C |
| 144   | TA24 - Außentemperatur Mittelwert 24h                       |   Wert/10       |    -    °C |


### 🔌 Leistung

| Register | Description                                              | Mapping           | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 170   | Leistungsabgabe Wärmepumpe (thermisch)                      |   Wert*10         |    -   kW    |         
| 171   | Leistungsaufnahme Wärmepumpe (elektrisch) 	                |   Wert*10           |    -   kW    |         
| 172   | Leistungszahl Wärmepumpe                                    |   Wert/100           |    -   kW    |         
| 173   | Leistungszahl Gesamtsystem (inkl. Zusatzheizing)            |   Wert/100           |    -   kW    |         
| 174   | Leistungsabgabe Zusatz-/Notheizung (thermisch)              |   Wert*10           |    -   kW    |         
| 175   | Leistungsaufnahme Zusatz-/Notheizung (elektrisch)           |   Wert*10          |    -   kW    |         



### ⚡ Energie

| Register | Description                                              | Mapping           | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 180   | Tag Heizbetrieb thermische Leistungsabgabe                                                           |   Wert/100           |    - kW    |         
| 181   | Tag Heizbetrieb elektrische Leistungsaufnahme	                                                       |   Wert/100           |    - kW    |         
| 182   | Tag Kühlbetrieb thermische Leistungsabgabe                                                           |   Wert/100           |    - kW    |         
| 183   | Tag Kühlbetrieb elektrische Leistungsaufnahme                                                        |   Wert/100           |    - kW    |         
| 184   | Tag Warmwasserbetrieb thermische Leistungsabgabe                                                     |   Wert/100           |    - kW    |         
| 185   | Tag Warmwasserbetrieb elektrische Leistungsaufnahme                                                  |   Wert/100           |    - kW    |         
| 186   | Tag Heizbetrieb Zusatzheizung Stufe 1 (3 kW) thermische Leistungsabgabe                              |   Wert/100           |    - kW    |         
| 187   | Tag Heizbetrieb Zusatzheizung Stufe 1 (3 kW) elektrische Leistungsaufnahme                           |   Wert/100           |    - kW    |         
| 188   | Tag Warmwasserbetrieb Zusatzheizung Stufe 1 (3 kW) thermische Leistungsabgabe                        |   Wert/100           |    - kW    |         
| 189   | Tag Warmwasserbetrieb Zusatzheizung Stufe 1 (3 kW) elektrische Leistungsaufnahme                     |   Wert/100           |    - kW    |         
| 190   | Tag Heizbetrieb Zusatzheizung Stufe 2 (6 kW) thermische Leistungsabgabe                              |   Wert/100           |    - kW    |         
| 191   | Tag Heizbetrieb Zusatzheizung Stufe 2 (6 kW) elektrische Leistungsaufnahme                           |   Wert/100           |    - kW    |         
| 192   | Tag Warmwasserbetrieb Zusatzheizung Stufe 2 (6 kW) thermische Leistungsabgabe                        |   Wert/100           |    - kW    |         
| 193   | Tag Warmwasserbetrieb Zusatzheizung Stufe 2 (6 kW) elektrische Leistungsaufnahme	                   |   Wert/100           |    - kW    |         





