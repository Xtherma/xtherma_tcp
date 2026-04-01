# Modbus_TCP

## 📡 Modbus TCP Mapping

Register-Dokumentation für Xtherma Wärmepumpen.

### Nutzung

- **Rechte:** Block 0-99: Lesen & Schreiben (je alle 1 min; ausgenommen 0, 1, 2, 60, 65 nur alle 30 min), Block 100 - 199 nur lesen
- **Register-Arten:** Alle Register sind 16Bit Holding Register. 
- **Port:** 502  
- **Slave-ID:** 1  
- **Optimales Pollingintervall:** >60 Sekunden  

---
### Changelog

21.07.2025: Schreibrechte für Einstellungen (0-99)<br>
14.07.2025: Ergänzen SG-Ready (60 - 63) und EnWG §14a (65)<br>
01.04.2026: Dokumentation ergänzt

---

## 🔌 General System State (Einstellungen)

| Register | Nummer | Description | Value Range | Wertetyp / Parsing |
|----------|--------|------------|-------------|--------------------|
| 0 | 001 | Wärmepumpe ein-/ausgeschaltet | | u16 (bool: 0=Aus, 1=Ein) |
| 1 | 002 | Betriebsmodus | | u16 (enum: 0=Standby,1=Heizen,2=Kühlen,3=WW,4=Auto) |
| 2 | 003 | Warmwasser-Sofort-Funktion | | u16 (bool) |

---

## 🔥 Heizkurve 1

| Register | Nummer | Description | Value Range | Unit | Wertetyp / Parsing |
|----------|--------|------------|-------------|------|--------------------|
| 10 | 310 | Aktiv | | | u16 (bool) |
| 11 | 311 | Außentemperatur P1 | -20..25 | °C | s16 |
| 12 | 312 | Außentemperatur P2 | -9..25 | °C | s16 |
| 13 | 315 | Heiztemp P1 | 20..75 | °C | u16 |
| 14 | 316 | Heiztemp P2 | 20..75 | °C | u16 |
| 15 | 320 | Konstant Soll | 20..75 | °C | u16 |

---

## ❄️ Kühlkurve 1

| Register | Nummer | Description | Value Range | Unit | Wertetyp / Parsing |
|----------|--------|------------|-------------|------|--------------------|
| 20 | 350 | Aktiv | | | u16 (bool) |
| 21 | 351 | Außentemperatur P1 | 16..32 | °C | u16 |
| 22 | 352 | Außentemperatur P2 | 29..45 | °C | u16 |
| 23 | 355 | Kühltemp P1 | 7..30 | °C | u16 |
| 24 | 356 | Kühltemp P2 | 7..30 | °C | u16 |
| 25 | 360 | Konstant Soll | 7..30 | °C | u16 |

---

## 🔥 Heizkurve 2

| Register | Nummer | Description | Value Range | Unit | Wertetyp / Parsing |
|----------|--------|------------|-------------|------|--------------------|
| 30 | 410 | Aktiv | | | u16 (bool) |
| 31 | 411 | Außentemperatur P1 | -20..25 | °C | s16 |
| 32 | 412 | Außentemperatur P2 | -9..25 | °C | s16 |
| 33 | 415 | Heiztemp P1 | 20..75 | °C | u16 |
| 34 | 416 | Heiztemp P2 | 20..75 | °C | u16 |
| 35 | 420 | Konstant Soll | 20..75 | °C | u16 |

---

## ❄️ Kühlkurve 2

| Register | Nummer | Description | Value Range | Unit | Wertetyp / Parsing |
|----------|--------|------------|-------------|------|--------------------|
| 40 | 450 | Aktiv | | | u16 (bool) |
| 41 | 451 | Außentemperatur P1 | 16..32 | °C | u16 |
| 42 | 452 | Außentemperatur P2 | 29..45 | °C | u16 |
| 43 | 455 | Kühltemp P1 | 7..30 | °C | u16 |
| 44 | 456 | Kühltemp P2 | 7..30 | °C | u16 |
| 45 | 560 | Konstant Soll | 7..30 | °C | u16 |

---

## 🚿 Warmwasser

| Register | Nummer | Description | Value Range | Unit | Wertetyp / Parsing |
|----------|--------|------------|-------------|------|--------------------|
| 50 | 501 | Sollwert | 25..75 | °C | u16 |
| 51 | 522 | Warmhalten | 30..55 | °C | u16 |

---

## ⚡ Vernetzung

| Register | Nummer | Description | Value Range | Unit | Wertetyp / Parsing |
|----------|--------|------------|-------------|------|--------------------|
| 60 | 815 | SG Ready Modus | | | u16 (enum: 0–3) |
| 61 | 811 | ΔT Heizen | 0..30 | K | u16 |
| 62 | 812 | ΔT WW | 0..30 | K | u16 |
| 63 | 813 | ΔT Kühlen | 0..30 | K | u16 |
| 65 | 808 | §14a aktiv | | | u16 (bool) |

---

## ⚡ Überschuss

| Register | Nummer | Description | Value Range | Unit | Wertetyp / Parsing |
|----------|--------|------------|-------------|------|--------------------|
| 70 | - | Aktiv | | | u16 (bool) |
| 71 | - | Überschuss | 0..100000 | W | u16 |

---

## 🔌 Betriebswerte

| Register | Key | Description | Value Range | Unit | Wertetyp / Parsing |
|----------|-----|------------|-------------|------|--------------------|
| 100 | controller_v | Version | | | u16 |
| 101 | mode | Modus | | | u16 (enum) |
| 102 | error | Fehlerstatus | | | u16 (bool inverted) |
| 103 | 14a | Status | | | u16 (bool) |
| 104 | sg | SG Status | | | u16 (enum) |
| 105 | evu | EVU | | | u16 (bool) |

---

## 🔥 Sollwerte

| Register | Key | Description | Unit | Wertetyp / Parsing |
|----------|-----|------------|------|--------------------|
| 110 | h_target | Heizen | °C | s16 /10 |
| 111 | h1_target | Heizen 1 | °C | s16 /10 |
| 112 | h2_target | Heizen 2 | °C | s16 /10 |
| 113 | c_target | Kühlen | °C | s16 /10 |
| 114 | c1_target | Kühlen 1 | °C | s16 /10 |
| 115 | c2_target | Kühlen 2 | °C | s16 /10 |
| 116 | hw_target | Warmwasser | °C | u16 |

---

## 🌡️ Fühlerwerte

| Register | Key | Description | Unit | Wertetyp / Parsing |
|----------|-----|------------|------|--------------------|
| 120 | tk | TK | °C | s16 /10 |
| 121 | tk1 | TK1 | °C | s16 /10 |
| 122 | tk2 | TK2 | °C | s16 /10 |
| 123 | tw | TW | °C | s16 /10 |
| 124 | tr | TR | °C | s16 /10 |
| 125 | trl | TRL | °C | s16 /10 |
| 126 | tvl | TVL | °C | s16 /10 |

---

## 💧 Pumpen / Aktoren

| Register | Key | Description | Unit | Wertetyp / Parsing |
|----------|-----|------------|------|--------------------|
| 130 | v | Volumenstrom | l/min | u16 /10 |
| 131 | pk | Pumpe | | u16 (bool) |
| 132 | pkl | Leistung | % | u16 /10 |
| 133 | pk1 | Kreis 1 | | u16 (bool) |
| 134 | pk2 | Kreis 2 | | u16 (bool) |
| 135 | pww | WW Pumpe | | u16 (bool) |
| 136 | vf | Verdichter | Hz | u16 |
| 137 | ld1 | Lüfter 1 | rpm | u16 |
| 138 | ld2 | Lüfter 2 | rpm | u16 |

---

## 🌡️ Außentemperaturen

| Register | Key | Description | Unit | Wertetyp / Parsing |
|----------|-----|------------|------|--------------------|
| 140 | ta | TA | °C | s16 /10 |
| 141 | ta1 | TA1 | °C | s16 /10 |
| 142 | ta4 | TA4 | °C | s16 /10 |
| 143 | ta8 | TA8 | °C | s16 /10 |
| 144 | ta24 | TA24 | °C | s16 /10 |

---

## 🔌 Leistung

| Register | Key | Description | Unit | Wertetyp / Parsing |
|----------|-----|------------|------|--------------------|
| 170 | out_hp | thermisch | W | u16 *10 |
| 171 | in_hp | elektrisch | W | u16 *10 |
| 172 | efficiency_hp | COP | | u16 /100 |
| 173 | efficiency_total | COP gesamt | | u16 /100 |
| 174 | out_backup | thermisch | W | u16 *10 |
| 175 | in_backup | elektrisch | W | u16 *10 |
| 176 | out_total | thermisch | W | u16 *10 |
| 177 | in_total | elektrisch | W | u16 *10 |

---

## ⚡ Tageswerte

| Register | Key | Description | Unit | Wertetyp / Parsing |
|----------|-----|------------|------|--------------------|
| 180 | day_hp_out_h | Heizen thermisch | kWh | u16 /100 |
| 181 | day_hp_in_h | Heizen elektrisch | kWh | u16 /100 |
| 182 | day_hp_out_c | Kühlen thermisch | kWh | u16 /100 |
| 183 | day_hp_in_c | Kühlen elektrisch | kWh | u16 /100 |
| 184 | day_hp_out_hw | WW thermisch | kWh | u16 /100 |
| 185 | day_hp_in_hw | WW elektrisch | kWh | u16 /100 |
| 186 | day_backup3_out_h | Backup 3kW thermisch | kWh | u16 /100 |
| 187 | day_backup3_in_h | Backup 3kW elektrisch | kWh | u16 /100 |
| 188 | day_backup3_out_hw | Backup WW thermisch | kWh | u16 /100 |
| 189 | day_backup3_in_hw | Backup WW elektrisch | kWh | u16 /100 |
| 190 | day_backup6_out_h | Backup 6kW thermisch | kWh | u16 /100 |
| 191 | day_backup6_in_h | Backup 6kW elektrisch | kWh | u16 /100 |
| 192 | day_backup6_out_hw | Backup WW thermisch | kWh | u16 /100 |
| 193 | day_backup6_in_hw | Backup WW elektrisch | kWh | u16 /100 |

