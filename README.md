# 🚲 AAS-Workshop: Erstelle die Verwaltungsschalen für das e-Bike

In diesem Workshop erstellst du die Verwaltungsschalen (Asset Administration Shells, AAS) für die verschiedenen **Komponenten eines e-Bikes**. Du nutzt dafür das bereitgestellte Template und arbeitest im **AAS-Designer** unter [https://designer.aas-suite.de/](https://designer.aas-suite.de/).

![ebike](https://github.com/user-attachments/assets/cbe31a72-746f-411f-8391-8c1cd6797cb4)

---

## 📥 Vorbereitung

### 🔹 Was du brauchst

- Den **AAS-Designer** im Browser: [https://designer.aas-suite.de/](https://designer.aas-suite.de/)
- Login-Daten (auf dem DIN-A4-Blatt auf deinem Platz)
- Die Datei `ebike_template_aas.aasx`
- Ein PDF-Handbuch je Bauteil (im Ordner `Manuals`)
- Diese Anleitung (`README_ebike_workshop.md`)
- Du musst im Projekt-WLAN eingeloggt sein (`siehe Tafelanschrieb`)

---

## ✅ Ziel der Übung

- Importiere das Template und verwende die übergeordnete Verwaltungsschale **„ebike“** (nicht neu erstellen!)
- Erstelle für **jede e-Bike-Komponente** eine eigene Verwaltungsschale als Kopie
- Befülle die Submodelle sorgfältig mit sinnvollen, realistischen Werten

---

## 🧩 Die e-Bike-Komponenten

Für jede der folgenden Komponenten erstellst du eine eigene AAS:

1. **Rahmen** (Frame)
2. **Antrieb** (Drive Unit)
3. **Akku** (Battery)
4. **Reifen** (Tires)
5. **Bremsen** (Brakes)
6. Time Series (Live Daten Akku-SoC) -> wird nicht aus Template dupliziert

---

## 🔧 Schritt-für-Schritt

### 1. Template importieren

- Öffne den AAS-Designer: [https://designer.aas-suite.de/](https://designer.aas-suite.de/)
- Gehe zu **„Shells“** → **„Add“** → **„Upload existing packages“**
- Lade `ebike_template_aas.aasx` hoch (enthält die AAS **„ebike“** inkl. Template-Komponenten)
- Wähle **„Derived Import“**
- unter "Derivation" den bisherigen "Reference Type" löschen und neun Value eines Types auf Basis von "https://campus-schwarzwald.de" generieren lassen.
- Speichere die AAS

> ⚠️ Wichtig: **Keine neue AAS** über „Add“ → „Empty AAS“ erstellen!

---

### 2. Für jede Komponente:

#### 🔹 AAS aus Template kopieren & einfügen

- Wechsle zurück zur Übersicht **„Shells“**
- Wähle die AAS **„Template“** und öffne das **Dreipunkt-Menü** → **„Advanced“** → **„Duplicate“**
- Öffne die duplizierte AAS und passe sie wie im Folgenden beschrieben an

#### 🔹 AAS anpassen

- **ID:** Klicke auf **„Change AAS ID“**
- **IdShort:** z. B. `Battery`, `Frame`, `DriveUnit`, `Tires`, `Brakes`
- **Global Asset ID:** z. B. `https://campus-schwarzwald.de/ids/shell/battery_001` oder `genegrate IRI`
- **Description:** z. B. „Hydraulische Scheibenbremse vorne und hinten“
- **Default thumbnail:** Komponentenspezifisches Bild (PNG oder JPG) hochladen

> 🛑 **Specific Asset ID ist nicht mehr notwendig**, solange die Global Asset ID gesetzt ist.

---

### 3. Submodel „Nameplate“

Befülle folgende Felder je Komponente:

| **Feld**               | **Rahmen**                               | **Antrieb**                              | **Akku**                                 | **Reifen**                               | **Bremsen**                              |
|------------------------|------------------------------------------|------------------------------------------|------------------------------------------|------------------------------------------|------------------------------------------|
| Seriennummer           | `SN-EBIKE-2025-001`                      | `SN-EBIKE-2025-015`                      | `SN-EBIKE-2025-031`                      | `SN-EBIKE-2025-045`                      | `SN-EBIKE-2025-060`                      |
| Herstellername         | `Schwarzwald Bikes GmbH`                 | `Bosch`               | `BatteryTech China Ltd.`                 | `Continental Reifen GmbH`                | `Shimano Brake Systems`                  |
| Produktbezeichnung     | `E-Bike Aluminium Rahmen X`              | `Bosch Performance Line Drive Unit`      | `LiFePO4 36V Akku, 500Wh`                | `Continental Contact Plus`               | `Shimano Deore Hydraulische Bremsen`     |
| Baujahr                | `2025`                                   | `2025`                                   | `2025`                                   | `2025`                                   | `2025`                                   |
| Software-Version       | `N/A`                                    | `2.1.5`                                  | `1.0.4`                                  | `N/A`                                    | `N/A`                                  |
| Hardware-Version       | `Rev. 5`                                 | `Rev. 8`                                 | `Rev. 2`                                 | `Rev. 4`                                 | `Rev. 3`                                 |
| Firmware-Version       | `N/A`                                    | `FW-2025.06`                             | `FW-2025.01`                             | `N/A`                                    | `N/A`                             |
| CE-Markierung          | `✔️ (Konform gemäß EU-Richtlinien)`      | `✔️ (Konform gemäß EU-Richtlinien)`       | `✔️ (Konform gemäß EU-Richtlinien)`       | `✔️ (Konform gemäß EU-Richtlinien)`       | `✔️ (Konform gemäß EU-Richtlinien)`       |
| Herkunftsland          | `Deutschland`                            | `Deutschland`                            | `China`                                  | `Deutschland`                            | `Japan`                                  |

> 📌 Hinweis: Das Feld **Produktbezeichnung** entspricht im Submodel dem Eintrag **„ManufacturerProductDesignation“**.

---

### 4. Submodel „Handover Documentation“

- Lade das passende **User Manual (PDF)** hoch
- Trage Metadaten ein:
  - Sprache, Titel, Version, Status, Organisation, Datei-Name

---

### 5. Submodel „Technical Data“

- Übertrage technische Eigenschaften aus dem Handbuch
- Neue Eigenschaften hinzufügen (im SMC "Technical Properties"):
  - Dreipunktemenü → **Add → Elements → Property**
  - Wähle den Datentyp passend (z. B. **Double** für Spannung: `14.3 V`)
  - Ergänze die Einheit über die Data Definition

> 📝 **Hinweis:** Eigenschaften findest du im PDF-Handbuch der jeweiligen Komponente unter dem Abschnitt *Technische Daten*.

> 💡 Falls Zeitdruck besteht: Du kannst ggf. einige Properties weglassen.

---

### 6. Submodel „Carbon Footprint“

Trage die folgenden CO₂-Werte ein:

| Komponente | PCF (kg CO₂e) | TCF (kg CO₂e) |
|------------|----------------|----------------|
| Rahmen     | 62,5           | 5              |
| Antrieb    | 110            | 10             |
| Akku       | 250            | 15             |
| Reifen     | 35             | 3              |
| Bremsen    | 45             | 4              |

Pflichtfeld **„Quantity of measure for calculation“**:  
→ **`kg CO₂e per unit`**

---

# 7. Submodel „Time Series Data“ mit Node-RED-Dashboard

In diesem Schritt ergänzt du deine eBike-Verwaltungsschale um ein vereinfachtes Submodell für Zeitreihendaten.
Die Messwerte werden dabei nicht direkt in der AAS gespeichert. Stattdessen beschreibt die AAS, welche Zeitreihe existiert und wo diese extern abgerufen und visualisiert werden kann.

Die eigentlichen Live- und Historiendaten werden über eine vorbereitete Node-RED-Simulation bereitgestellt.

### Ziel
Du sollst verstehen, dass eine Verwaltungsschale nicht zwingend alle Daten selbst enthalten muss. Sie kann auch auf externe Datenquellen verweisen, zum Beispiel auf eine API oder ein Dashboard.

### Submodel anlegen
Lege in deiner eBike-AAS ein neues Submodel an:

| Feld | Wert |
| :--- | :--- |
| **idShort** | TimeSeriesData |
| **Description** | Vereinfachtes Submodell zur Beschreibung von Zeitreihendaten des E-Bikes. |

---

### Properties hinzufügen
Füge im Submodel **TimeSeriesData** folgende Properties hinzu:

| Property | Datentyp | Wert |
| :--- | :--- | :--- |
| **ObservedProperty** | String | State of Charge |
| **ValueName** | String | soc_percent |
| **Unit** | String | % |
| **SamplingInterval** | String | 1 s |
| **DataSourceType** | String | external |
| **PayloadFormat** | String | application/json |
| **EndpointCurrentValue** | String | http://10.100.10.108:1880/ebike/soc |
| **EndpointTimeSeries** | String | http://10.100.10.108:1880/ebike/soc/history |
| **DashboardUrl** | String | http://10.100.10.108:1880/ui |

**Hinweis:** Die Endpunkte wurden auf die Ziel-IP **10.100.10.108** angepasst. Du kannst das Dashboard direkt über die angegebene `DashboardUrl` in deinem Browser aufrufen.


### 8. Speichern & Prüfen

- Speichere jede AAS sinnvoll benannt ab (z. B. `Battery_ebike`)
- Prüfe, ob alle Werte korrekt und vollständig sind

---

## 📁 Dateien im Repo

- `ebike_template_aas.aasx` – Ausgangstemplate
- `README_ebike_workshop.md` – Diese Anleitung
- `Manual_Frame.pdf`, `Manual_Battery.pdf`, … – Handbücher je Komponente

---

Viel Erfolg & Spaß beim digitalen Zwilling! Bei Fragen einfach fragen 😊
