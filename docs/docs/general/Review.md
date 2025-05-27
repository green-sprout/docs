# Technical Review
**Datum:** 27.05.25

**Dauer:** 8:32 **/** 8:57 

**Teilnehmer:**
Moderation: Safae K./Samuel B.

Notizen: Samuel B.

Code Review (Team Intern): Safae K.

Code Review (Extern): Lukas S.

Projektmanagement Review: Safae K. / Samuel B.

**Ziel / Fokus:**

Ausgewählte Abschnitte: 
	Backend, generell

Was wird untersucht?
	Sicherheit + Generelle Übersicht

Warum die Wahl?
	Die Wahl fiel auf das Backend, da wir hier ein höheres Niveau im Rahmen der Review aufbringen konnten und auch unser externer Review-Partner sich besser mit dem Thema auskennt.

**Komponenten für die Review:**
- Login/Registierung Komponente
 - OpenStreetAPI Daten Aurufen Komponente
- Unit Tests
- Datenbankverbindung
- Allgemeine Struktur

**Kriterien für die Review:**
- Codequalität
- Security
**Review Methodik:**

Walkthrough + Code Review

**Ergebnis:**
`Sicherheitstechnisch ist vielleicht noch etwas Bedarf da, das man da eben noch ein paar Sachen fixt - eben so die CORS-Sachen. Ansonsten solide Projektstruktur.`



`Kommentare von Lukas`
`Cors alle Origins Erlauben ist vermutlich nicht so sicher`
`Ist es sinnvoll, alle headers zu erlauben?`
`Security Config - Welche Implication hat das ".permitAll()" ?`
`Auth Controller hat kein Error-Handling`
`Default Errors wenn zb. 2x die gleiche Email angegeben wird`
`AuthService.java - machen Input-Sanitisation`
`JWTService.java - Datei hat einen Secret Key!! Dieser sollte NICHT in der Datei drinn stehen!!!`

