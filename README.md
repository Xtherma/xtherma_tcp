# Modbus_TCP

## 📡 Modbus TCP Mapping

Register-Dokumentation für Xtherma Wärmpepumpen.

### 🔌 General System State

| Register | Description                                                | Mapping          | Value Range         |
|-------|------------------------------------------------------------|------------------|---------------------|
| 0     | Wärmepumpe ein-/ausgeschaltet                              |                  | 0 = Aus, 1 = Ein    |
| 1     | Betriebsmodus                                              |                  | 0=Standby, Heiz-, Kühl-, WW-Betrieb, 4=Automatik |
| 2     | Warmwasser-Sofort-Funktion aktiviert                       |                  | 0 = Aus, 1 = Ein    |

### 🔥 Heizkurve 1 (Heating Curve 1)

| Register | Description                                                 | Mapping          | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 10    | Heizkurve 1 aktiviert                                       |                  | 0 = Aus, 1 = Ein    |
| 11    | Außentemperatur niedrig (P1)                                |                  | -20 bis 25°C        |
| 12    | Außentemperatur hoch (P2)                                   |                  | -9 bis 25°C         |
| 13    | Heiztemperatur hoch (P1)                                    |                  | 20 bis 75°C         |
| 14    | Heiztemperatur niedrig (P2)                                 |                  | 20 bis 75°C         |
| 15    | Konstante Heiztemperatur (Sollwert)                         |                  | 20 bis 75°C         |

### ❄️ Kühlkurve 1 (Cooling Curve 1)

| Register | Description                                                 | Mapping         | Value Range         |
|-------|-------------------------------------------------------------|-----------------|---------------------|
| 20    | Kühlkurve 1 aktiviert                                       |                 | 0 = Aus, 1 = Ein    |
| 21    | Außentemperatur niedrig (P1)                                |                 | 16 bis 32°C         |
| 22    | Außentemperatur hoch (P2)                                   |                 | 29 bis 37°C         |
| 23    | Kühltemperatur hoch (P1)                                    |                 | 7 bis 30°C          |
| 24    | Kühltemperatur niedrig (P2)                                 |                 | 7 bis 30°C          |
| 25    | Konstante Kühltemperatur (Sollwert)                         |                 | 7 bis 30°C          |

### 🔥 Heizkurve 2 (Heating Curve 2)

| Register | Description                                                 | Mapping           | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 30    | Heizkurve 2 aktiviert                                       |                  | 0 = Aus, 1 = Ein    |
| 31    | Außentemperatur niedrig (P1)                                |                  | 16 bis 32°C         |
| 32    | Außentemperatur hoch (P2)                                   |                  | 29 bis 37°C         |
| 33    | Heiztemperatur hoch (P1)                                    |                  | 7 bis 30°C          |
| 34    | Heiztemperatur niedrig (P2)                                 |                  | 7 bis 30°C          |
| 35    | Konstante Heiztemperatur (Sollwert)                         |                  | 7 bis 30°C          |
| 36    | Kühlkurve 2 aktiviert                                       |                  | 0 = Aus, 1 = Ein    |

### ❄️ Kühlkurve 2 (Cooling Curve 2)

| Register | Description                                                 | Mapping          | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 40    | Außentemperatur niedrig (P1)                                |                  | -20 bis 25°C        |
| 41    | Außentemperatur hoch (P2)                                   |                  | -20 bis 25°C        |
| 42    | Kühltemperatur hoch (P1)                                    |                  | 20 bis 75°C         |
| 43    | Kühltemperatur niedrig (P2)                                 |                  | 20 bis 75°C         |
| 44    | Konstante Kühltemperatur (Sollwert)                         |                  | 20 bis 75°C         |

### 🚿 Warmwasser (Hot Water)

| Register | Description                                                 | Mapping          | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 50    | Warmwasser Sollwert                                         |                  | 25 bis 75°C         |
| 51    | Warmhalten Sollwert                                         |                  | 30 bis 55°C         |

### 🔥 Heizkurve 2 (Heating Curve 2)

| Register | Description                                              | Mapping           | Value Range         |
|-------|-------------------------------------------------------------|------------------|---------------------|
| 100   | Software Version                                            |                  | 240 = 2.40          |
| 101   | Betriebsmodus                                               |                  |                     |
| 102   | Anlage auf Grund Fehler gestoppt                            |                  | 1=kein Fehler, 0= Fehler    |
| 103   | §14a EnWG Status                                            |                  | 0 = Aus, 1 = Ein    |
| 104   | SG-Ready Status                                             |                  | 0 = Aus, 1 = Ein    |
| 105   | EVU Status                                                  |                  | 0 = Aus, 1 = Ein    |

