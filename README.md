# drum-kit
# VS-Instant-Messenger

## Architektur

### Lösungsstrategie

**Kernidee:**  
Unser Lösungskonzept für den Instant Messenger beruht auf einer robusten und skalierbaren Architektur, die es dem Benutzer ermöglicht, nahtlos miteinander zu kommunizieren und die Administratoren das System effizient verwalten können. Wir verwenden eine Client-Server-Architektur, bei der der Server als zentrale Instanz fungiert, um Nachrichten zu verwalten, Benutzerkonten zu überwachen und andere Aufgaben auszuführen. Wir verwenden Java für das Programmieren, während wir Sockets für die Kommunikation zwischen Client und Server verwenden.

**Technologien:**  
- **Java**: Programmiersprache für plattformunabhängige Entwicklung.
- **Sockets**: Für die bidirektionale Kommunikation zwischen Client und Server.
- **Spring Boot**: Für serverseitige Logik und Verwaltung.
- **JavaFX**: Für die Client-Oberfläche.
- **MySQL**: Für die Persistenz und Speicherung von Benutzerdaten und Nachrichten.

**Designentscheidungen:**
1. **Wahl der Middleware (Sockets):** Sockets bieten eine zuverlässige und effiziente Möglichkeit für die Kommunikation zwischen Client und Server. Sie ermöglichen eine bidirektionale Datenübertragung und können leicht in Java implementiert werden, was die Entwicklung erleichtert.
2. **Wahl der Programmiersprache (Java):** Java bietet eine breite Unterstützung für Netzwerkkommunikation, eine robuste Objektorientierung und eine große Auswahl an Bibliotheken und Frameworks, die bei der Entwicklung von serverseitigen Anwendungen helfen. Darüber hinaus ist Java plattformunabhängig, was die Skalierbarkeit und Portabilität unserer Lösung verbessert.
3. **Architekturansatz (Client-Server):** Die client-serverbasierte Architektur ermöglicht eine klare Trennung von Client- und Serververantwortlichkeiten, was die Skalierbarkeit und Wartbarkeit verbessert. Der Server übernimmt die zentrale Verwaltung der Nachrichten und anderer Systemfunktionen, während der Client die Benutzeroberfläche und die Benutzerinteraktionen bereitstellt.

**Architekturprinzipien:**
- **Transparancy:** Der Client kommuniziert über klar definierte Schnittstellen (der ClientHandler) mit dem Server.
- **Softwarearchitektur:** Das System ist in Schichten unterteilt: Präsentation, Logik und Daten.
- **Systemarchitektur:** Verwendet ein synchrones Request-Reply Pattern für die Nachrichtenkommunikation.
- **Thin-Client vs. Fat-Client:** Thin-Client-Ansatz, um die Verarbeitung auf dem Server zu konzentrieren.
- **Stateless vs. Stateful Server-Design:** Der Server ist stateless.
- **Fehlersemantik:** Fehler werden dem Benutzer klar kommuniziert.
- **Idempotenz:** Nachrichtenübermittlung ist idempotent.
- **Skalierbarkeit:** Der Server unterstützt horizontale Skalierung für hohe Verbindungen.

## Use Cases

### Client Use Cases

1. **Mit Server verbinden:**
   - **Beschreibung:** Ein Benutzer verbindet sich mit dem Server durch Anmeldung oder Registrierung.
   - **Akteure:** Endbenutzer (Client)

2. **Verbindung zum Server trennen:**
   - **Beschreibung:** Ein Benutzer trennt die Verbindung zum Server, um die Sitzung zu beenden.
   - **Akteure:** Endbenutzer (Client)

3. **Freund hinzufügen:**
   - **Beschreibung:** Ein Benutzer fügt einen anderen Benutzer als Freund hinzu.
   - **Akteure:** Endbenutzer (Client)

4. **Freund entfernen:**
   - **Beschreibung:** Ein Benutzer entfernt einen Freund aus seiner Freundesliste.
   - **Akteure:** Endbenutzer (Client)

5. **Nachricht an Freund senden:**
   - **Beschreibung:** Ein Benutzer sendet eine Nachricht an einen Freund.
   - **Akteure:** Endbenutzer (Client)

6. **Gruppe erstellen:**
   - **Beschreibung:** Ein Benutzer erstellt eine neue Gruppe.
   - **Akteure:** Endbenutzer (Client)

7. **Gruppe entfernen:**
   - **Beschreibung:** Ein Benutzer entfernt eine bestehende Gruppe.
   - **Akteure:** Endbenutzer (Client)

8. **Nachricht an Gruppe senden:**
   - **Beschreibung:** Ein Benutzer sendet eine Nachricht an eine Gruppe.
   - **Akteure:** Endbenutzer (Client)

9. **Freund in Gruppe einladen:**
   - **Beschreibung:** Ein Benutzer lädt einen Freund in eine bestehende Gruppe ein.
   - **Akteure:** Endbenutzer (Client)

### Admin-Client Use Cases

1. **Mit Server verbinden:**
   - **Beschreibung:** Ein Administrator verbindet sich mit dem Server durch Anmeldung oder Registrierung.
   - **Akteure:** Administrator (Admin-Client)

2. **Verbindung zum Server trennen:**
   - **Beschreibung:** Ein Administrator trennt die Verbindung zum Server, um die Sitzung zu beenden.
   - **Akteure:** Administrator (Admin-Client)

3. **Freund hinzufügen:**
   - **Beschreibung:** Ein Administrator fügt einen anderen Benutzer als Freund hinzu (ähnlich wie der Client, jedoch möglicherweise zur Verwaltung von Benutzern).
   - **Akteure:** Administrator (Admin-Client)

4. **Freund entfernen:**
   - **Beschreibung:** Ein Administrator entfernt einen Freund aus einer Freundesliste (ähnlich wie der Client, jedoch zur Verwaltung von Benutzern).
   - **Akteure:** Administrator (Admin-Client)

5. **Nachricht an Freund senden:**
   - **Beschreibung:** Ein Administrator kann Nachrichten an Freunde senden (ähnlich wie der Client, jedoch möglicherweise zur Systemüberwachung).
   - **Akteure:** Administrator (Admin-Client)

6. **Gruppe erstellen:**
   - **Beschreibung:** Ein Administrator erstellt eine neue Gruppe (ähnlich wie der Client, jedoch zur Verwaltung des Systems).
   - **Akteure:** Administrator (Admin-Client)

7. **Gruppe entfernen:**
   - **Beschreibung:** Ein Administrator entfernt eine bestehende Gruppe (ähnlich wie der Client, jedoch zur Verwaltung des Systems).
   - **Akteure:** Administrator (Admin-Client)

8. **Nachricht an Gruppe senden:**
   - **Beschreibung:** Ein Administrator sendet Nachrichten an Gruppen (ähnlich wie der Client, zur Systemverwaltung).
   - **Akteure:** Administrator (Admin-Client)

9. **Freund in Gruppe einladen:**
   - **Beschreibung:** Ein Administrator lädt Freunde in Gruppen ein (ähnlich wie der Client, jedoch zur Systemverwaltung).
   - **Akteure:** Administrator (Admin-Client)

10. **System verwalten:**
    - **Beschreibung:** Ein Administrator konfiguriert und verwaltet Systemeinstellungen, Benutzerkonten und Systemressourcen.
    - **Akteure:** Administrator (Admin-Client)

11. **Benutzer und Clients managen:**
    - **Beschreibung:** Ein Administrator verwaltet Benutzerkonten, überprüft deren Status und verwaltet die Clients.
    - **Akteure:** Administrator (Admin-Client)

**User Stories (optional):**
- Als Benutzer möchte ich Nachrichten senden können, um mit Freunden zu kommunizieren.
- Als Benutzer möchte ich Nachrichten empfangen können, um über neue Nachrichten informiert zu werden.

**Use Case-Diagramm:**  
![Use Case Diagram](path/to/Use-Cases-diagram.png)

# Anforderungsübersicht

| **Anforderung**                                  | **Erfüllung** | **Erläuterung**                                                                                      |
|--------------------------------------------------|---------------|------------------------------------------------------------------------------------------------------|
| **MUST Have Anforderungen**                     |               |                                                                                                      |
| Textnachrichten versenden                        | Ja            | Implementiert durch TCP/IP-basierte Kommunikation.                                                   |
| Gruppenkommunikation                             | Ja            | Realisiert durch eine Gruppenchat-Funktionalität.                                                    |
| Nachrichtenaustausch bei Abwesenheit             | Ja            | Nachrichten werden zwischengespeichert und zugestellt, sobald der Empfänger online ist.              |
| Zugriff über Client-Anwendung                    | Ja            | Implementiert mit JavaFX für den Client-Zugang.                                                      |
| Admin-Client für Systemverwaltung                | Ja            | Admin-Client ermöglicht Konfiguration und Verwaltung.                                                |
| Eindeutige ID für Nutzer                         | Ja            | Jeder Nutzer hat eine eindeutige ID für die Adressierung.                                            |
| Command Line Interface                           | Ja            | Beide Clients (User und Admin) haben CLI-Schnittstellen.                                             |
| **SHOULD Have Anforderungen**                    |               |                                                                                                      |
| Parallelverarbeitung von Anfragen                | Ja            | Anfragen werden in separaten Threads verarbeitet.                                                    |
| Persistenz und Wiederherstellung                 | Ja            | Daten werden in MySQL gespeichert und bei Serverabsturz wiederhergestellt.                          |
| Überwachung und Statistik durch Admin-Client     | Ja            | Admin-Client bietet Statusüberwachung und Statistiken.                                               |
| Online-Status der Nutzer anzeigen                | Ja            | Echtzeit-Anzeige des Online-Status der Nutzer.                                                       |
| Benachrichtigungen über neue Nachrichten         | Ja            | Nutzer werden aktiv über neue Nachrichten informiert.                                                |
| **COULD Have Anforderungen**                     |               |                                                                                                      |
| Horizontal Skalierbarkeit                        | Nein          | Derzeit nicht umgesetzt.                                                                            |
| Erkennung und Behandlung von Nachrichtenverlusten| Nein          | Noch nicht implementiert.                                                                          |
| Logdateien für Zugriffsprotokollierung            | Nein          | Keine Logdateien für Zugriffe auf den Service vorhanden.                                             |
| Heartbeat-Mechanismus                            | Nein          | Derzeit nicht vorhanden.                                                                           |
| Nutzer-Suche nach Namen                          | Nein          | Suchfunktion nach Namen und Vornamen ist nicht implementiert.                                       |
| **++ Anforderungen**                            |               |                                                                                                      |
| Asynchrone Kommunikation                         | Ja            | Die Kommunikation zwischen Client und Server ist asynchron.                                          |
| Three-Tier-Architektur                           | Ja            | Datenbank ist auf einem separaten Server in einer Three-Tier-Architektur ausgelagert.                |
| Dezentrale Architektur ohne zentrale Verwaltungsinstanz | Ja        | Der Service besteht aus mehreren Instanzen ohne zentrale Verwaltung.                                 |


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



## Built With

- **Maven** - Dependency Management
- **Spring Boot** - Server-Framework
- **JavaFX** - Client-Technologie
- **MySQL** - Datenbank
