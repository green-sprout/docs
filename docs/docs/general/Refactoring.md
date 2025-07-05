## Refactoring-Zusammenfassung

### 🛠️ OsmService
- `@Service` und `@Slf4j` Annotationen hinzugefügt für klare Struktur und Logging.
- `ObjectMapper` über Konstruktor injiziert (bessere Testbarkeit und Konfiguration).
- Wiederverwendbaren HTTP-Client eingeführt zur effizienten Ressourcennutzung.
- Verbesserte Fehlerbehandlung durch sauberes Exception Handling.
- Fehler werden nun korrekt geloggt statt über `System.out` ausgegeben.

### 🧩 OsmController
- Konstruktor-Injektion mit `@RequiredArgsConstructor` eingeführt.
- Verwendung von `@RestController` statt `@Controller` + `@ResponseBody`.
- `System.out.println` durch `slf4j` Logging ersetzt.
- Verbesserte und konsistentere Fehlermeldungen für bessere Nutzererfahrung.

### 🔐 Späteres Refactoring
- JWT-Secret-Key abgesichert (nicht mehr im Code hardcoded).
- Zusätzliche Tests geschrieben, um neue Klassen und Funktionalität abzudecken.
