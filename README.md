# Join

Join ist eine responsive Kanban-Projektmanagement-App, die im Rahmen der Developer Akademie Weiterbildung entstanden ist. Die App bietet Login, Registrierung, Kontaktverwaltung, Task-Erstellung, Board-Ansicht und eine Summary-Uebersicht. Daten werden ueber Firebase Authentication und die Firebase Realtime Database verwaltet; fuer den Gastzugang werden Aufgaben lokal im Browser gespeichert.

## Features

- Login und Registrierung mit Firebase Authentication
- Gast-Login mit lokal gespeicherten Gast-Aufgaben
- Kanban-Board mit den Spalten `To do`, `In progress`, `Await feedback` und `Done`
- Aufgaben erstellen, bearbeiten, suchen und nach Status verwalten
- Prioritaeten, Faelligkeitsdatum, Kategorien, Kontakte und Subtasks fuer Aufgaben
- Kontaktverwaltung mit Erstellen, Bearbeiten und Loeschen von Kontakten
- Summary-Dashboard mit Aufgabenuebersicht
- Responsive Layouts fuer Desktop und Mobile
- Hilfe-, Datenschutz- und Impressumsseiten
- JSDoc-Dokumentation fuer die JavaScript-Dateien

## Technologien

- HTML5
- CSS3
- Vanilla JavaScript
- Firebase Authentication
- Firebase Realtime Database
- JSDoc mit `better-docs`

## Projektstruktur

```text
join/
|-- assets/                 # Logos, Icons und Fonts
|-- scripts/                # JavaScript-Module fuer Auth, Board, Contacts, Summary usw.
|-- sites/                  # Unterseiten der App
|-- styles/                 # Seiten- und Komponenten-Stylesheets
|-- out/                    # Generierte JSDoc-Dokumentation
|-- index.html              # Login-Seite / Einstiegspunkt
|-- script.js               # Globale Hilfsfunktionen
|-- style.css               # Globale Basis-Styles
|-- package.json            # npm-Scripts und Dev-Abhaengigkeiten
|-- jsdoc.json              # JSDoc-Konfiguration
`-- jsdoc-andi.json         # Alternative JSDoc-Konfiguration
```

## Installation

Voraussetzung: Node.js und npm sind installiert.

```bash
git clone https://github.com/Hueppi92/join.git
cd join
npm install
```

## Lokale Nutzung

Die App ist eine statische Website ohne Build-Schritt. Du kannst `index.html` direkt im Browser oeffnen.

Empfohlen ist trotzdem ein lokaler Webserver, damit relative Pfade und Browser-Verhalten moeglichst nah an einer echten Auslieferung sind. Zum Beispiel:

```bash
npx serve .
```

Danach die ausgegebene lokale URL im Browser oeffnen und mit `index.html` starten.

## Firebase

Die Firebase-Konfiguration befindet sich in:

```text
scripts/db.js
```

Genutzt werden:

- Firebase App
- Firebase Authentication
- Firebase Realtime Database

Damit Login und Registrierung funktionieren, muss im verbundenen Firebase-Projekt die E-Mail/Passwort-Authentifizierung aktiviert sein. Fuer die Realtime Database muessen passende Regeln gesetzt sein, damit angemeldete Nutzer ihre Daten lesen und schreiben koennen.

## Wichtige Seiten

- `index.html` - Login und Gast-Login
- `sites/sign-up.html` - Registrierung
- `sites/summary.html` - Dashboard / Aufgabenuebersicht
- `sites/task-editor.html` - Aufgabe erstellen
- `sites/taskboard.html` - Kanban-Board
- `sites/contacts.html` - Kontaktverwaltung
- `sites/help.html` - Hilfe
- `sites/privacy-policy.html` - Datenschutz
- `sites/legal-notice.html` - Impressum

## npm Scripts

```bash
npm run doc
```

Generiert die JSDoc-Dokumentation anhand von `jsdoc.json` in den Ordner `out/`.

```bash
npm run doc-andi
```

Generiert die Dokumentation mit der alternativen Konfiguration `jsdoc-andi.json`.

Hinweis: Fuer Tests ist aktuell noch kein Test-Setup eingerichtet. Das vorhandene `npm test` Script ist ein Platzhalter.

## Entwicklungshinweise

- Globale Firebase-Initialisierung liegt in `scripts/db.js`.
- Wiederverwendbare Hilfsfunktionen liegen in `script.js`.
- Board-Logik ist auf mehrere Dateien unter `scripts/taskboard_*.js` und `scripts/taskboard*.js` verteilt.
- Task-Editor-Logik liegt in `scripts/taskeditor*.js`.
- Kontaktlogik liegt in `scripts/contacts*.js`.
- Authentifizierung und Session-Kontext liegen in `scripts/login*.js`, `scripts/sign-up*.js`, `scripts/auth-guard.js` und `scripts/user-context.js`.

## Dokumentation

Die generierte Dokumentation befindet sich nach dem Ausfuehren von `npm run doc` im Ordner:

```text
out/
```

Die Startdatei der generierten Dokumentation ist:

```text
out/index.html
```

## Repository

GitHub: [Hueppi92/join](https://github.com/Hueppi92/join)

## Lizenz

Dieses Projekt ist laut `package.json` unter der ISC-Lizenz angegeben.
