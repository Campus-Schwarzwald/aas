# 🚲 AAS-Workshop: Erstelle die Verwaltungsschalen für das e-Bike

In diesem Workshop erstellst du als Study die Verwaltungsschalen (Asset Administration Shells, AAS) für die verschiedenen **Komponenten eines e-Bikes**. Du nutzt dafür das bereitgestellte Template und arbeitest im **AAS-Designer** unter [https://designer.aas-suite.com](https://designer.aas-suite.com).

---

## 📥 Vorbereitung

### 🔹 Was du brauchst

- Den **AAS-Designer** im Browser: [https://designer.aas-suite.com]  https://v1-designer.aas-suite.de/ (https://designer.aas-suite.com)
- Die Datei `ebike_template_void.aasx` (bereitgestellt)
- Ein PDF-Handbuch je Bauteil (wird von der Lehrperson bereitgestellt)
- Diese Anleitung (`README_ebike_workshop.md`)

---

## ✅ Ziel der Übung

- Du importierst das Template und arbeitest mit der übergeordneten Verwaltungsschale **„ebike“**
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

- Öffne [https://designer.aas-suite.com](https://designer.aas-suite.com)
- Klicke auf **„Open Project“**
- Lade die Datei `ebike_template_void.aasx` hoch. Du findest darin bereits die übergeordnete AAS mit dem Namen **„ebike“**.

### 2. Pro Komponente:

#### 🔹 AAS erstellen
- Erstelle eine neue Verwaltungsschale (AAS)
- **Benennung:** z. B. `Battery`, `Frame`, etc.
- **ID:** Eindeutig und sinnvoll benennen (z. B. `https://campus-schwarzwald.de/ids/shell/battery_001`)
- **Description:** Kurz und präzise (z. B. „Hydraulische Scheibenbremse vorne und hinten“)
- **Assetbild:** Bild der Komponente hochladen (PNG, JPG)

#### 🔹 Submodel „Nameplate“
- Füge alle Felder einmalig aus:
  - Seriennummer
  - Herstellernamen
  - Produktbezeichnung
  - Baujahr, Software-/Hardware-/Firmware-Versionen
  - CE-Markierung, Herkunftsland

#### 🔹 Submodel „Handover Documentation“
- **User Manual hochladen** (PDF wird bereitgestellt)
- Trage Metadaten zum Dokument ein:
  - Sprache, Titel, Version, Status, Organisation, Datei-Name

#### 🔹 Submodel „Technical Data“
- Technische Eigenschaften aus dem Manual übernehmen
- Trage Maße, Gewicht, Spannung, Leistung etc. unter „Technical Properties“ ein
- Optional: Produktbild, Herstellerlogo

#### 🔹 Submodel „Carbon Footprint“
- Trage folgende CO₂-Werte ein:

| Komponente | Product Carbon Footprint (PCF) | Total Carbon Footprint (TCF) |
|------------|-------------------------------|------------------------------|
| Rahmen     | 62,5 kg CO₂e                  | 70 kg CO₂e                   |
| Antrieb    | 110 kg CO₂e                   | 125 kg CO₂e                  |
| Akku       | 250 kg CO₂e                   | 265 kg CO₂e                  |
| Reifen     | 35 kg CO₂e                    | 40 kg CO₂e                   |
| Bremsen    | 45 kg CO₂e                    | 50 kg CO₂e                   |

---

## 💾 Speichern & Abgabe

- Klicke auf **Export** > **AASX**
- Benenne deine Datei eindeutig (z. B. `battery_studentname.aasx`)
- Abgabe erfolgt laut Ansage (Moodle, Mail, USB, etc.)

---

## 📁 Dateien im Repo

- `ebike_template_void.aasx` – Ausgangstemplate
- `README_ebike_workshop.md` – Diese Anleitung
- `Manual_Frame.pdf`, `Manual_Battery.pdf`, ... – je Komponente

---

Viel Spaß beim Erstellen deiner digitalen Verwaltungsschale! Bei Fragen: einfach fragen :)
