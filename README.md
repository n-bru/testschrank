# Unser Testschrank – einrichten

Die Seite besteht aus einer einzigen Datei: `index.html`. Ausleihen und Fehlermeldungen laufen über Microsoft Forms und landen in Excel. Dafür braucht niemand ein Claude- oder GitHub-Konto, nur das normale Schulkonto.

## 1. Ausleih-Formular anlegen (ca. 10 Min.)

1. Im Teams-Kanal des Sonderpädagogik-Teams unter **Dateien** eine neue Excel-Datei anlegen, z. B. „Ausleihliste Testschrank“.
2. Die Datei in Excel im Browser öffnen: **Einfügen → Forms → Neues Formular**. So landen die Antworten automatisch in dieser Datei.
3. Drei Fragen anlegen, genau in dieser Schreibweise:
   - **Test** (Text)
   - **Kürzel** (Text)
   - **Aktion** (Auswahl mit den Optionen **Ausleihe** und **Rückgabe**)
4. Einstellungen (⋯ → Einstellungen): „Nur Personen in meiner Organisation können antworten“ an, „Namen erfassen“ **aus**.
5. Vorausgefüllten Link holen: ⋯ → **Vorausgefüllten Link abrufen**. Bei Test `TESTNAME` eintippen, bei Kürzel `KUERZEL`, bei Aktion **Ausleihe** wählen. Dann **Vorausgefüllten Link abrufen** und den Link kopieren.

## 2. Fehler-Formular anlegen (ca. 5 Min.)

1. Ein zweites Formular, z. B. „Fehler im Testschrank“, mit den Fragen **Test** (Text), **Was stimmt nicht?** (langer Text), **Was wäre richtig?** (langer Text) und **Quelle** (Text, optional).
2. Vorausgefüllten Link holen, bei Test `TESTNAME` eintippen und kopieren.

Wenn kein Formular gewünscht ist, reicht eine Mailadresse (siehe Schritt 3).

## 3. Links in die Seite eintragen

`index.html` mit einem Texteditor öffnen. Weit unten steht der Block **Einstellungen**. Dort die Links zwischen die Anführungszeichen setzen:

```js
const FORM_AUSLEIHE="";  // Link aus Schritt 1.5
const AUSLEIHE_URL="";   // Link zur Excel-Datei (Teilen → Personen in eurer Organisation)
const MELDEN_FORM="";    // Link aus Schritt 2.2
const MELDEN_MAIL="";    // nur falls kein Fehler-Formular: Mailadresse
```

Die Wörter `TESTNAME`, `KUERZEL` und `Ausleihe` im Link bleiben stehen. Die Seite ersetzt sie beim Klick durch den Test, das Kürzel und bei „Zurückgeben“ durch „Rückgabe“.

## 4. Auf GitHub veröffentlichen

1. Neues Repository anlegen, z. B. `testschrank`, und `index.html` hochladen.
2. **Settings → Pages → Branch: main, Ordner: / (root) → Save.**
3. Nach etwa einer Minute ist die Seite unter `https://<dein-name>.github.io/testschrank/` erreichbar.

GitHub Pages ist öffentlich. Das ist in Ordnung, weil die Seite nur Testinformationen enthält. Kürzel und Ausleihen stehen nur in eurer Excel-Datei.

## 5. Testen

Einen Test öffnen, Kürzel eintragen, **Ausleihen** klicken, absenden, und in der Excel-Datei nachsehen, ob die Zeile ankommt. Danach mit **Zurückgeben** dasselbe.

## Datenschutz

- In Kürzel, Formulare und Fehlermeldungen kommen keine Namen oder Daten von Schüler:innen.
- Die Seite speichert nur das eigene Kürzel im Browser, damit man es nicht jedes Mal eintippen muss.
