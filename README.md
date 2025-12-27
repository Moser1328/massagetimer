# 💆‍♂️ Massagetimer Web-App

Eine moderne, iPhone-optimierte Web-App für deine Massage-Sessions mit intelligenter Zeitverwaltung und Statistiken.

## 🎯 Features

✅ **Intelligenter Timer**
- Zufallsdauer 5-12 Minuten an Wochentagen
- 5 Sondereingaben pro Jahr für individuelle Dauer
- Unbegrenzte manuelle Eingabe an Sonntagen
- Automatischer Reset der Sondereingaben im neuen Jahr

⏱️ **Timer-Funktionen**
- Visueller Countdown mit Fortschrittsring
- Pause/Fortsetzen-Funktion
- Vibration bei Timer-Ende (wenn unterstützt)
- Push-Benachrichtigung (wenn aktiviert)

📊 **Statistiken & Tracking**
- Anzahl der Massagen
- Durchschnittliche Dauer
- Gesamtzeit
- Durchschnittliche Bewertung
- Detaillierter Verlauf aller Sessions

📱 **PWA (Progressive Web App)**
- Installierbar als App auf dem iPhone
- Funktioniert offline
- Kein App Store nötig
- Automatische Updates

💾 **Lokale Datenspeicherung**
- Alle Daten bleiben auf deinem Gerät
- Keine Cloud, kein Login
- 100% Privatsphäre

## 🚀 Deployment

### Option 1: Vercel (Empfohlen - Am einfachsten!)

1. **Account erstellen:**
   - Gehe zu [vercel.com](https://vercel.com)
   - Klicke auf "Sign Up"
   - Registriere dich mit GitHub, GitLab oder E-Mail

2. **Projekt hochladen:**
   - Klicke auf "Add New..." → "Project"
   - Wähle "Deploy from CLI" oder ziehe die Dateien in den Browser
   - Oder nutze GitHub Import (siehe unten)

3. **Mit GitHub (Alternative):**
   - Erstelle ein GitHub Repository
   - Lade die Dateien hoch
   - Importiere das Repo in Vercel
   - Automatisches Deployment bei jedem Push!

4. **Fertig!**
   - Deine App ist live unter: `https://dein-projekt.vercel.app`
   - Kostenlos für immer
   - Automatisches HTTPS

### Option 2: Netlify

1. **Account erstellen:**
   - Gehe zu [netlify.com](https://netlify.com)
   - "Sign Up" → Mit GitHub/E-Mail

2. **Drag & Drop:**
   - Klicke auf "Add new site" → "Deploy manually"
   - Ziehe den `massagetimer`-Ordner in den Browser
   - Fertig in 30 Sekunden!

3. **URL:**
   - Deine App: `https://random-name.netlify.app`
   - Du kannst den Namen ändern in den Site Settings

### Option 3: GitHub Pages

1. **GitHub Repository erstellen:**
   - Gehe zu [github.com](https://github.com)
   - "New Repository" → Name: `massagetimer`
   - Public repository

2. **Dateien hochladen:**
   - "Add file" → "Upload files"
   - Ziehe alle Dateien rein
   - "Commit changes"

3. **GitHub Pages aktivieren:**
   - Repository Settings → "Pages"
   - Source: "Deploy from a branch"
   - Branch: `main` → Ordner: `/ (root)`
   - "Save"

4. **URL:**
   - Deine App: `https://deinusername.github.io/massagetimer`
   - Dauert 1-2 Minuten bis live

### Option 4: Cloudflare Pages

1. **Account:**
   - [pages.cloudflare.com](https://pages.cloudflare.com)
   - Sign up (kostenlos)

2. **Upload:**
   - "Create a project"
   - "Upload assets"
   - Ordner hochziehen
   - Fertig!

## 📱 Als App auf dem iPhone installieren

1. **Safari öffnen:**
   - Öffne die URL deiner gehosteten App in Safari (nicht Chrome!)

2. **Zur Home-Screen hinzufügen:**
   - Tippe auf das "Teilen"-Symbol (Quadrat mit Pfeil)
   - Scrolle runter → "Zum Home-Bildschirm"
   - Bestätige mit "Hinzufügen"

3. **Fertig!**
   - Die App erscheint wie eine normale App auf deinem iPhone
   - Funktioniert offline
   - Kein Browser-UI mehr

## 🛠️ Lokale Entwicklung

Zum Testen lokal:

```bash
# Einfacher Python Server
python3 -m http.server 8000

# Oder mit Node.js
npx serve

# Dann öffne: http://localhost:8000
```

## 📦 Enthaltene Dateien

```
massagetimer/
├── index.html       # Haupt-App (HTML + CSS + JavaScript)
├── manifest.json    # PWA Configuration
├── sw.js           # Service Worker (Offline-Support)
└── README.md       # Diese Datei
```

## 🎨 Anpassungen

### Farben ändern
In `index.html` → `<style>` Bereich:

```css
/* Gradient ändern */
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);

/* Oder andere Farben: */
background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);  /* Pink */
background: linear-gradient(135deg, #4facfe 0%, #00f2fe 100%);  /* Blau */
background: linear-gradient(135deg, #43e97b 0%, #38f9d7 100%);  /* Grün */
```

### Timer-Dauer anpassen
In `index.html` → JavaScript:

```javascript
// Zeile ~370: Zufallsbereich ändern
const duration = Math.floor(Math.random() * 8) + 5; // 5-12 Min
// Zu z.B. 10-20 Min ändern:
const duration = Math.floor(Math.random() * 11) + 10; // 10-20 Min
```

### Sondereingaben ändern
```javascript
// Zeile ~50 & ~399: 5 → andere Zahl
if (specialCount < 5) {
// Zu z.B. 10:
if (specialCount < 10) {
```

## 🐛 Troubleshooting

**App lädt nicht offline:**
- Service Worker braucht HTTPS (funktioniert automatisch bei Vercel/Netlify)
- localhost funktioniert auch ohne HTTPS

**Icons fehlen:**
- Icons sind optional, App funktioniert auch ohne
- Du kannst eigene Icons erstellen und hochladen

**Statistiken werden nicht angezeigt:**
- Mache mindestens eine Massage
- Daten werden im Browser gespeichert (localStorage)

**Daten weg nach Browser-Löschung:**
- localStorage wird beim Cache-Löschen gelöscht
- Nutze "Als App installieren" für bessere Persistenz

## 💡 Tipps

- **Notifications:** Erlaube Benachrichtigungen für Timer-Ende-Alert
- **Vollbild:** Installiere als App für beste Nutzung
- **Backup:** Exportiere Daten über Browser-DevTools (localStorage)

## 🤝 Support

Fragen oder Probleme? 
- Öffne ein Issue auf GitHub
- Oder passe den Code selbst an - er ist sehr einfach zu verstehen!

## 📝 Lizenz

Frei verwendbar! Mach damit was du willst 🎉

---

Viel Spaß mit deinem Massagetimer! 💆‍♂️✨