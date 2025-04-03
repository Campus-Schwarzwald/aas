# Aufgaben Tobi:
- Screenshots einfügen von AAS-Suite
- Einmal komplett durchspielen lassen von JH
- Studi-User anlegen

# 🚲 AAS-Workshop: Erstelle die Verwaltungsschalen für das e-Bike

In diesem Workshop erstellst du die Verwaltungsschalen (Asset Administration Shells, AAS) für die verschiedenen **Komponenten eines e-Bikes**. Du nutzt dafür das bereitgestellte Template und arbeitest im **AAS-Designer** unter [https://v1-designer.aas-suite.de/].

![ebike](https://github.com/user-attachments/assets/cbe31a72-746f-411f-8391-8c1cd6797cb4)

---

## 📥 Vorbereitung

### 🔹 Was du brauchst

- Den **AAS-Designer** im Browser: [https://v1-designer.aas-suite.de/] (https://designer.aas-suite.com)
- Logge dich mit den bereitgestellten Login-Daten (DIN A4 Blatt auf deinem Platz) ein
- Die Datei `ebike_template_aas.aasx` (bereitgestellt)
- Ein PDF-Handbuch je Bauteil (wird von der Lehrperson bereitgestellt)
- Diese Anleitung (`README_ebike_workshop.md`)

---

## ✅ Ziel der Übung

- Du importierst das Template und arbeitest mit der übergeordneten Verwaltungsschale **„ebike“** (bestehende AAS weiterverwenden!)
- Du erstellst eine eigene Verwaltungsschale **für jede e-Bike-Komponente**
- Du befüllst die Submodelle sauber mit sinnvollen, realistischen Werten

---

## 🧩 Die e-Bike-Komponenten

Du erstellst eine eigene Verwaltungsschale für:

1. **Rahmen** (Frame)
2. **Antrieb** (Drive Unit)
3. **Akku** (Battery)
4. **Reifen** (Tires)
5. **Bremsen** (Brakes)

---

## 🔧 Schritt-für-Schritt

### 1. Template importieren

- Öffne [https://v1-designer.aas-suite.de/]
- Klicke auf **„Packages“** → **„Add“** → **„Upload existing packages“**
- Lade die Datei `ebike_template_aas.aasx` hoch. Darin ist die übergeordnete AAS **„ebike“** bereits enthalten

**Wichtig:** Keine neue AAS über „Add“ → „Empty AAS“ erstellen, sondern mit der vorhandenen AAS arbeiten!

### 2. Pro Komponente:

#### 🔹 AAS erstellen
- Öffne das Dreipunktemenü und erstelle eine neue Verwaltungsschale (AAS)
- **Benennung:** z. B. `Battery`, `Frame`, etc.
- **Global Asset ID:** Eindeutig und sinnvoll benennen (z. B. `https://campus-schwarzwald.de/ids/shell/battery_001`)
- **Specific Asset ID:** Eine eigene Identifikationsnummer vergeben
- **Description:** Kurz und präzise (z. B. „Hydraulische Scheibenbremse vorne und hinten“)
- **Assetbild:** Bild der Komponente hochladen (PNG, JPG)

#### 🔹 Submodel „Nameplate“
- Füge alle Felder einmalig aus:
  - **Seriennummer:** `SN-EBIKE-2025-001`
  - **Herstellername:** `Schwarzwald Bikes GmbH`
  - **Produktbezeichnung:** `E-Bike Modell X`
  - **Baujahr:** `2025`
  - **Software-Version:** `1.2.3`
  - **Hardware-Version:** `Rev. 4`
  - **Firmware-Version:** `FW-2025.04`
  - **CE-Markierung:** `✔️ (Konform gemäß EU-Richtlinien)`
  - **Herkunftsland:** `Deutschland`

#### 🔹 Submodel „Handover Documentation“
- **User Manual hochladen** (PDF wird bereitgestellt)
- Trage Metadaten zum Dokument ein:
  - Sprache, Titel, Version, Status, Organisation, Datei-Name

#### 🔹 Submodel „Technical Data“
- Technische Eigenschaften aus dem Manual übernehmen
- Neue Eigenschaften (Spannung, Leistung, Gewicht etc.) hinzufügen:
  - **Dreipunktemenü → „Add“ → „Elements“ → „Property“**
  - Datentyp korrekt wählen (z. B. **Double** für Spannung: `14.3` V)
  - Einheit in der Data Definition ergänzen

#### 🔹 Submodel „Carbon Footprint“
- Trage folgende CO₂-Werte ein:

| Komponente | Product Carbon Footprint (PCF) | Transport Carbon Footprint (TCF) |
|------------|-------------------------------|------------------------------|
| Rahmen     | 62,5 kg CO₂e                  | 5 kg CO₂e                    |
| Antrieb    | 110 kg CO₂e                   | 10 kg CO₂e                   |
| Akku       | 250 kg CO₂e                   | 15 kg CO₂e                   |
| Reifen     | 35 kg CO₂e                    | 3 kg CO₂e                    |
| Bremsen    | 45 kg CO₂e                    | 4 kg CO₂e                    |

**Hinweis:** Das Pflichtfeld **„Quantity of measure for calculation“** muss ausgefüllt sein. Trage hier **„kg CO₂e per unit“** ein, da sich die Werte auf komplette Komponenten beziehen.

---

## 💾 Speichern & Betrachten

- Speichere deine Verwaltungsschale entsprechend ab (Name_ebike)
- Betrachte deine Verwaltungsschale

---

## 📁 Dateien im Repo

- `ebike_template_aas.aasx` – Ausgangstemplate
- `README_ebike_workshop.md` – Diese Anleitung
- `Manual_Frame.pdf`, `Manual_Battery.pdf`, ... – je Komponente

---

Viel Spaß beim Erstellen deiner digitalen Verwaltungsschale! Bei Fragen: einfach fragen :)
