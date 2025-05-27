# Technical Review
**Datum:** 27.05.25

**Dauer:** 8:32 **/** 9:17 

**Teilnehmer**
Moderation: Safae K./Samuel B.

Notizen: Samuel B.

Code Review (Team Intern): Safae K./Jonas S./Valentin W./Paula K./Samuel B.

Code Review (Extern): Lukas S. (Team Restaurant Reservierung)

Projektmanagement Review: Safae K./Samuel B.

**Ziel / Fokus**

- Ausgewählte Abschnitte: 
	Backend, generell

- Was wird untersucht?
	Sicherheit + Generelle Übersicht

- Warum die Wahl?
	Die Wahl fiel auf das Backend, da wir hier ein höheres Niveau im Rahmen der Review aufbringen konnten und auch unser externer Review-Partner sich besser mit dem Thema auskennt.

**Komponenten für die Review**
- Login/Registierung Komponente
- OpenStreetAPI Daten Aurufen Komponente
- Unit Tests
- Datenbankverbindung
- Allgemeine Struktur

**Kriterien für die Review**
- Codequalität
- Security
- Fehlerbehandlung

**Review Methodik**

Walkthrough + Code Review

**Ergebnis**
- Codequalität:
    - zumeist hohe Codequalität.
    - Kernelmente des Systems werden getestet.
- Security:
    - `CorsConfig.java` - anyRequest().permitAll()
    - `JWTService.java` - Secret Key sollte ausgelagert werden.
- Fehlerbehandlung:
    - `AuthService.java`, `OsmController.java` weisen eine umfangreiche Fehlerbehandlung auf
  

# External Review


**Komponenten für die Review**
- Login/Registierung Komponente
 - OpenStreetAPI Daten Aurufen Komponente
- Unit Tests
- Datenbankverbindung
- Allgemeine Struktur

**Kriterien für die Review**
- Codequalität
- Security
- Fehlerbehandlung
  
**Review Methodik**

Walkthrough + Code Review

**Ergebnis**
- Codequalität:
    - Performancerelevante Quellcodesegmente weisen eine durchgehend hohe Codequalität aus.
    - Tests decken sicherheitsrelevante Kernkomponenten der Anwendung ausreichend ab.
- Security:
    - `SecurityConfig.java` - CORS-Sicherheitsstandards müssen einhalten werden (.permitAll()-Methode)
    - `CorsConfig.java` - keine beliebigen Headers und any-Origins akzeptieren
    - `AuthService.java` - Implementieren von Input-Sanitisation-Mechanismen für benutzerspezifische Daten.
    - `JWTService.java` - Datei enthält Authentifizierungsschlüssel, welcher NICHT in der Datei stehen sollte.
- Fehlerbehandlung:
    - `AuthController.java` - hat kein Error-Handling
    - ansonsten weitreichendes Error Handling

**Bemerkung**

`Sicherheitstechnisch ist vielleicht noch etwas Bedarf da, das man da noch ein paar Sachen fixt. Ansonsten solide Projektstruktur.`



