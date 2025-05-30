# Git History Analysis for C4 Documentation

## Purpose
Analyze Git commit history to understand system evolution, identify architectural decisions, and detect development patterns for C4 documentation.

## Context
Git history provides temporal insights about architectural changes, team structure, and system evolution that enrich C4 documentation with historical perspective.

## Instructions

1. Analyze commit patterns:
   - Frequency by component/directory
   - Commit message categorization
   - Release patterns

2. Identify development focus areas:
   - Most frequently modified files
   - Hotspot detection
   - Coupled file changes

3. Extract architectural changes:
   - Major refactoring commits
   - New component introductions
   - Deprecated component removals

4. Map contributor expertise:
   - Primary contributors by component
   - Knowledge distribution
   - Team boundaries

5. Detect evolution trends:
   - Growth patterns
   - Technology migrations
   - Architecture style changes

## Output Format

```json
{
  "commit_analysis": {
    "total_commits": 0,
    "date_range": {},
    "commit_categories": {}
  },
  "hotspots": [],
  "architectural_changes": [
    {
      "date": "",
      "type": "refactoring|new_component|removal",
      "description": "",
      "impact": ""
    }
  ],
  "contributor_map": {},
  "evolution_patterns": {
    "growth_trend": "",
    "architectural_shifts": []
  }
}
```

## Success Criteria

- Complete commit history analyzed
- Major architectural changes identified
- Clear evolution timeline established
- Hotspots accurately detected

$ARGUMENTS