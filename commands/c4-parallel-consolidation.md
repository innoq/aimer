# C4 Documentation Consolidation

## Purpose
Consolidate results from parallel analysis agents into comprehensive C4 architecture documentation with consistent, cross-referenced content.

## Context
Multiple analysis agents provide different perspectives on the system. This agent synthesizes their findings into cohesive C4 documentation.

## Instructions

1. Validate and merge analysis results:
   - Check JSON schema compliance
   - Resolve conflicting information
   - Fill information gaps

2. Generate System Context (context.md):
   - Use business context from documentation scanner
   - Add external systems from all analyses
   - Create context diagram with Mermaid

3. Create Container View (containers.md):
   - Map services from static analysis
   - Add deployment info from infrastructure
   - Include technology choices

4. Develop Component View (components.md):
   - Focus on most critical container
   - Use static analysis patterns
   - Include internal structure

5. Build Deployment View (deployment.md):
   - Use infrastructure analysis data
   - Show all environments
   - Include scaling information

6. Document Decisions (decisions.md):
   - Extract from git history
   - Include ADRs from documentation
   - Add inferred decisions

7. Show Evolution (evolution.md):
   - Use git history timeline
   - Project future direction
   - Include migration paths

## Output Format

Seven markdown files with:
- Consistent formatting
- Cross-referenced sections
- Complete Mermaid diagrams
- Traceable to source analyses

## Success Criteria

- All analysis data incorporated
- No contradictions between sections
- Diagrams align with descriptions
- Complete C4 model coverage

$ARGUMENTS