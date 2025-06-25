# ADR Parallel Existing ADR Scanner

## Purpose

Scan repository for existing Architecture Decision Records and related architectural documentation to avoid duplication and maintain continuity.

## Context

This sub-agent searches for existing ADRs, architectural documentation, and decision logs to understand what has already been documented and ensure new ADRs build upon existing decisions.

## Instructions

1. **ADR Discovery**
   - Search for ADR directories (doc/adr, docs/adr, architecture/decisions)
   - Identify ADR files by naming patterns (adr-*.md, *.adr.md, [0-9]*.md)
   - Detect alternative decision documentation formats
   - Find architectural documentation in README files

2. **ADR Content Analysis**
   - Parse existing ADR structure and format
   - Extract decision status (proposed, accepted, deprecated, superseded)
   - Identify decision dates and authors
   - Analyze decision rationale and consequences

3. **Documentation Coverage**
   - Map which architectural areas are already documented
   - Identify gaps in current documentation
   - Find outdated or conflicting decisions
   - Detect superseded decisions needing updates

4. **Cross-References**
   - Identify ADRs that reference each other
   - Find external documentation references
   - Map decision dependencies
   - Detect broken or outdated links

5. **Documentation Standards**
   - Identify ADR template or format used
   - Detect numbering scheme
   - Analyze documentation quality and completeness
   - Find deviations from standard format

## Output Format

```json
{
  "existing_adrs": {
    "location": "<path_to_adr_directory>",
    "count": <number>,
    "format": "madr|nygard|custom",
    "numbering_scheme": "sequential|date-based|custom",
    "adrs": [
      {
        "number": "<adr_number>",
        "title": "<title>",
        "status": "proposed|accepted|deprecated|superseded",
        "date": "<ISO_date>",
        "file_path": "<relative_path>",
        "superseded_by": "<adr_number>",
        "supersedes": "<adr_number>",
        "areas_covered": ["<area1>", "<area2>"]
      }
    ]
  },
  "documentation_analysis": {
    "quality_score": "high|medium|low",
    "completeness": <percentage>,
    "last_updated": "<ISO_date>",
    "common_issues": [
      {
        "issue": "outdated|incomplete|conflicting|missing_rationale",
        "affected_adrs": ["<adr1>", "<adr2>"],
        "severity": "high|medium|low"
      }
    ]
  },
  "coverage_gaps": [
    {
      "area": "<architectural_area>",
      "description": "<what_is_missing>",
      "priority": "high|medium|low",
      "evidence": ["<file_or_component>"]
    }
  ],
  "related_documentation": [
    {
      "type": "readme|wiki|comments|design_doc",
      "location": "<file_path>",
      "architectural_content": "<summary>",
      "should_be_adr": true|false
    }
  ],
  "recommendations": {
    "next_adr_number": "<number>",
    "format_to_follow": "<template_reference>",
    "decisions_to_update": ["<adr1>", "<adr2>"],
    "decisions_to_supersede": ["<adr1>", "<adr2>"],
    "new_decisions_needed": ["<area1>", "<area2>"]
  }
}
```

## Success Criteria

- All existing ADRs discovered and cataloged
- Documentation quality and coverage assessed
- Gaps in architectural documentation identified
- Clear recommendations for new ADR numbers and format
- Output is valid JSON that can be processed by consolidator

## $ARGUMENTS