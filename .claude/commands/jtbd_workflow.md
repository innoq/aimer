# JTBD Workflow

Dieser Prompt führt dich durch einen strukturierten Prozess zur Erstellung einer umfassenden Jobs-to-be-Done Dokumentation. Er verwendet die spezialisierten JTBD-Prompts in `./.claude/commands/` und führt sie in der optimalen Reihenfolge aus.

## Eingabevariablen

- **End User:** [Wer führt den Job aus?]
- **Job:** [Der Hauptjob, der erledigt werden soll]
- **Focus:** [B2C für Verbraucherkontext, B2B für Geschäftskontext, NA für funktionale Analyse]
- **Product/Service:** [Optional: Die Lösung, für die JTBD-Analysen durchgeführt werden]
- **Domain:** [Optional: Der Bereichskontext, in dem der Job stattfindet]
- **Session:** [Optional: Aktueller Stand des Workflows - neu, fortgesetzt oder abschließend]

## Workflow-Management

Vor Beginn jeder JTBD-Analyse-Session:

1. **Workflow-Status prüfen**
   - Prüfe, ob ein Index-Dokument unter `docs/domain/jtbd/README.md` existiert
   - Falls ja, analysiere den aktuellen Stand und identifiziere die bereits abgeschlossenen Schritte
   - Falls nein und es handelt sich nicht um eine neue Analyse, erstelle ein grundlegendes Index-Dokument

2. **Progressives Index-Dokument**
   - Das Index-Dokument dient sowohl als Dokumentationseinstieg als auch als Fortschrittsindikator
   - Nach jedem abgeschlossenen Analyseschritt aktualisiere das Index-Dokument mit:
     - Einer kurzen Zusammenfassung der neuen Erkenntnisse
     - Links zum neuen Dokument
     - Einem aktualisierten Fortschrittsindikator, der zeigt, welche Schritte bereits abgeschlossen wurden
   - Speichere das aktualisierte Index-Dokument, um den Fortschritt zwischen Sessions zu erhalten

## Basis-Workflow-Schritte

1. **Jobs and Performers** (`./.claude/commands/jtbd_jobs_and_performers.md`)
   - Input: Domain, Focus, Market, Number of Jobs
   - Output: Grundlegende Jobs und ihre Ausführenden
   - Zweck: Identifiziert zentrale Jobs im Anwendungsbereich

2. **Job Contexts** (`./.claude/commands/jtbd_job_contexts.md`)
   - Input: End User, Job, Focus
   - Output: Verschiedene Kontexte, in denen der Job ausgeführt wird
   - Zweck: Grenzt den Umfang deiner Untersuchung ein

3. **Job Maps** (`./.claude/commands/jtbd_job_map.md`)
   - Input: End User, Job, Kontext, Focus, Fidelity
   - Output: Grundlegende Job Map mit 9 Phasen
   - Zweck: Erstellt das Grundgerüst für weitere Analysen

4. **Broaden the level of abstraction** (`./.claude/commands/jtbd_broaden_abstraction.md`)
   - Input: End User, Job, Kontext (aus Schritt 2), Focus
   - Output: Übergeordnete Ziele hinter dem Job
   - Zweck: Erfasst den strategischen Kontext

5. **Narrow the level of abstraction** (`./.claude/commands/jtbd_narrow_abstraction.md`)
   - Input: End User, Job, Kontext (aus Schritt 2), Focus
   - Output: Konkretere Teilaufgaben
   - Zweck: Entwickelt detaillierteres Verständnis

## Erweiterte Analyse

6. **Job Hierarchies** (`./.claude/commands/jtbd_job_hierarchies.md`)
   - Input: End User, Product/Service, Focus, Context
   - Output: Hierarchische Struktur von Jobs auf verschiedenen Abstraktionsebenen
   - Zweck: Zeigt Zusammenhänge zwischen strategischen und taktischen Jobs

7. **Related Jobs** (`./.claude/commands/jtbd_related_jobs.md`)
   - Input: End User, Job, Kontext, Focus
   - Output: Vor, während und nach dem Haupt-Job auftretende Aufgaben
   - Zweck: Identifiziert angrenzende Aktivitäten

8. **Situational Factors** (`./.claude/commands/jtbd_situational_factors.md`)
   - Input: End User, Job, Kontext, Focus
   - Output: Externe Faktoren, die den Job beeinflussen
   - Zweck: Erfasst Umgebungsvariablen

## Ergebnis- und Erfolgsmessung

9. **Outcome Statements** (`./.claude/commands/jtbd_outcome_statements.md`)
   - Input: End User, Job, Kontext, Focus, Number of statements
   - Output: Gewünschte Ergebnisse und Erfolgsmetriken
   - Zweck: Definiert messbare Kundenerwartungen

10. **Success Metrics** (`./.claude/commands/jtbd_success_metrics.md`)
    - Input: End User, Job, Kontext, Focus, Schritte aus der Job Map
    - Output: Erfolgsmetriken für jeden Schritt
    - Zweck: Definiert konkrete Erfolgskriterien

11. **Unmet Needs** (`./.claude/commands/jtbd_unmet_needs.md`)
    - Input: End User, Job, Kontext, Focus, Number of needs
    - Output: Unerfüllte Kundenbedürfnisse
    - Zweck: Identifiziert Innovationspotenzial

## Nutzerperspektive

12. **Job Personas** (`./.claude/commands/jtbd_job_personas.md`)
    - Input: End User Category, Job, Context, Number of Personas, Focus
    - Output: Archetypen von Nutzern basierend auf ihrem Jobansatz
    - Zweck: Repräsentiert verschiedene Nutzergruppen

13. **Job Stories** (`./.claude/commands/jtbd_job_stories.md`)
    - Input: End User, Job, Context, Product/Service, Categories, Stories per category, Focus
    - Output: Kontextbasierte Job-Geschichten
    - Zweck: Beschreibt situative Nutzeranwendungen

14. **Emotional Jobs** (`./.claude/commands/jtbd_emotional_jobs.md`)
    - Input: End User, Job, Kontext, Focus
    - Output: Emotionale Bedürfnisse während der Ausführung
    - Zweck: Erfasst emotionale Aspekte

15. **Social Jobs** (`./.claude/commands/jtbd_social_jobs.md`)
    - Input: End User, Job, Kontext, Focus
    - Output: Soziale Aspekte und Wahrnehmungsziele
    - Zweck: Analysiert Interaktionsbedürfnisse

## Lösungs- und Umsetzungsstrategie

16. **Approaches** (`./.claude/commands/jtbd_approaches.md`)
    - Input: End User, Schritte aus der Job Map, Job Kontext
    - Output: Lösungsansätze für jeden Schritt
    - Zweck: Entwickelt Umsetzungsstrategien

17. **Financial Metrics** (`./.claude/commands/jtbd_financial_metrics.md`)
    - Input: End User, Job, Kontext, Focus
    - Output: Finanzielle Aspekte und TCO
    - Zweck: Bewertet ökonomische Faktoren

18. **Potential Jobs of a Solution** (`./.claude/commands/jtbd_potential_jobs.md`)
    - Input: End User, Product/Lösung
    - Output: Jobs, die durch eine Lösung unterstützt werden könnten
    - Zweck: Validiert Lösungsansätze

19. **Forces Diagram** (`./.claude/commands/jtbd_forces_diagram.md`)
    - Input: End User, Job, Context, Solution/Product, Focus
    - Output: Analyse der Kräfte, die Adoption fördern oder hemmen
    - Zweck: Visualisiert Entscheidungsfaktoren

## Marktforschung und Validierung

20. **Profiling & Screening Accelerator** (`./.claude/commands/jtbd_profiling_screening.md`)
    - Input: End User, Job, Kontext, Focus
    - Output: Screening-Fragen für Forschung
    - Zweck: Bereitet Nutzerforschung vor

21. **Survey Design** (`./.claude/commands/jtbd_survey.md`)
    - Input: End User, Job, Context, Focus, Language
    - Output: Umfassende JTBD-Umfrage
    - Zweck: Ermöglicht quantitative Validierung

## Ergebnisintegration

Die Ergebnisse aus allen Schritten bilden zusammen eine umfassende JTBD-Dokumentation, die als Grundlage für Produktentwicklung, Marketing und Kundenkommunikation dienen kann. Speichere die Ergebnisse jedes Schritts in einem einheitlichen Markdown Format unter:
- Basis-Analysen und Erweiterte Dokumentation unter `docs/domain/jtbd/`

## JTBD Dokumentations-Index

22. **JTBD Index Erstellung und Pflege**
    - **Initiales Index-Dokument** (bei Beginn einer neuen JTBD-Analyse oder fortgesetzter Session)
      - Erstelle ein Index-Dokument, das die Basis-Informationen und geplante Analyseschritte enthält
      - Folgende Struktur verwenden:
        ```markdown
        # JTBD Analyse: [Job]
        
        ## End User
        [End User Beschreibung]
        
        ## Job
        [Job Beschreibung]
        
        ## Kontext
        [Kontext Beschreibung]
        
        ## Analyse-Fortschritt
        
        | Analyse-Schritt | Status | Dokument | Letzte Aktualisierung |
        |-----------------|--------|----------|------------------------|
        | Jobs and Performers | ❌ | - | - |
        | Job Contexts | ❌ | - | - |
        | ... | ... | ... | ... |
        
        ## Vorläufige Erkenntnisse
        [Wird mit fortschreitender Analyse aktualisiert]
        ```
      
    - **Progressives Update** (nach jedem abgeschlossenen Analyseschritt)
      - Aktualisiere das Index-Dokument mit:
        - Status-Update in der Fortschrittstabelle (❌ → ✅)
        - Link zum erstellten Dokument
        - Datum der letzten Aktualisierung
        - Kurze Zusammenfassung der neuen Erkenntnisse im Abschnitt "Vorläufige Erkenntnisse"
      
    - **Finales Index-Dokument** (nach Abschluss aller gewünschten Analysen)
      - Ergänze das Index-Dokument um:
        - Einen umfassenden Überblick über den analysierten Job und Kontext
        - Eine detaillierte Zusammenfassung der wichtigsten Erkenntnisse aus allen Analysen
        - Links zu allen erstellten Dokumenten mit Kurzbeschreibungen
        - Empfohlene Lesereihenfolge für verschiedene Anwendungsfälle
        - Visuelle Darstellung der Jobhierarchie und Zusammenhänge (falls möglich)
      
    - Speichere das Index-Dokument nach jedem Update als:
      - `docs/domain/jtbd/README.md`

## Hinweise zur Anwendung

- Der Workflow ist modular – du kannst mit einzelnen Schritten beginnen und je nach Bedarf weitere hinzufügen
- Jeder Schritt baut auf den Ergebnissen der vorherigen Schritte auf
- Verwende für jeden Schritt den entsprechenden spezialisierten Prompt
- Passe die Parameter (wie n=Anzahl der zu generierenden Items) je nach Bedarf an
- Nicht alle Schritte sind für jedes Projekt notwendig – wähle die relevantesten aus
- Für tiefere Analysen von Job-Schritten wiederhole den entsprechenden Prompt für jeden einzelnen Schritt
- **Wichtig für kontinuierliche Arbeit**: Aktualisiere das Index-Dokument nach jedem abgeschlossenen Schritt, damit der Fortschritt über mehrere Sessions hinweg nachvollziehbar bleibt und die Analyse bei Bedarf fortgesetzt werden kann
- Bei Fortführung einer unterbrochenen Analyse, prüfe immer zuerst das Index-Dokument, um den aktuellen Stand zu ermitteln und sinnvoll fortzufahren