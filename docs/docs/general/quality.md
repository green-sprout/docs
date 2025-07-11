# Qualitätsbericht
Um die Qualität des Codes & der WebApp zu gewährleisten wurden die folgenden Maßnahmen getroffen:
- Es wurde eine technische Review durchgeführt, deren Ergebniss [hier](https://github.com/green-sprout/blog/discussions/19) eingesehen werden können.
- Es wurde ein [Code Refactoring](https://github.com/green-sprout/docs/blob/main/docs/docs/general/Refactoring.md) durchgeführt um Probleme aus der Review zu addressieren
- Es wurden Code Coverage Berichte mittles JaCoCo eingerichtet, welche manuel Clientside und beim Pushen auf den Main-Branch automatisch durchgeführt werden. Ein Beispiel davon kann [hier](https://github.com/green-sprout/backend/pull/4) eingesehen werden.
- Es wurde das IntelliJ-Plugin "MetricsReloaded" eingeführt mit welchem Statistiken wie Attribute Hiding Factor (AHF), Coupling Factor (CF) und Average Operation Complexity (AOC) so wie viele weitere berechnet und eingesehen werden können. Mehr Informationen dazu können [hier](https://github.com/green-sprout/blog/discussions/16) gefunden werden.
