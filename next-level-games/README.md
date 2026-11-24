# Next Level Games – WAR & Tech Empire (Version 10)

## Start
`index.html` im Browser öffnen oder den Ordner auf GitHub Pages veröffentlichen.

## Version 10 – Tech Empire und Ranglisten

### Tech Empire
- Neues Spiel direkt nach der Anmeldung im Spiele-Hub.
- Eigenes Technologieunternehmen mit frei wählbarem Unternehmensnamen, Startkapital, Forschungspunkten und Labor-Upgrades.
- Forschungsbaum mit 40 Technologien in den Bereichen Werkstoffe/Fertigung, Displays, CPUs/Grafikprozessoren, Speicher, Funk, Akkus, Kamera/Audio sowie Software/Sicherheit.
- Erforschbare Komponenten wie LCD-, OLED-, AMOLED- und MicroLED-Bildschirme, CPU-Architekturen, mobile SoCs, GPUs, High-End-Grafikkarten, KI-Chips, DDR-/LPDDR-Speicher, NAND, NVMe, 5G/6G, Akkutechnik und mehr.
- 13 veröffentlichbare Gerätearten bzw. Produktmodelle: Smartphones (Einstieg, Premium, faltbar), Tablet, Ultrabook, Gaming-Laptop, Desktop-PC, Monitor, OLED-Fernseher, Smartwatch, Spielekonsole, VR-Headset und Digitalkamera.
- Jedes Produkt verlangt die dafür benötigten Technologien. Veröffentlichte Geräte erzeugen laufende Einnahmen.
- Forschungspunkte werden automatisch generiert; höhere Laborstufen steigern die Forschungsrate.

### Leaderboards
- Eigenes WAR-Leaderboard, nach Basis-, Forschungs- und Einheitenstärke sortiert.
- Eigenes Tech-Empire-Leaderboard, nach Unternehmenswert sortiert.
- Beide Ranglisten zeigen alle Konten, die im aktuellen Browser gespeichert sind, vom höchsten zum niedrigsten Wert.
- Die eigene Zeile wird markiert.

### WAR
Die bestehenden WAR-Funktionen aus Version 9 bleiben erhalten, darunter Nation, Basisbau, Forschung, Marine/Luftwaffe, Drohnen, Truppen, Fahrzeuge und Kampf.

## Wichtiger Hinweis zu Accounts, Multiplayer und Ranglisten
Der Login, die Spielstände und die beiden Ranglisten werden weiterhin lokal im Browser gespeichert. Die Ranglisten enthalten daher nur Konten, die in genau diesem Browser angelegt wurden. Sie sind **noch keine globalen Online-Ranglisten**.

GitHub Pages hostet nur die statische Website. Für geräteübergreifende Accounts, gemeinsame Spielstände, Echtzeit-Multiplayer und globale Ranglisten ist ein Backend erforderlich. Die geplante Supabase-Anbindung und die Begrenzung auf eine Registrierung pro Browserinstallation sind in `MULTIPLAYER_SETUP.md` beschrieben. Eine Browser-Installations-ID ist keine fälschungssichere Hardware-ID. Niemals einen Supabase `service_role`-Key im Frontend veröffentlichen.

## Enthaltene Dateien
- `index.html` – spielbare Browser-Version
- `MULTIPLAYER_SETUP.md` – Anforderungen und Schritte für echten Online-Multiplayer
