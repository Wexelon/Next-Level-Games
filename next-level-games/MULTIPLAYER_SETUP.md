# Echter Online-Multiplayer – nächster Integrationsschritt

Die aktuelle HTML-Version 10 enthält weiterhin den bisherigen lokalen Demo-Login und lokale Spielstände. Das ist **noch kein geräteübergreifender Multiplayer**. Für echte Accounts, gemeinsame Gegnerlisten, synchronisierte Basen, globale WAR- und Tech-Empire-Ranglisten sowie Live-Kämpfe muss ein Backend verbunden werden.

## Vorgesehene Infrastruktur

- **Hosting:** GitHub Pages (liefert nur HTML/CSS/JS aus)
- **Backend:** Supabase (Auth, PostgreSQL und Realtime)
- **Authentifizierung:** Supabase Auth mit E-Mail und Passwort; Benutzernamen werden serverseitig eindeutig gespeichert.
- **Spielstände:** pro Auth-User ein Datensatz in `game_saves`; darin werden WAR- und Tech-Empire-Fortschritt gespeichert. Änderungen werden über Realtime an andere Clients verteilt.
- **Ranglisten:** serverseitig berechnete und veröffentlichte Scores für WAR und Tech Empire; die Clients laden die sortierten Spielerlisten aus dem Backend.
- **Kämpfe:** serverseitig angelegte Battle-Sessions mit Angreifer, Verteidiger, Status und Ergebnis. Das Ergebnis darf nicht nur im Browser berechnet werden, sonst könnte ein Spieler Siege fälschen.
- **Ein Account pro Browserinstallation:** eine zufällige Installations-ID wird beim ersten Start erzeugt und serverseitig beansprucht. Die Datenbank weist eine zweite Registrierung derselben Installations-ID ab. Das ist eine praktische Gerätebegrenzung, aber keine fälschungssichere Hardware-ID: Löschen der Browserdaten oder ein neues Browserprofil kann eine neue ID erzeugen.

## Was für die Aktivierung benötigt wird

1. Ein Supabase-Projekt erstellen.
2. Projekt-URL und den öffentlichen `anon`-Key bereitstellen (niemals den `service_role`-Key in die HTML-Datei schreiben).
3. Supabase Auth auf E-Mail/Passwort konfigurieren.
4. Datenbankschema, Row-Level-Security-Policies und serverseitige Funktionen für Registrierung, Gerätebindung, Speichern und Kampfresultate einrichten.
5. Den bisherigen lokalen Login-/Speicheradapter in `index.html` auf Supabase Auth und Datenbank umstellen.
6. Die beiden lokalen Ranglisten durch serverseitige Abfragen bzw. Views ersetzen. Scores sollten serverseitig validiert oder aus gespeicherten Spieldaten abgeleitet werden, damit Browser-Clients ihre Ranglistenpunkte nicht beliebig fälschen.

**Wichtig:** Bis diese Einrichtung erfolgt ist, bleiben Konten, PvP und Leaderboards lokal im Browser. Die Datei kann auf GitHub Pages veröffentlicht werden, aber allein durch das Hochladen entsteht kein Online-Multiplayer.
