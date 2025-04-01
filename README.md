# aas

# 🛠 Anleitung zur Befüllung der Verwaltungsschalen für das e-Bike

Diese Anleitung beschreibt, wie du als Study eine Asset Administration Shell (AAS) für ein e-Bike und dessen Komponenten erstellst und befüllst. Die Datenstruktur basiert auf der AASX-Datei `ebike_template_void.aasx`.

---

## 🔍 Struktur der Verwaltungsschale (AAS)

Die Verwaltungsschale ist hierarchisch aufgebaut:

1. **Asset (Niveau 0):** Das gesamte e-Bike
2. **Submodelle (Niveau 1):** Verschiedene Aspekte wie "Digital Nameplate" oder "Technical Data"
3. **Submodel-Elemente (Niveau 2):** Konkrete Datenfelder innerhalb der Submodelle

---

## 🧩 Komponenten und ihre Submodelle

| Komponente | Submodelle |
|------------|-------------|
| Rahmen     | Digital Nameplate, HandoverDocumentation, Technical Data, CarbonFootprint |
| Antrieb    | Digital Nameplate, HandoverDocumentation, Technical Data, TimeSeries, CarbonFootprint |
| Akku       | Digital Nameplate, HandoverDocumentation, Technical Data, TimeSeries, CarbonFootprint |
| Reifen     | Digital Nameplate, HandoverDocumentation, Technical Data, CarbonFootprint |
| Bremsen    | Digital Nameplate, HandoverDocumentation, Technical Data, CarbonFootprint |

---

## 📦 Allgemeine Befüllung je Submodell

### 1. Digital Nameplate
- URIOfTheProduct
- ManufacturerName
- ManufacturerProductDesignation
- ContactInformation
- OrderCodeOfManufacturer
- ProductArticleNumberOfManufacturer
- SerialNumber

### 2. HandoverDocumentation
- UserManual (PDF-Datei)
- numberOfDocuments
- Language, Version, StatusValue, StatusSetDate, OrganizationName, etc.

### 3. Technical Data
- GeneralInformation
- ProductImage
- ManufacturerLogo
- ProductDimensions
- PackagingDimension
- MediaSupply

### 4. TimeSeries *(nur für Antrieb & Akku)*
- Zeitreihen wie z. B. Temperatur oder Ladezyklen
- (Noch manuell einfügen als TechnicalProperty)

### 5. CarbonFootprint
- Ein einfacher numerischer Wert z. B. "62,5"

---

## 🧱 Schritt-für-Schritt je Komponente

### 🔹 Rahmen
- **Beschreibung:** Aluminiumrahmen mit integrierten Leuchten
- **SerialNumber:** 10131
- Submodelle: alle vier

### 🔹 Antrieb
- **Beschreibung:** 500-Watt Hinterradnabenmotor
- **SerialNumber:** 10132
- Zusätzlich mit TimeSeries

### 🔹 Akku
- **Beschreibung:** 48V, 15Ah Lithium-Ionen-Akku, entnehmbar
- **SerialNumber:** 10133
- Mit TimeSeries + hohem CarbonFootprint (z. B. "250 kg")

### 🔹 Reifen
- **Beschreibung:** High-End Offroad Bereifung
- **SerialNumbers:** 10134, 10135

### 🔹 Bremsen
- **Beschreibung:** Hydraulische Scheibenbremsen vorne und hinten
- **SerialNumbers:** 10136, 10137

---

## 💡 Tipps für den AASX Package Explorer

1. **Asset hinzufügen:** Für jede Komponente ein Asset anlegen
2. **Submodell wählen:** Digital Nameplate, Technical Data etc.
3. **Submodel-Elemente einfügen:** Werte eingeben oder Dateien hochladen
4. **Dateien:** PDFs, Bilder etc. über den Typ "File" hochladen
5. **Speichern:** Regelmäßig sichern und am Ende als `.aasx` exportieren

---

## 📁 Dateien im Repo

- `ebike_template_void.aasx` → Vorlage
- `README.md` → Diese Anleitung

---

Bei Fragen: Gerne im Team oder bei der Lehrperson melden – viel Erfolg beim Ausprobieren!


---

## 🖥 Anleitung für den AAS-Designer (https://designer.aas-suite.com/)

Der AAS-Designer ist ein webbasiertes Tool zur Erstellung und Bearbeitung von Verwaltungsschalen. So nutzt du ihn in der Übung:

### 🔑 Einstieg

1. Rufe [https://designer.aas-suite.com/](https://designer.aas-suite.com/) im Browser auf.
2. Klicke auf **"Open Project"** und lade die Datei `ebike_template_void.aasx` hoch.

### 🧱 Verwaltungsschale bearbeiten

1. **Verwaltungsschale auswählen:** Klicke auf die Kachel des gewünschten Assets (z. B. "Rahmen").
2. **Submodell hinzufügen:** Nutze das Pluszeichen ➕ neben "Submodels".
3. **Submodel-Elemente bearbeiten:** Klicke auf ein Submodell → dann auf "Add Submodel Element".
4. **Felder befüllen:** Gib die Werte laut Anleitung oben ein.

### 📎 Dateien hochladen

- Elemente vom Typ **File** (z. B. Bedienungsanleitungen, Bilder) kannst du direkt über das Dateiauswahlfenster hochladen.
- Achte auf sinnvolle Benennung und Dateiformate (z. B. PDF, PNG, JPG).

### 💾 Speichern & Exportieren

- Nach dem Bearbeiten klicke oben rechts auf **"Export"** → wähle **"AASX"**, um deine Version zu speichern.
- Datei lokal sichern oder ins Repository hochladen.

---

## ☑️ Empfohlene Vorgehensweise

1. Projekt in den Designer laden
2. Schritt für Schritt die Komponenten befüllen
3. Zwischenspeichern nicht vergessen!
4. Zum Schluss alles exportieren

---

Viel Spaß beim Arbeiten mit dem AAS-Designer!
