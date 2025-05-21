# JTBD Resume Workflow

Dieser Prompt hilft dir, einen bereits begonnenen JTBD-Analyseprozess wieder aufzunehmen und fortzuführen. Er baut auf dem existierenden Index-Dokument auf, um den aktuellen Stand zu erfassen und die nächsten Schritte zu planen.

## Eingabevariablen

- **Index File Path:** [Pfad zur README.md oder Index-Datei, z.B. docs/domain/jtbd/README.md]
- **Focus:** [B2C für Verbraucherkontext, B2B für Geschäftskontext, NA für funktionale Analyse]
- **Priority Steps:** [Optional: Spezifische Analyse-Schritte, die priorisiert werden sollen]
- **Session Goal:** [Optional: Anzahl der Schritte oder spezifische Ergebnisse für diese Session]

## Workflow-Wiederaufnahme

1. **Status Evaluation**
   - Analysiere das angegebene Index-Dokument, um den aktuellen Stand des JTBD-Analyseprozesses zu bestimmen
   - Identifiziere:
     - Bereits abgeschlossene Schritte (markiert mit ✅)
     - Ausstehende Schritte (markiert mit ❌)
     - Vorhandene End User, Job und Kontext-Definitionen
     - Bisher gesammelte Erkenntnisse

2. **Kontext-Wiederherstellung**
   - Lese die relevanten vorhandenen Dokumente, um Kontext und bisherige Erkenntnisse zu verstehen
   - Stelle die wichtigsten Parameter wieder her:
     - End User und dessen Merkmale
     - Job-Definition und -Umfang
     - Kontext-Spezifikationen
     - Annahmen und Rahmenbedingungen

3. **Priorisierung der nächsten Schritte**
   - Identifiziere die logisch nächsten Schritte basierend auf:
     - Natürlicher Progression der JTBD-Analyse
     - Vom Benutzer angegebenen Prioritäten
     - Aktuellen Lücken in der Analyse
     - Potenzial für wertvollen Erkenntnisgewinn

4. **Fortführungsplan**
   - Erstelle einen konkreten Plan für die Fortführung der Analyse mit:
     - Spezifischen nächsten Schritten
     - Erforderlichen Inputs für jeden Schritt
     - Erwarteten Outputs
     - Geschätztem Aufwand

## Ausführungsphase

Für jeden priorisierten, noch nicht abgeschlossenen Schritt:

1. **Parameter Preparation**
   - Sammle und bereite alle notwendigen Parameter für den entsprechenden Prompt vor
   - Stelle sicher, dass alle erforderlichen Informationen aus vorherigen Analysen verfügbar sind

2. **Prompt Execution**
   - Führe den entsprechenden spezialisierten Prompt aus `./.claude/commands/` aus
   - Verwende die in Schritt 1 vorbereiteten Parameter
   - Speichere die Ergebnisse im richtigen Verzeichnis

3. **Index-Aktualisierung**
   - Aktualisiere das Index-Dokument mit:
     - Status-Update in der Fortschrittstabelle (❌ → ✅)
     - Link zum neuen Dokument
     - Datum der Aktualisierung
     - Kurzer Zusammenfassung der neuen Erkenntnisse

4. **Fortschrittsüberprüfung**
   - Bewerte den Gesamtfortschritt im Hinblick auf:
     - Vollständigkeit der Analyse
     - Qualität der gewonnenen Erkenntnisse
     - Kohärenz zwischen den verschiedenen Analyseschritten
     - Erreichen des Session-Ziels

## Abschluss der Session

Nach Abschluss der Session oder Erreichen des Session-Ziels:

1. **Zusammenfassung der Session**
   - Erstelle eine kurze Zusammenfassung der in dieser Session:
     - Abgeschlossenen Schritte
     - Gewonnenen Haupterkenntnisse
     - Identifizierten neuen Fragen oder Richtungen

2. **Final Index-Update**
   - Führe ein abschließendes Update des Index-Dokuments durch:
     - Aktualisiere den Abschnitt "Vorläufige Erkenntnisse"
     - Ergänze Empfehlungen für die nächste Session
     - Speichere das Index-Dokument in beiden Verzeichnissen

3. **Nächste Schritte**
   - Empfehle die nächsten zu priorisierenden Schritte für zukünftige Sessions
   - Identifiziere potenzielle Bereiche für tiefere Analyse
   - Schlage mögliche Anwendungen der bisherigen Erkenntnisse vor

## Prozesshinweise

- Stelle sicher, dass alle Parameter für die JTBD-Prompts aus dem Index-Dokument oder den bestehenden Analysen entnommen werden, um Konsistenz zu gewährleisten
- Priorisiere "Basis-Workflow-Schritte" vor "Erweiterten Analysen", wenn diese noch nicht abgeschlossen sind
- Achte darauf, dass die neuen Analysen konsistent mit den bereits vorhandenen Erkenntnissen sind
- Bei Inkonsistenzen oder widersprüchlichen Erkenntnissen, dokumentiere diese und schlage Anpassungen vor
- Halte das Index-Dokument als zentralen Referenzpunkt laufend aktuell
- Verwende die in der ursprünglichen Analyse verwendete Sprache und Terminologie

## Ausführungsbeispiel

1. Analysiere Index-Dokument und identifiziere ausstehende Schritte
2. Priorisiere nächsten Schritt (z.B. "Unmet Needs")
3. Führe entsprechenden Prompt aus (z.B. `./.claude/commands/jtbd_unmet_needs.md`)
4. Speichere Ergebnis im richtigen Verzeichnis
5. Aktualisiere Index-Dokument mit neuem Status und Erkenntnissen
6. Wiederhole für weitere Schritte je nach Session-Ziel
7. Erstelle abschließende Zusammenfassung und aktualisiere Index-Dokument final