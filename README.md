
# 🚲 AAS-Workshop: Erstelle die Verwaltungsschalen für das e-Bike

In diesem Workshop erstellst du die Verwaltungsschalen (Asset Administration Shells, AAS) für die verschiedenen **Komponenten eines e-Bikes**. Du nutzt dafür das bereitgestellte Template und arbeitest im **AAS-Designer** unter [https://v1-designer.aas-suite.de/](https://v1-designer.aas-suite.de/).

![ebike](https://github.com/user-attachments/assets/cbe31a72-746f-411f-8391-8c1cd6797cb4)

---

## 📥 Vorbereitung

### 🔹 Was du brauchst

- Den **AAS-Designer** im Browser: [https://v1-designer.aas-suite.de/](https://v1-designer.aas-suite.de/)
- Logge dich mit den bereitgestellten Login-Daten (DIN A4 Blatt auf deinem Platz) ein
- Die Datei `ebike_template_aas.aasx` (bereitgestellt)
- Ein PDF-Handbuch je Bauteil (im Ordner Manuals)
- Diese Anleitung (`README_ebike_workshop.md`)

---

## ✅ Ziel der Übung

- Du importierst das Template und arbeitest mit der übergeordneten Verwaltungsschale **„ebike“** (bestehende AAS weiterverwenden!)
- Du erstellst eine eigene Verwaltungsschale **für jede e-Bike-Komponente**
- Du befüllst die Submodelle sauber mit sinnvollen, realistischen Werten

---

## 🧩 Die e-Bike-Komponenten

Für jede der folgenden Komponenten des e-Bikes erstellst du eine eigene Verwaltungsschale, basierend auf dem bereitgestellten **AAS-Template**:

1. **Rahmen** (Frame)
2. **Antrieb** (Drive Unit)
3. **Akku** (Battery)
4. **Reifen** (Tires)
5. **Bremsen** (Brakes)

---

## 🔧 Schritt-für-Schritt

### 1. Template importieren

- Öffne [https://v1-designer.aas-suite.de/](https://v1-designer.aas-suite.de/)
- Klicke auf **„Packages“** → **„Add“** → **„Upload existing packages“**
- Lade die Datei `ebike_template_aas.aasx` hoch. Darin ist die übergeordnete AAS **„ebike“** bereits enthalten.

**Wichtig:** Keine neue AAS über „Add“ → „Empty AAS“ erstellen, sondern mit der vorhandenen AAS arbeiten!

---

### 2. Für jede Komponente:

#### 🔹 AAS vom Template kopieren

- Wähle die bereits vorhandene AAS aus dem Template (z. B. die übergeordnete „ebike“-AAS)
- Klicke auf das Dreipunktemenü und wähle **„Copy“** aus, um eine Kopie der AAS für jede Komponente zu erstellen.
- **Benennung:** Wähle einen spezifischen Namen für jede Komponente (z. B. `Battery`, `Frame`, `DriveUnit`, `Tires`, `Brakes`)
- **Global Asset ID:** Eindeutig und sinnvoll benennen (z. B. `https://campus-schwarzwald.de/ids/shell/battery_001`)
- **Specific Asset ID:** Eine eigene Identifikationsnummer vergeben
- **Description:** Kurz und präzise (z. B. „Hydraulische Scheibenbremse vorne und hinten“)
- **Assetbild:** Bild der jeweiligen Komponente hochladen (PNG, JPG)

#### 🔹 Submodel „Nameplate“

Füge die folgenden Felder aus und fülle sie mit den entsprechenden Informationen. Beachte die tabellarische Übersicht, um die Felder für jede Komponente zu vervollständigen.

| **Feld**               | **Rahmen**                               | **Antrieb**                              | **Akku**                                 | **Reifen**                               | **Bremsen**                              |
|------------------------|------------------------------------------|------------------------------------------|------------------------------------------|------------------------------------------|------------------------------------------|
| **Seriennummer**        | `SN-EBIKE-2025-001`                      | `SN-EBIKE-2025-015`                      | `SN-EBIKE-2025-031`                      | `SN-EBIKE-2025-045`                      | `SN-EBIKE-2025-060`                      |
| **Herstellername**      | `Schwarzwald Bikes GmbH`                 | `E-Motion Systems`                       | `BatteryTech China Ltd.`                 | `Continental Reifen GmbH`                | `Shimano Brake Systems`                  |
| **Produktbezeichnung**  | `E-Bike Aluminium Rahmen X`              | `Bosch Performance Line Drive Unit`      | `LiFePO4 36V Akku, 500Wh`                | `Continental Contact Plus`               | `Shimano Deore Hydraulische Bremsen`     |
| **Baujahr**             | `2025`                                   | `2025`                                   | `2025`                                   | `2025`                                   | `2025`                                   |
| **Software-Version**    | `1.2.3`                                  | `2.1.5`                                  | `1.0.4`                                  | `N/A`                                    | `3.0.1`                                  |
| **Hardware-Version**    | `Rev. 5`                                 | `Rev. 8`                                 | `Rev. 2`                                 | `Rev. 4`                                 | `Rev. 3`                                 |
| **Firmware-Version**    | `FW-2025.04`                             | `FW-2025.06`                             | `FW-2025.01`                             | `N/A`                                    | `FW-2025.02`                             |
| **CE-Markierung**       | `✔️ (Konform gemäß EU-Richtlinien)`       | `✔️ (Konform gemäß EU-Richtlinien)`       | `✔️ (Konform gemäß EU-Richtlinien)`       | `✔️ (Konform gemäß EU-Richtlinien)`       | `✔️ (Konform gemäß EU-Richtlinien)`       |
| **Herkunftsland**       | `Deutschland`                            | `Deutschland`                            | `China`                                 | `Deutschland`                            | `Japan`                                  |

#### 🔹 Submodel „Handover Documentation“

- **User Manual hochladen** (PDF wird bereitgestellt)
- Trage Metadaten zum Dokument ein:
  - Sprache, Titel, Version, Status, Organisation, Datei-Name

#### 🔹 Submodel „Technical Data“

- Übernehme die technischen Eigenschaften aus dem Handbuch der jeweiligen Komponente.
- Füge neue Eigenschaften hinzu (Spannung, Leistung, Gewicht etc.):
  - **Dreipunktemenü → „Add“ → „Elements“ → „Property“**
  - Wähle den richtigen Datentyp (z. B. **Double** für Spannung: `14.3` V)
  - Ergänze die Einheit in der Data Definition

#### 🔹 Submodel „Carbon Footprint“

Trage die CO₂-Werte für jede Komponente ein. Die Werte für die Komponenten des e-Bikes sind:

| Komponente | Product Carbon Footprint (PCF) | Transport Carbon Footprint (TCF) |
|------------|-------------------------------|----------------------------------|
| **Rahmen** | 62,5 kg CO₂e                  | 5 kg CO₂e                        |
| **Antrieb**| 110 kg CO₂e                   | 10 kg CO₂e                       |
| **Akku**   | 250 kg CO₂e                   | 15 kg CO₂e                       |
| **Reifen** | 35 kg CO₂e                    | 3 kg CO₂e                        |
| **Bremsen**| 45 kg CO₂e                    | 4 kg CO₂e                        |

**Hinweis:** Das Pflichtfeld **„Quantity of measure for calculation“** muss ausgefüllt sein. Trage hier **„kg CO₂e per unit“** ein, da sich die Werte auf komplette Komponenten beziehen.

---

### 3. Speichern & Betrachten

- Speichere deine Verwaltungsschale mit einem sinnvollen Namen (z. B. `Battery_ebike`, `Frame_ebike`)
- Betrachte deine Verwaltungsschale, um sicherzustellen, dass alle Werte korrekt übernommen wurden

---

## 📁 Dateien im Repo

- `ebike_template_aas.aasx` – Ausgangstemplate
- `README_ebike_workshop.md` – Diese Anleitung
- `Manual_Frame.pdf`, `Manual_Battery.pdf`, ... – je Komponente

---

Viel Spaß beim Erstellen deiner digitalen Verwaltungsschale! Bei Fragen: einfach fragen :)
