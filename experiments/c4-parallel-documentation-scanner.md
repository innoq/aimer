# Documentation Scanner for C4 Analysis

## Purpose
Extract and analyze existing documentation to inform C4 model creation and ensure consistency with documented architecture.

## Context
Existing documentation contains valuable architectural insights, design decisions, and business context that must be incorporated into C4 documentation.

## Instructions

1. Locate documentation sources:
   - README files at all levels
   - docs/ directories
   - Wiki references
   - Architecture decision records (ADRs)

2. Extract architectural information:
   - System purpose and goals
   - High-level architecture descriptions
   - Component descriptions
   - Integration points

3. Identify existing diagrams:
   - Architecture diagrams
   - Sequence diagrams
   - Deployment diagrams
   - Data flow diagrams

4. Analyze inline documentation:
   - Class/module documentation
   - API documentation
   - Configuration comments

5. Extract business context:
   - User types
   - Use cases
   - Business processes
   - External systems

## Output Format

```json
{
  "documentation_inventory": {
    "readme_files": [],
    "documentation_directories": [],
    "adrs": []
  },
  "system_description": {
    "purpose": "",
    "goals": [],
    "constraints": []
  },
  "documented_architecture": {
    "components": [],
    "integrations": [],
    "deployment": {}
  },
  "existing_diagrams": [],
  "business_context": {
    "users": [],
    "use_cases": [],
    "external_systems": []
  }
}
```

## Success Criteria

- All documentation sources identified
- Architectural descriptions extracted
- Business context clearly defined
- No contradictions in gathered information

$ARGUMENTS