# Unser Testschrank – einrichten

Die Seite besteht aus einer einzigen Datei: `index.html`. Vorschläge und Fehlermeldungen laufen über Microsoft Forms und landen in Excel. Dafür braucht niemand ein Claude- oder GitHub-Konto, nur das normale Schulkonto.

Ausleihen läuft ohne Formular: Test aus dem Schrank in C134 nehmen, nutzen, zurückstellen. Die Seite zeigt nur den Standort.

## 1. Vorschlags-Formular anlegen (ca. 10 Min.)

Damit Kolleg:innen eintragen können, was im Testschrank fehlt: kostenlose Funde (z. B. aus der Diagnostik-Suchmaschine) und Kaufwünsche für die nächste Bestellung.

1. Im Teams-Kanal des Sonderpädagogik-Teams unter **Dateien** eine neue Excel-Datei anlegen, z. B. „Vorschläge Testschrank“.
2. Die Datei in Excel im Browser öffnen: **Einfügen → Forms → Neues Formular**. So landen die Antworten automatisch in dieser Datei.
3. Diese Fragen anlegen:
   - **Name des Verfahrens** (Text, Pflicht)
   - **Link** (Text), z. B. Seite in der Diagnostik-Suchmaschine oder beim Verlag
   - **Art** (Auswahl): **Kostenlos online, bitte aufnehmen** · **Kaufwunsch** · **Neuere Fassung von etwas, das wir haben**
   - **Wofür?** (Text): Bereich, Förderschwerpunkt, Klassen
   - **Preis, falls bekannt** (Text)
   - **Dein Kürzel** (Text, optional)
4. Einstellungen (⋯ → Einstellungen): „Nur Personen in meiner Organisation können antworten“ an, „Namen erfassen“ **aus**.
5. Vorausgefüllten Link holen: ⋯ → **Vorausgefüllten Link abrufen**. Bei „Name des Verfahrens“ `TESTNAME` eintippen, dann den Link kopieren. Dann füllt die Seite bei „Kaufwunsch eintragen“ den Namen schon aus.

## 2. Fehler-Formular (gibt es schon)

Fragen **Test** (Text), **Was stimmt nicht?**, **Was wäre richtig?**, **Quelle** (optional). Vorausgefüllter Link mit `TESTNAME`.

## 3. Links in die Seite eintragen

`index.html` mit einem Texteditor öffnen. Weit unten steht der Block **Einstellungen**:

```js
const VORSCHLAG_FORM=""; // Link aus Schritt 1.5
const MELDEN_FORM="…";   // Fehler-Formular
const MELDEN_MAIL="";    // nur falls kein Formular: Mailadresse
```

Ist `VORSCHLAG_FORM` leer, kopiert der Knopf „Vorschlag eintragen“ eine Textvorlage in die Zwischenablage.

## 4. Auf GitHub veröffentlichen

1. `index.html` im Repository `testschrank` ersetzen.
2. **Settings → Pages → Branch: main, Ordner: / (root)** ist schon eingestellt. Nach etwa einer Minute ist die neue Fassung online.

GitHub Pages ist öffentlich. Das ist in Ordnung, weil die Seite nur Testinformationen enthält. Vorschläge und Kürzel stehen nur in eurer Excel-Datei.

## Bereiche

Deutsch ist in die Kompetenzbereiche aufgeteilt: **Sprechen und Zuhören**, **Lesen**, **Schreiben** (mit Rechtschreibung) und **Grammatik** (Sprachreflexion). Daneben gibt es Mathematik, Kognition, Sozial-emotional und Verlaufsdiagnostik. Ein Verfahren kann mehrere Bereiche haben, z. B. `ber:["Lesen","Schreiben"]`. Ist der Bereich noch nicht geklärt, steht `ber:"unklar"` (angezeigt als „Bereich offen“).

## Suche

Die Suche verzeiht Tippfehler, Groß- und Kleinschreibung, Umlaute (ä, ae, a) und ß. Sie findet auch Teilwörter, Kürzel (LE, ES, SQ, KM, HK, IQ, LRS, ADHS, DaZ) und verwandte Begriffe, z. B. „Rechnen“ → Mathematik, „Rechtschreibung“ → Schreiben, „Sprachreflexion“ → Grammatik. „Deutsch“ findet alle Verfahren aus den Deutsch-Bereichen. Eine Zahl gilt als Klasse: „Lesen 7“ zeigt Lesetests für Klasse 7.

Fehlt ein Suchwort, in `index.html` die Liste `SYN` suchen und das Wort in die passende Zeile eintragen.

## Datenschutz

- In Vorschläge und Fehlermeldungen kommen keine Namen oder Daten von Schüler:innen.
- Die Seite speichert nur die eigene Merkliste und die gewählte Ansicht im Browser.
