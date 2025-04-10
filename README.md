# 🚲 AAS-Workshop: Erstelle die Verwaltungsschalen für das e-Bike

In diesem Workshop erstellst du die Verwaltungsschalen (Asset Administration Shells, AAS) für die verschiedenen **Komponenten eines e-Bikes**. Du nutzt dafür das bereitgestellte Template und arbeitest im **AAS-Designer** unter [https://v1-designer.aas-suite.de/](https://v1-designer.aas-suite.de/).

![ebike](https://github.com/user-attachments/assets/cbe31a72-746f-411f-8391-8c1cd6797cb4)

---

## 📥 Vorbereitung

### 🔹 Was du brauchst

- Den **AAS-Designer** im Browser: [https://v1-designer.aas-suite.de/](https://v1-designer.aas-suite.de/)
- Login-Daten (auf dem DIN-A4-Blatt auf deinem Platz)
- Die Datei `ebike_template_aas.aasx`
- Ein PDF-Handbuch je Bauteil (im Ordner `Manuals`)
- Diese Anleitung (`README_ebike_workshop.md`)

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

---

## 🔧 Schritt-für-Schritt

### 1. Template importieren

- Öffne den AAS-Designer: [https://v1-designer.aas-suite.de/](https://v1-designer.aas-suite.de/)
- Gehe zu **„Packages“** → **„Add“** → **„Upload existing packages“**
- Lade `ebike_template_aas.aasx` hoch (enthält die AAS **„ebike“** inkl. Template-Komponenten)

> ⚠️ Wichtig: **Keine neue AAS** über „Add“ → „Empty AAS“ erstellen!

---

### 2. Für jede Komponente:

#### 🔹 AAS aus Template kopieren & einfügen

- Wähle die AAS **„Template“** innerhalb der übergeordneten AAS **„AssetAdministrationShell“** aus
- Öffne das **Dreipunkt-Menü** → **„Copy“**
- Wechsle zur „AssetAdministrationShell“ → Dreipunkt-Menü → **„Paste“ → „Paste as copy“**

#### 🔹 AAS anpassen

- **ID:** Klicke auf **„generate IRI“**
- **IdShort:** z. B. `Battery`, `Frame`, `DriveUnit`, `Tires`, `Brakes`
- **Global Asset ID:** z. B. `https://campus-schwarzwald.de/ids/shell/battery_001`
- **Description:** z. B. „Hydraulische Scheibenbremse vorne und hinten“
- **Default thumbnail:** Komponentenspezifisches Bild (PNG oder JPG) hochladen

> 🛑 **Specific Asset ID ist nicht mehr notwendig**, solange die Global Asset ID gesetzt ist.

---

### 3. Submodel „Nameplate“

Befülle folgende Felder je Komponente (leicht angepasst für mehr Realitätsnähe):

| **Feld**               | **Rahmen**                               | **Antrieb**                              | **Akku**                                 | **Reifen**                               | **Bremsen**                              |
|------------------------|------------------------------------------|------------------------------------------|------------------------------------------|------------------------------------------|------------------------------------------|
| Seriennummer           | `SN-EBIKE-2025-001`                      | `SN-EBIKE-2025-015`                      | `SN-EBIKE-2025-031`                      | `SN-EBIKE-2025-045`                      | `SN-EBIKE-2025-060`                      |
| Herstellername         | `Schwarzwald Bikes GmbH`                 | `E-Motion Systems / Bosch`               | `BatteryTech China Ltd.`                 | `Continental Reifen GmbH`                | `Shimano Brake Systems`                  |
| Produktbezeichnung     | `E-Bike Aluminium Rahmen X`              | `Bosch Performance Line Drive Unit`      | `LiFePO4 36V Akku, 500Wh`                | `Continental Contact Plus`               | `Shimano Deore Hydraulische Bremsen`     |
| Baujahr                | `2025`                                   | `2025`                                   | `2025`                                   | `2025`                                   | `2025`                                   |
| Software-Version       | `1.2.3`                                  | `2.1.5`                                  | `1.0.4`                                  | `N/A`                                    | `3.0.1`                                  |
| Hardware-Version       | `Rev. 5`                                 | `Rev. 8`                                 | `Rev. 2`                                 | `Rev. 4`                                 | `Rev. 3`                                 |
| Firmware-Version       | `FW-2025.04`                             | `FW-2025.06`                             | `FW-2025.01`                             | `N/A`                                    | `FW-2025.02`                             |
| CE-Markierung          | `✔️ (Konform gemäß EU-Richtlinien)`       | `✔️ (Konform gemäß EU-Richtlinien)`       | `✔️ (Konform gemäß EU-Richtlinien)`       | `✔️ (Konform gemäß EU-Richtlinien)`       | `✔️ (Konform gemäß EU-Richtlinien)`       |
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
- Neue Eigenschaften hinzufügen:
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

### 7. Speichern & Prüfen

- Speichere jede AAS sinnvoll benannt ab (z. B. `Battery_ebike`)
- Prüfe, ob alle Werte korrekt und vollständig sind

---

## 📁 Dateien im Repo

- `ebike_template_aas.aasx` – Ausgangstemplate
- `README_ebike_workshop.md` – Diese Anleitung
- `Manual_Frame.pdf`, `Manual_Battery.pdf`, … – Handbücher je Komponente

---

Viel Erfolg & Spaß beim digitalen Zwilling! Bei Fragen einfach fragen 😊
