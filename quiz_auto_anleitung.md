# 🚀 Quiz-App - Automatische Version

## So funktioniert es:

Diese Version lädt **automatisch** die JSON-Datei aus dem gleichen Ordner - **ohne Upload-Button**!

---

## ✅ Schnellstart:

### Schritt 1: Dateien vorbereiten
Legen Sie beide Dateien in den **gleichen Ordner**:
- `quiz_app_auto.html`
- `quiz_fragen.json`

### Schritt 2: HTML öffnen
Öffnen Sie `quiz_app_auto.html` im Browser → Das Quiz startet automatisch!

**Fertig!** 🎉

---

## 📂 Mehrere Quizze verwenden:

### Option 1: Standard-Datei umbenennen
Die App sucht automatisch nach `quiz_fragen.json`

**Ihre Quiz-Dateien:**
- `quiz_python.json`
- `quiz_netzwerke.json`
- `quiz_html.json`

**Zum Nutzen:** Benennen Sie die gewünschte Datei in `quiz_fragen.json` um

### Option 2: URL-Parameter (Empfohlen!)
Öffnen Sie die HTML-Datei mit einem Parameter:

```
quiz_app_auto.html?file=quiz_python.json
quiz_app_auto.html?file=quiz_netzwerke.json
quiz_app_auto.html?file=quiz_html.json
```

**Vorteile:**
- ✅ Keine Umbenennungen nötig
- ✅ Alle Quiz-Dateien behalten ihren Namen
- ✅ Schneller Wechsel zwischen Quizzen

---

## 💻 Mehrere HTML-Dateien erstellen:

Noch einfacher: Erstellen Sie für jedes Quiz eine eigene HTML-Datei!

### Kopieren Sie die HTML-Datei:
- `quiz_python.html` → lädt `quiz_python.json`
- `quiz_netzwerke.html` → lädt `quiz_netzwerke.json`
- `quiz_html.html` → lädt `quiz_html.json`

### Ändern Sie nur EINE Zeile:
Öffnen Sie die HTML-Datei und suchen Sie (ca. Zeile 312):

```javascript
const fileToLoad = fileParam || 'quiz_fragen.json';
```

Ändern Sie zu:
```javascript
const fileToLoad = fileParam || 'quiz_python.json';
```

**Fertig!** Jetzt lädt diese HTML-Datei automatisch `quiz_python.json`

---

## 📁 Empfohlene Ordnerstruktur:

```
Informatik-Quiz/
├── quiz_app_auto.html          (Haupt-Version)
├── quiz_python.html            (Spezielle Version für Python)
├── quiz_netzwerke.html         (Spezielle Version für Netzwerke)
│
├── quiz_fragen.json            (Standard)
├── quiz_python.json            (Python-Fragen)
├── quiz_netzwerke.json         (Netzwerk-Fragen)
├── quiz_html.json              (HTML-Fragen)
└── quiz_datenbanken.json       (SQL-Fragen)
```

---

## 🎓 Für den Unterricht:

### Variante A: Beamer-Präsentation
1. Öffnen Sie `quiz_app_auto.html?file=quiz_python.json`
2. Projizieren Sie das Quiz
3. Schüler rufen Antworten

### Variante B: Schüler arbeiten selbst
1. Geben Sie Schülern den Ordner mit allen Dateien
2. Schüler öffnen die entsprechende HTML-Datei
3. Quiz läuft automatisch

### Variante C: Online bereitstellen
1. Laden Sie alle Dateien auf einen Webserver hoch
2. Verlinken Sie: `https://ihre-website.ch/quiz_python.html`
3. Schüler können direkt im Browser arbeiten

---

## ⚠️ Häufige Probleme:

### Problem 1: "Quiz konnte nicht geladen werden"
**Lösung:**
- Prüfen Sie, ob die JSON-Datei im gleichen Ordner liegt
- Prüfen Sie die Schreibweise (Gross-/Kleinschreibung!)
- Öffnen Sie die JSON-Datei und prüfen Sie auf Fehler

### Problem 2: Datei wird nicht gefunden
**Lösung:**
- Beide Dateien müssen im **gleichen Ordner** sein
- Öffnen Sie die HTML-Datei direkt (nicht über Drag & Drop)

### Problem 3: JSON-Fehler
**Lösung:**
- Validieren Sie Ihr JSON auf https://jsonlint.com
- Prüfen Sie Kommas, Anführungszeichen, Klammern

---

## 💡 Tipps:

1. **Benennung:** Verwenden Sie aussagekräftige Namen wie `quiz_python_schleifen.json`
2. **Backup:** Kopieren Sie funktionierende JSON-Dateien vor Änderungen
3. **Testen:** Öffnen Sie neue Quiz-Dateien immer erst im Browser zum Testen
4. **Organisation:** Erstellen Sie einen Ordner pro Thema oder Klasse

---

## 🔗 URL-Parameter - Alle Möglichkeiten:

```
# Standard (lädt quiz_fragen.json)
quiz_app_auto.html

# Spezifische Datei laden
quiz_app_auto.html?file=quiz_python.json

# Datei in Unterordner
quiz_app_auto.html?file=python/schleifen.json

# Andere Dateien im gleichen Ordner
quiz_app_auto.html?file=quiz_netzwerke.json
quiz_app_auto.html?file=quiz_html_basics.json
quiz_app_auto.html?file=quiz_datenbanken_sql.json
```

---

## 🚀 Beispiel-Setup für Ihre Schule:

### Szenario: Sie unterrichten Python in 3 Klassen

**Dateien:**
```
quiz_app_auto.html
quiz_3p_python.json
quiz_4g_python.json
quiz_4h_python.json
```

**Links für Schüler:**
- Klasse 3p: `quiz_app_auto.html?file=quiz_3p_python.json`
- Klasse 4g: `quiz_app_auto.html?file=quiz_4g_python.json`
- Klasse 4h: `quiz_app_auto.html?file=quiz_4h_python.json`

Sie können diese Links sogar in Moodle oder Teams einfügen!

---

## ✅ Vorteile der automatischen Version:

- ✅ Keine Buttons - einfach öffnen und starten
- ✅ Perfekt für Schüler - keine Verwirrung
- ✅ Schneller Wechsel zwischen verschiedenen Quizzen
- ✅ Kann online gehostet werden
- ✅ Links können geteilt werden

---

Viel Erfolg mit Ihren Quizzen! 🎉
