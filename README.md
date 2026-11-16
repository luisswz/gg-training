# GG-Training

Lern-Website zur Vorbereitung auf die Kurzarbeit in **Politik und Gesellschaft** (FOS 12, Bayern).

Themen: Grundgesetz, wehrhafte Demokratie, Gewaltenteilung, Grundrechte, AfD-Verbotsverfahren und das politische System der Bundesrepublik. Mit Podcast und Erklärvideo.

👉 **Live-Seite:** https://luisswz.github.io/gg-training/

## Fortschritt auf mehreren Geräten: der Lerncode

- Jedes Profil bekommt automatisch einen **Lerncode** (z. B. `ABCD-EFGH-JKMN`). Du findest ihn oben unter 👤 Profil.
- Dein Fortschritt wird damit automatisch online gespeichert, **ohne Login und ohne deinen Namen**.
- Auf einem anderen Gerät: „Code eingeben“ oder den Link „Link fürs andere Gerät“ öffnen. Dann ist dein Stand da.
- Wer deinen Code kennt, kann deinen Stand sehen und ändern. Also nur selbst benutzen, nicht in Gruppen posten.
- Ohne Internet funktioniert alles weiter, der Abgleich passiert später.
- „Sicherung speichern/laden“ gibt es weiterhin als Notlösung.

## Technik

- Eine einzige Datei `index.html`, kein Build-Schritt, gehostet über GitHub Pages.
- Fortschritt liegt im Browser (localStorage) und per Lerncode in Firebase Cloud Firestore (Spark-Tarif, Region Frankfurt `europe-west3`).
- Zugriffsregeln: [`firestore.rules`](firestore.rules). Ein Lerncode kann nur sein eigenes Dokument lesen und schreiben, Auflisten und Löschen ist gesperrt.
- Der Firebase-Schlüssel in `index.html` ist ein öffentlicher Web-Schlüssel, geschützt wird über die Regeln.
- Regeln neu veröffentlichen: `firebase deploy --only firestore:rules`
