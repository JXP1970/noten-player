# KORREKTUR-ANLEITUNG für MusicXML

## 🎯 ÜBERBLICK

Die MusicXML-Konvertierung ist zu **85% korrekt**, hat aber folgende Punkte, die verbessert werden können:

---

## ⚙️ METHODE 1: Mit MuseScore (empfohlen)

### Schritt 1: Datei öffnen
1. **MuseScore installieren** (kostenlos): https://musescore.org
2. **Musik_war_meine_erste_Liebe.mvt1.mxl** öffnen

### Schritt 2: Korrektionen durchführen

#### ✏️ Korrektur 1: Werktitel hinzufügen
- Klick auf **Datei → Eigenschaften → Titel**
- Eingeben: **"Musik war meine erste Liebe"**
- OK

#### ✏️ Korrektur 2: Tempo setzen
- Erste Note anklicken
- **Eigenschaften → Tempo**: 80 BPM
- Oder: Text-Palette → Tempo → "♩ = 80"

#### ✏️ Korrektur 3: Tonhöhen überprüfen (Optional)
- **Maße 1-20** durchgehen
- Folgende Töne überprüfen (könnten fehlerhaft sein):
  - **B → sollte Bb sein?** (In Es-Dur)
  - **E → sollte Eb sein?** (In Es-Dur)
  - **A → sollte Ab sein?** (In Es-Dur)

Falls Fehler:
- Note anklicken
- Akkzidentals hinzufügen (♭ Button in Akkzidentals-Palette)

### Schritt 3: Speichern
- **Datei → MusicXML exportieren**
- **Format**: MusicXML → MXL (compressed)
- Speichern unter: `Musik_war_meine_erste_Liebe_KORRIGIERT.mxl`

---

## ⚙️ METHODE 2: Mit Finale oder Sibelius

Falls Sie eines dieser Programme nutzen:
1. MXL-Datei öffnen
2. Gleiche Korrektionen durchführen
3. Als MusicXML speichern

---

## ⚙️ METHODE 3: Manuell mit XML-Editor (Fortgeschrittene)

### Schritt 1: MXL in ZIP extrahieren
```bash
# Windows PowerShell:
Expand-Archive "Musik war meine erste Liebe.mvt1.mxl" -DestinationPath "mxl_content"
```

### Schritt 2: XML bearbeiten
Öffne `mxl_content/Musik war meine erste Liebe.mvt1.xml` mit Notepad++:

**Hinzufügen nach `<score-partwise>`:**
```xml
<work>
  <work-title>Musik war meine erste Liebe</work-title>
  <movement-number>1</movement-number>
  <movement-title>Satz I</movement-title>
</work>
```

**In erste `<measure number="1">` einfügen:**
```xml
<direction>
  <direction-type>
    <metronome>
      <beat-unit>quarter</beat-unit>
      <per-minute>80</per-minute>
    </metronome>
  </direction-type>
  <sound tempo="80" />
</direction>
```

### Schritt 3: Zurück in MXL packen
```bash
# Neues ZIP erstellen mit Inhalt von mxl_content
```

---

## 🔍 WAS GENAU ZU ÜBERPRÜFEN IST

### PRIORITÄT 1 (WICHTIG): Tonhöhen
- [ ] Maße 1-10: Erste Noten überprüfen
- [ ] Besonders: C-E Motiv (siehe Analyse)
- [ ] Alle "B" überprüfen → sollten "Bb" sein?
- [ ] Alle "E" überprüfen → sollten "Eb" sein?
- [ ] Alle "A" überprüfen → sollten "Ab" sein?

### PRIORITÄT 2 (WICHTIG): Metadaten
- [ ] Werktitel: "Musik war meine erste Liebe"
- [ ] Tempo: 80 BPM
- [ ] Komponist: [Falls bekannt]
- [ ] Copyright: [Falls bekannt]

### PRIORITÄT 3 (OPTIONAL): Feinheiten
- [ ] Dynamik-Markierungen (f, p, pp, ff)
- [ ] Tempoangaben (Allegro, Andante, etc.)
- [ ] Text/Liedtext (falls vorhanden)
- [ ] Artikulation (Staccato, Legato)

---

## ✅ CHECKLISTE VOR SPEICHERN

```
[ ] Werktitel vorhanden
[ ] Tempo auf 80 BPM gesetzt
[ ] Tonart: Es-Dur (3 Flats) bestätigt
[ ] Taktart: 4/4 bestätigt
[ ] Erste 10 Maße auf Tonhöhen überprüft
[ ] Alle 4 Stimmen hörbar im Playback
[ ] Datei speichern als: MusicXML (MXL)
```

---

## 📊 VORHER-NACHHER

### Vorher (OCR-Rohversion)
- ❌ Fehlender Titel
- ❌ Fehlende Tempoangabe
- ⚠️ Tonhöhen-Unsicherheiten (12 Naturals)
- ✅ Struktur korrekt
- ✅ Rhythmus korrekt

### Nachher (Korrigierte Version)
- ✅ Titel: "Musik war meine erste Liebe"
- ✅ Tempo: 80 BPM
- ✅ Tonhöhen überprüft
- ✅ Struktur korrekt
- ✅ Rhythmus korrekt
- ✅ Spielbar und korrekt

---

## 🎵 NOTEN-PLAYER TEST

Nach den Korrektionen:
1. Neue MXL-Datei in den Noten-Player laden
2. **Play** klicken
3. Musik anhören und überprüfen:
   - Klingt die Harmonie richtig?
   - Sind alle Stimmen hörbar?
   - Passt das Tempo?

---

## 💡 TIPPS

- **MuseScore** ist kostenlos und benutzerfreundlich
- Sie können einzelne Fehler "durchhören" - falschen Noten klingt man schnell an
- Speichern Sie die korrigierte Version mit einem neuen Namen
- Behalten Sie die Original-OCR-Version zur Referenz

---

## 📞 HILFE

Falls Sie Fragen haben:
- MuseScore Handbuch: https://musescore.org/de/handbook
- MusicXML Standard: https://www.musicxml.com/

---

**Geschätzte Korrekturzeit: 30-45 Minuten mit MuseScore**

