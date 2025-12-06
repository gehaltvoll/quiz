# 📝 JSON-Format Anleitung

## Das ist JSON! ✅

JSON = **J**ava**S**cript **O**bject **N**otation

## Wie Sie das JSON bearbeiten:

### Schritt 1: JSON-Datei öffnen
Öffnen Sie `quiz_fragen.json` oder `quiz_template_leer.json` mit einem Texteditor:
- **Windows:** Notepad, Notepad++, VS Code
- **Mac:** TextEdit, VS Code
- **Online:** jsoneditoronline.org

### Schritt 2: Struktur verstehen

```json
{
  "title": "Ihr Quiz-Titel",
  "subtitle": "Ihre Beschreibung",
  "questions": [
    {
      "id": 1,
      "question": "Ihre Frage?",
      "answers": [
        { "text": "Antwort A", "correct": false },
        { "text": "Antwort B", "correct": true },
        { "text": "Antwort C", "correct": false },
        { "text": "Antwort D", "correct": false }
      ],
      "explanation": "Erklärung hier"
    }
  ]
}
```

## ✅ Wichtige JSON-Regeln:

### 1. **Anführungszeichen**
```json
"title": "Mein Quiz"  ✅ Richtig (doppelte Anführungszeichen)
'title': 'Mein Quiz'  ❌ Falsch (einfache nicht erlaubt)
title: "Mein Quiz"    ❌ Falsch (Schlüssel braucht auch "")
```

### 2. **Kommas**
```json
{
  "id": 1,              ✅ Komma nach jedem Eintrag
  "question": "..."     ✅ KEIN Komma beim letzten Eintrag
}
```

```json
"answers": [
  { "text": "A", "correct": false },   ✅ Komma
  { "text": "B", "correct": true }     ✅ Kein Komma beim letzten
]
```

### 3. **Wahrheitswerte**
```json
"correct": true   ✅ Richtig (kleingeschrieben, keine "")
"correct": false  ✅ Richtig
"correct": "true" ❌ Falsch (nicht in Anführungszeichen!)
"correct": True   ❌ Falsch (nicht großgeschrieben!)
```

### 4. **Zahlen**
```json
"id": 1      ✅ Richtig (keine Anführungszeichen bei Zahlen)
"id": "1"    ❌ Falsch (ist dann ein Text, keine Zahl)
```

## 📋 Vollständiges Beispiel - Netzwerk-Quiz:

```json
{
  "title": "Netzwerk-Grundlagen Quiz",
  "subtitle": "Testen Sie Ihr Wissen über Computer-Netzwerke",
  "questions": [
    {
      "id": 1,
      "question": "Was bedeutet die Abkürzung IP?",
      "answers": [
        { "text": "Internet Provider", "correct": false },
        { "text": "Internet Protocol", "correct": true },
        { "text": "Internal Process", "correct": false },
        { "text": "International Port", "correct": false }
      ],
      "explanation": "IP steht für Internet Protocol und ist die Grundlage der Internetkommunikation."
    },
    {
      "id": 2,
      "question": "Welche IP-Adresse ist eine private Adresse?",
      "answers": [
        { "text": "8.8.8.8", "correct": false },
        { "text": "192.168.1.1", "correct": true },
        { "text": "1.1.1.1", "correct": false },
        { "text": "123.45.67.89", "correct": false }
      ],
      "explanation": "192.168.x.x ist ein privater IP-Bereich für lokale Netzwerke."
    },
    {
      "id": 3,
      "question": "Was ist die Aufgabe eines Routers?",
      "answers": [
        { "text": "Dateien speichern", "correct": false },
        { "text": "Netzwerke verbinden", "correct": true },
        { "text": "Viren scannen", "correct": false },
        { "text": "E-Mails versenden", "correct": false }
      ],
      "explanation": "Ein Router verbindet verschiedene Netzwerke miteinander und leitet Datenpakete weiter."
    }
  ]
}
```

## 🔧 So nutzen Sie Ihre JSON-Datei:

### Option 1: Automatisch laden
1. Speichern Sie Ihre JSON-Datei als `quiz_fragen.json`
2. Legen Sie sie im **gleichen Ordner** wie die HTML-Datei
3. Öffnen Sie `quiz_app_json.html` im Browser
4. Fertig! Quiz lädt automatisch

### Option 2: Manuell hochladen
1. Öffnen Sie `quiz_app_json.html` im Browser
2. Klicken Sie auf "JSON-Datei auswählen"
3. Wählen Sie Ihre JSON-Datei aus
4. Quiz startet sofort

## 🛠️ JSON validieren (Fehler finden):

**Online-Tools:**
- https://jsonlint.com
- https://jsonformatter.org
- https://jsoneditoronline.org

**Vorgehen:**
1. Kopieren Sie Ihr komplettes JSON
2. Fügen Sie es in eines der Tools ein
3. Klicken Sie auf "Validate" oder "Format"
4. Das Tool zeigt Fehler an (z.B. "Komma fehlt in Zeile 15")

## ❌ Häufige Fehler:

### Fehler 1: Vergessenes Komma
```json
{
  "id": 1
  "question": "..."  ❌ Komma fehlt nach "1"
}
```

**Richtig:**
```json
{
  "id": 1,           ✅
  "question": "..."
}
```

### Fehler 2: Komma zu viel
```json
{
  "id": 1,
  "question": "...",  ❌ Letzter Eintrag braucht KEIN Komma
}
```

**Richtig:**
```json
{
  "id": 1,
  "question": "..."   ✅
}
```

### Fehler 3: Falsche Anführungszeichen
```json
"title": 'Mein Quiz'  ❌ Einfache Anführungszeichen
```

**Richtig:**
```json
"title": "Mein Quiz"  ✅ Doppelte Anführungszeichen
```

### Fehler 4: Text mit Sonderzeichen
```json
"question": "Was ist "richtig"?"  ❌ Anführungszeichen im Text
```

**Richtig:**
```json
"question": "Was ist \"richtig\"?"  ✅ Mit Backslash maskieren
```

Oder besser:
```json
"question": "Was ist 'richtig'?"  ✅ Einfache im Text sind OK
```

### Fehler 5: Umlaute/Sonderzeichen
```json
"question": "Wie groß ist..."  ⚠️ Funktioniert meist, aber...
```

**Sicherer:**
- Speichern Sie die Datei als **UTF-8** (in den meisten Editoren Standard)
- Oder verwenden Sie: `"Wie gross ist..."`

## 💡 Tipps:

1. **Einrückung:** Macht JSON lesbarer, aber ist nicht zwingend
2. **Validierung:** Nutzen Sie Online-Tools vor dem Speichern
3. **Backup:** Kopieren Sie die funktionierende Version vor Änderungen
4. **Schritt für Schritt:** Ändern Sie erst eine Frage, dann testen
5. **Editor:** VS Code zeigt JSON-Fehler direkt an (sehr hilfreich!)

## 📁 Mehrere Quizze erstellen:

Erstellen Sie verschiedene JSON-Dateien:
- `quiz_python.json`
- `quiz_netzwerke.json`
- `quiz_html.json`
- `quiz_datenbanken.json`

Laden Sie sie einfach in der Quiz-App hoch!

## 🎓 Beispiel-Themen:

Ich kann Ihnen gerne fertige JSON-Dateien erstellen für:
- Python (Schleifen, Funktionen, Listen)
- HTML/CSS
- Netzwerke (IP, Protokolle)
- Datenbanken (SQL)
- Algorithmen
- Binärsystem
- Kryptographie

Einfach fragen! 😊
