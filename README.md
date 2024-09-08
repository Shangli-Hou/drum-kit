# drum-kit
# VS-Instant-Messenger

## Architektur

### Lösungsstrategie

**Kernidee:**  
Unser Instant-Messenger-Projekt ermöglicht Echtzeit-Textnachrichten zwischen Nutzern. Die Architektur basiert auf einem Client-Server-Modell, bei dem der Server die Nachrichtenverarbeitung und Benutzerverwaltung übernimmt, während der Client die Benutzeroberfläche bereitstellt.

**Technologien:**  
- **Programmiersprache:** Java
- **Server-Framework:** Spring Boot
- **Client-Technologie:** JavaFX
- **Datenbank:** MySQL
- **Kommunikationsprotokoll:** TCP/IP

**Designentscheidungen:**
- **Middleware:** Spring Boot wurde gewählt für eine robuste und skalierbare Server-Infrastruktur.
- **Architekturansatz:** Client-Server-Architektur zur zentralen Verwaltung und Verarbeitung.
- **Client-Technologie:** JavaFX ermöglicht eine ansprechende und benutzerfreundliche Oberfläche.

**Architekturprinzipien:**
- **Transparancy:** Der Client kommuniziert über klar definierte Schnittstellen mit dem Server.
- **Softwarearchitektur:** Das System ist in Schichten unterteilt: Präsentation, Logik und Daten.
- **Systemarchitektur:** Verwendet ein synchrones Request-Reply Pattern für die Nachrichtenkommunikation.
- **Thin-Client vs. Fat-Client:** Thin-Client-Ansatz, um die Verarbeitung auf dem Server zu konzentrieren.
- **Stateless vs. Stateful Server-Design:** Der Server ist stateless.
- **Fehlersemantik:** Fehler werden dem Benutzer klar kommuniziert.
- **Idempotenz:** Nachrichtenübermittlung ist idempotent.
- **Skalierbarkeit:** Der Server unterstützt horizontale Skalierung für hohe Verbindungen.

## Use Cases

**Use Cases:**
1. **Nachricht senden:** Ein Benutzer sendet eine Nachricht an einen anderen Benutzer.
2. **Nachricht empfangen:** Ein Benutzer empfängt eine Nachricht von einem anderen Benutzer.
3. **Benutzer anmelden:** Ein neuer Benutzer registriert sich.
4. **Benutzer authentifizieren:** Ein bestehender Benutzer meldet sich an.

**User Stories (optional):**
- Als Benutzer möchte ich Nachrichten senden können, um mit Freunden zu kommunizieren.
- Als Benutzer möchte ich Nachrichten empfangen können, um über neue Nachrichten informiert zu werden.

**Use Case-Diagramm:**  
![Use Case Diagram](path/to/use-case-diagram.png)

## Anforderungen

| Anforderung                        | Erfüllung  | Erläuterung                                                               |
|------------------------------------|------------|---------------------------------------------------------------------------|
| **MUST Have Anforderungen**        |            |                                                                           |
| Echtzeit-Nachrichtenaustausch       | Ja         | Implementiert durch TCP/IP-basierte Kommunikation.                         |
| Benutzeranmeldung und Authentifizierung | Ja         | Realisiert mit Spring Boot und MySQL zur Verwaltung von Benutzerdaten.     |
| **SHOULD Have Anforderungen**      |            |                                                                           |
| Benutzerfreundliche Oberfläche      | Ja         | JavaFX für eine ansprechende UI.                                          |
| Nachrichtenprotokollierung          | Teilweise  | Nachrichten werden protokolliert, aber keine detaillierte Historie.       |
| **COULD Have Anforderungen**        |            |                                                                           |
| Gruppennachrichten                  | Nein       | Derzeit nicht implementiert.                                              |
| Dateiübertragung                    | Nein       | Keine Unterstützung für Dateitransfer.                                    |
| **++ Anforderungen**                |            |                                                                           |
| Push-Benachrichtigungen             | Nein       | Momentan nicht unterstützt, geplant für zukünftige Versionen.            |

## Statisches Modell

**Komponentendiagramm:**  
![Komponentendiagramm](path/to/component-diagram.png)

**Verteilungsdiagramm:**  
![Verteilungsdiagramm](path/to/distribution-diagram.png)

**Optional: Paketdiagramm:**  
![Paketdiagramm](path/to/package-diagram.png)

**Klassendiagramme:**  
![Klassendiagramm](path/to/class-diagram.png)

## API

Die API-Dokumentation wird durch Javadoc bereitgestellt. [Javadoc](path/to/api-docs)

## Datenbankmodell

**Datenbankmodell:**  
- **Benutzertabelle:** Speichert Benutzerinformationen.
- **Nachrichtentabelle:** Speichert gesendete Nachrichten.

**Datenbankschema:**  
![Datenbankschema](path/to/database-schema.png)

## Dynamisches Modell

**Aktivitätsdiagramm:**  
![Aktivitätsdiagramm](path/to/activity-diagram.png)

**Sequenzdiagramm:**  
![Sequenzdiagramm](path/to/sequence-diagram.png)

## Getting Started

**Voraussetzungen:**
- Java Development Kit (JDK) 11 oder höher
- Spring Boot
- MySQL
- Maven (für das Dependency Management)
- JavaFX (für die Client-Oberfläche)

**Installation und Deployment:**

1. **Repository klonen:**
   ```bash
   git clone https://github.com/username/vs-instant-messenger.git
