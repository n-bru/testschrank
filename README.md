# Unser Testschrank – einrichten

Die Seite besteht aus einer einzigen Datei: `index.html`. Fehlermeldungen laufen über Microsoft Forms und landen in Excel. Dafür braucht niemand ein Claude- oder GitHub-Konto, nur das normale Schulkonto.

Die Seite zeigt nur, was wir haben: die Tests im Schrank in C134 und kostenlos online verfügbare Verfahren. Keine Kaufvorschläge. Wünsche für Bestellungen laufen nicht über die Seite.

Ausleihen läuft ohne Formular: Test aus dem Schrank nehmen, nutzen, zurückstellen.

## 1. Fehler-Formular (gibt es schon)

Fragen **Test** (Text), **Was stimmt nicht?**, **Was wäre richtig?**, **Quelle** (optional). Vorausgefüllter Link mit `TESTNAME`.

## 2. Link in die Seite eintragen

`index.html` mit einem Texteditor öffnen. Weit unten steht der Block **Einstellungen**:

```js
const MELDEN_FORM="…";   // Fehler-Formular
const MELDEN_MAIL="";    // nur falls kein Formular: Mailadresse
```

## 3. Auf GitHub veröffentlichen

1. `index.html` im Repository `testschrank` ersetzen.
2. **Settings → Pages → Branch: main, Ordner: / (root)** ist schon eingestellt. Nach etwa einer Minute ist die neue Fassung online.

GitHub Pages ist öffentlich. Das ist in Ordnung, weil die Seite nur Testinformationen enthält. Fehlermeldungen stehen nur in eurer Excel-Datei.

## Bereiche

Deutsch ist in die Kompetenzbereiche aufgeteilt: **Sprechen und Zuhören**, **Lesen**, **Schreiben** (mit Rechtschreibung) und **Grammatik** (Sprachreflexion). Daneben gibt es Mathematik, Kognition, Sozial-emotional und Verlaufsdiagnostik. Ein Verfahren kann mehrere Bereiche haben, z. B. `ber:["Lesen","Schreiben"]`. Ist der Bereich noch nicht geklärt, steht `ber:"unklar"` (angezeigt als „Bereich offen“).

## Suche

Die Suche verzeiht Tippfehler, Groß- und Kleinschreibung, Umlaute (ä, ae, a) und ß. Sie findet auch Teilwörter, Kürzel (LE, ES, SQ, KM, HK, IQ, LRS, ADHS, DaZ) und verwandte Begriffe, z. B. „Rechnen“ → Mathematik, „Rechtschreibung“ → Schreiben, „Sprachreflexion“ → Grammatik. „Deutsch“ findet alle Verfahren aus den Deutsch-Bereichen. Eine Zahl gilt als Klasse: „Lesen 7“ zeigt Lesetests für Klasse 7.

Fehlt ein Suchwort, in `index.html` die Liste `SYN` suchen und das Wort in die passende Zeile eintragen.

## Datenschutz

- In Fehlermeldungen kommen keine Namen oder Daten von Schüler:innen.
- Die Seite speichert nur die eigene Merkliste und die gewählte Ansicht im Browser.
