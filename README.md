# GG-Training

Lern-Website zur Vorbereitung auf die Kurzarbeit in **Politik und Gesellschaft** (FOS 12, Bayern).

Themen: Grundgesetz, wehrhafte Demokratie, Gewaltenteilung, Grundrechte, AfD-Verbotsverfahren und das politische System der Bundesrepublik. Mit Podcast und Erklärvideo.

👉 **Live-Seite:** https://luisswz.github.io/gg-training/

## Anmelden (freiwillig)

- Oben in der Übersicht auf **👤 Anmelden** tippen, E-Mail und Passwort eingeben, „Konto erstellen“. Fertig.
- Mit Konto ist dein Fortschritt auf all deinen Geräten da und wird automatisch gespeichert.
- Ohne Anmeldung geht alles auch, dann bleibt dein Fortschritt nur in diesem Browser auf diesem Gerät.
- Passwort vergessen? Unter „Anmelden“ auf „Passwort vergessen?“ tippen. Die Mail kommt von Firebase und landet manchmal im Spam.
- „Abmelden“ entfernt deinen Stand von diesem Gerät (praktisch bei geteilten Geräten), im Konto bleibt er erhalten.
- „Konto löschen“ löscht Konto und gespeicherten Fortschritt sofort.

## Technik

- Eine einzige Datei `index.html`, kein Build-Schritt, gehostet über GitHub Pages.
- Fortschritt liegt im Browser (localStorage). Mit Konto zusätzlich in Firebase Cloud Firestore (Spark-Tarif, Region Frankfurt `europe-west3`), Anmeldung über Firebase Authentication (E-Mail + Passwort), alles per REST ohne SDK.
- Zugriffsregeln: [`firestore.rules`](firestore.rules). Jedes Konto darf nur sein eigenes Dokument `users/{uid}` lesen, schreiben und löschen. Auflisten ist gesperrt.
- Der Firebase-Schlüssel in `index.html` ist ein öffentlicher Web-Schlüssel, geschützt wird über die Regeln.
- Regeln neu veröffentlichen: `firebase deploy --only firestore:rules`
