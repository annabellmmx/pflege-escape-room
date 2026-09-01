# Escape Room – Geschichte der Pflege

Du brauchst auf den Schul-PCs keine Installation. Beide Seiten laufen im Browser.

## Dateien
- `gamemaster.html` – deine Steuerung im Büro
- `screen.html` – Vollbildanzeige im Escape Room
- `config.js` – hier kommen die Firebase-Zugangsdaten hinein
- `shared.css` – Design
- `firebase-rules.json` – einfache Datenbankregeln für die Einrichtung

## Einrichtung – einmalig

### 1. Firebase-Projekt erstellen
1. Öffne https://console.firebase.google.com/
2. "Projekt hinzufügen"
3. Name z. B. `pflege-escape-room`
4. Google Analytics kannst du für diesen Zweck deaktivieren.
5. Im Projekt links **Build → Realtime Database**
6. Datenbank erstellen.
7. Region auswählen.
8. Danach bei **Regeln / Rules** für den ersten Test diese Regeln eintragen:

{
  "rules": {
    ".read": true,
    ".write": true
  }
}

Hinweis: Diese Regeln sind absichtlich simpel für einen geschlossenen Unterrichts-Escape-Room. Der Link sollte nicht öffentlich herumgegeben werden.

### 2. Web-App registrieren
1. In Firebase auf das Zahnrad → Projekteinstellungen.
2. Unter "Deine Apps" Web-App (`</>`) hinzufügen.
3. App-Name z. B. `escape-room`.
4. Firebase zeigt dir ein Objekt namens `firebaseConfig`.
5. Öffne `config.js` und ersetze dort die Platzhalter durch diese Werte.
6. Wichtig: `databaseURL` muss ebenfalls enthalten sein.

### 3. Dateien online stellen – ohne Programme zu installieren
Am einfachsten über GitHub Pages:
1. Kostenloses Konto bei https://github.com/ erstellen/anmelden.
2. Neues Repository anlegen, z. B. `pflege-escape-room`.
3. Diese fünf Dateien hochladen.
4. Repository → Settings → Pages.
5. "Deploy from a branch" → Branch `main` → `/root` → Save.
6. Nach kurzer Zeit erhältst du eine Webadresse.

Dann sind deine Seiten:
- `https://DEINNAME.github.io/pflege-escape-room/gamemaster.html`
- `https://DEINNAME.github.io/pflege-escape-room/screen.html`

## Unterricht
### Escape-Room-PC
1. `screen.html` öffnen.
2. F11 drücken → Vollbild.
3. Die Seite offen lassen.

### Dein Laptop im Büro
1. `gamemaster.html` öffnen.
2. Prüfen, dass oben "Mit Firebase verbunden" steht.
3. Timer starten.
4. Hinweise nach Bedarf anklicken.

Ein Hinweis erscheint ungefähr 12 Sekunden auf dem Escape-Room-Bildschirm und verschwindet danach automatisch.

## Enthaltene Stationen
1. Ereigniskarten / Reihenfolge → 5–1–8 → BETT
2. Historischer Krankensaal → Code 332
3. Zeitung / Spiegel → SPIEGEL → Code 315
4. Finale → Lampe

Zusätzlich:
- 45-Minuten-Timer
- Pause / Fortsetzen / Reset
- 10-, 5- und 1-Minuten-Warnung
- freie Nachricht
- "Pflege gerettet"
- "Zeit abgelaufen"

## Sicherheit
Die mitgelieferten Firebase-Regeln sind für einen kleinen geschlossenen Test gedacht und nicht für eine öffentliche App mit sensiblen Daten. In diesem Escape Room werden keine personenbezogenen Daten gespeichert.
