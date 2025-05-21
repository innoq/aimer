# Product Backlog Workflow

Dieser Prompt führt dich durch einen strukturierten Prozess zur Erstellung eines umfassenden Produkt-Backlogs basierend auf einer zentralen CSV-Datei. Er verarbeitet die Datei `docs/product/backlog/user-stories-mvp.csv` und erstellt daraus zunächst Feature-Beschreibungen und anschließend detaillierte User Stories mit Hilfe des `./.claude/commands/create_user_story.md` Commands.

## Eingabevariablen

- **start_index:** [Optional: Index, ab dem die Verarbeitung starten soll (Standard: 0)]
- **max_stories:** [Optional: Maximale Anzahl der zu verarbeitenden Stories pro Durchlauf (Standard: 10)]
- **session:** [Optional: Neue Session (new), fortgesetzte Session (continue) oder finale Session (final)]

## Workflow-Management

Vor Beginn jeder Backlog-Erstellung-Session:

1. **Workflow-Status prüfen**
   - Prüfe, ob ein Index-Dokument unter `docs/product/backlog/README.md` existiert
   - Falls ja, analysiere den aktuellen Stand und identifiziere die bereits abgeschlossenen Stories
   - Falls nein und es handelt sich um eine neue Session, erstelle ein grundlegendes Index-Dokument

2. **Progressives Index-Dokument**
   - Das Index-Dokument dient sowohl als Dokumentationseinstieg als auch als Fortschrittsindikator
   - Nach jedem abgeschlossenen Verarbeitungsschritt aktualisiere das Index-Dokument mit:
     - Den neu erstellten User Stories
     - Einem aktualisierten Fortschrittsindikator, der zeigt, welche Stories bereits verarbeitet wurden
   - Speichere das aktualisierte Index-Dokument, um den Fortschritt zwischen Sessions zu erhalten

## CSV-Datei und Struktur

Die CSV-Datei hat die folgende Struktur:
```
User Activity,User Task,Story,Category,Source
"Discover & Browse Prompts","Search for prompts","As a technical consultant, I want to search for prompts by keywords so that I can quickly find relevant prompts during client meetings",MVP,"Prompt Management"
```

Dabei gilt:
- User Activity: Die übergeordnete Nutzeraktivität/Epic (z.B. "Discover & Browse Prompts")
- User Task: Die spezifische Aufgabe/Feature (z.B. "Search for prompts")
- Story: Die User Story im Format "As a [persona], I want to [action] so that [benefit]"
- Source: Herkunft der Story (z.B. "Prompt Management")

## Workflow-Schritte

1. **Initialisierung**
   - Bei einer neuen Session (`session=new`):
     - Erstelle die Verzeichnisse `docs/product/backlog/features/` und `docs/product/backlog/user-stories/` wenn sie nicht existieren
     - Erstelle ein initiales README.md als Index-Dokument
     - Prüfe, ob die CSV-Datei `docs/product/backlog/user-stories-mvp.csv` existiert

   - Bei einer fortgesetzten Session (`session=continue`):
     - Lese das existierende Index-Dokument, um den Fortschritt zu ermitteln
     - Identifiziere den nächsten zu verarbeitenden Start-Index

2. **CSV-Datei Verarbeitung**
   - Lese und parse die CSV-Datei `docs/product/backlog/user-stories-mvp.csv`
   - Beginne die Verarbeitung beim angegebenen `start_index`

3. **Story-Verarbeitung**
   - Verarbeite bis zu `max_stories` Zeilen aus der CSV-Datei:
     - Extrahiere User Activity (Epic), User Task (Feature), Story, Category und Source
     - Identifiziere die im Story-Text erwähnte Persona (z.B. "technical consultant")
     - Extrahiere den Inhalt der entsprechenden Persona-Datei (z.B. `docs/product/proto-personas/technical-consultant.md`)
     - Erstelle eine Feature-Beschreibung, die folgendes beinhaltet und speichere sie unter `docs/product/backlog/features/{zeilennummer}.md`:
       ```
       # Feature: [Task] innerhalb von [Activity]
       
       Diese Feature ermöglicht es [Persona], [Aktion durchzuführen] im Kontext von [Activity].
       
       ## Kontext
       Das Feature ist Teil der übergeordneten Aktivität "[Activity]" und fokussiert sich auf die Aufgabe "[Task]".
       
       ## User Story
       [Original Story]
       
       ## Priorität
       [Category]
       
       ## Quelle
       [Source]
       
       ## Produktkontext
       Dieses Feature sollte in die bestehende Promptwerk-Anwendung integriert werden und mit den bestehenden Funktionen zur [relevante Funktionen] zusammenarbeiten.
       ```
     - Rufe den `./.claude/commands/create_user_story.md` Claude Command bzw. Prompt auf mit:
       - Dem Persona-Inhalt als {{PERSONA}}
       - Der generierten Feature-Beschreibung als {{FEATURE_DESCRIPTION}}
     - Speichere die generierte User Story unter `docs/product/backlog/user-stories/{zeilennummer}.md`

4. **Backlog-Organisation**
   - Organisiere die generierten User Stories im Index-Dokument nach:
     - Priorität (MVP vor Future)
     - Epic (User Activity)
     - Feature (User Task)

5. **Fortschritts-Tracking**
   - Aktualisiere das Index-Dokument nach jedem Durchlauf mit:
     - Status-Update in der Fortschrittstabelle
     - Aktuellem Verarbeitungsindex und Gesamtzahl der Stories
     - Generiere einen Befehl zur Fortsetzung der Verarbeitung

## Backlog Index-Dokument

**Initiales Index-Dokument** (bei Beginn eines neuen Backlog oder fortgesetzter Session)
- Erstelle ein Index-Dokument mit folgender Struktur:
  ```markdown
  # Promptwerk MVP Product Backlog

  ## Überblick
  Dieses Dokument verfolgt den Fortschritt der Backlog-Erstellung aus der User Stories CSV-Datei.

  ## Verarbeitungsfortschritt

  | Verarbeitet | Gesamtzahl | Status | Letzte Aktualisierung |
  |-------------|------------|--------|------------------------|
  | 0/241 | 241 | ⏳ In Bearbeitung | 2023-05-06 |

  ## MVP Stories

  ### Epic: [User Activity 1]

  #### Feature: [User Task 1]

  ##### Story: [Story title]
  [Detaillierte User Story]

  ## Nächste Schritte
  Verwende den folgenden Befehl zur Fortsetzung der Verarbeitung:
  ```
  /generate_backlog_workflow start_index=5 max_stories=10 session=continue
  ```
  ```

## Progressives Update (nach jedem abgeschlossenen Analyseschritt)
- Aktualisiere das Index-Dokument mit:
  - Status-Update in der Fortschrittstabelle
  - Neuen generierten User Stories
  - Befehl zur Fortsetzung der Verarbeitung

## Finales Index-Dokument (nach Abschluss aller Verarbeitungen)
- Ergänze das Index-Dokument um:
  - Einen umfassenden Überblick über den erstellten Backlog
  - Zusammenfassung der wichtigsten Erkenntnisse
  - Vollständigen Status aller verarbeiteten Stories (alle auf ✅ Abgeschlossen)

## Beispielaufruf

Für den ersten Durchlauf:
```
/generate_backlog_workflow session=new
```

Für fortgesetzte Durchläufe:
```
/generate_backlog_workflow start_index=5 max_stories=10 session=continue
```

Für den finalen Abschluss:
```
/generate_backlog_workflow session=final
```

## Workflow-Implementierung

Folge diesen Schritten zur Umsetzung des Workflows:

1. **Initialisierung**
   - Erstelle notwendige Verzeichnisse (features und user-stories)
   - Erstelle oder aktualisiere das Index-Dokument

2. **CSV Verarbeitung**
   - Verarbeite die CSV-Datei `docs/product/backlog/user-stories-mvp.csv`
   - Extrahiere und verarbeite Stories

3. **Feature-Beschreibungen und User Story Generierung**
   - Erstelle für jede Story eine Feature-Beschreibung unter `docs/product/backlog/features/{zeilennummer}.md`
   - Rufe den ./.claude/commands/create_user_story.md Command bzw. Prompt auf
   - Speichere die generierte User Story unter `docs/product/backlog/user-stories/{zeilennummer}-{storyname}.md`, wobei der Storyname im Kebab-Case gehalten ist und Umlaute ausgeschrieben werden
   - Strukturiere die generierten Stories in einem organisierten Backlog

4. **Fortschrittsverfolgung**
   - Aktualisiere das Index-Dokument mit dem aktuellen Fortschritt
   - Generiere den Befehl für den nächsten Durchlauf

Starte den Workflow entsprechend der angegebenen Parameter. Bitte schreibe keine Skripte, sondern löse diese Aufgabe wie beschrieben.