# ADR Parallel Consolidator

## Purpose

Consolidate outputs from all ADR analysis sub-agents into a comprehensive set of Architecture Decision Records, writing them as markdown files to the specified target directory.

## Context

This consolidation agent receives JSON outputs from multiple parallel analyzers and the target directory path. It synthesizes the analysis results into well-structured ADR markdown files, ensuring consistency, avoiding duplication, and maintaining proper cross-references.

## Instructions

1. **Input Processing**
   - Receive target directory path from orchestrator
   - Verify all expected sub-agent outputs are present
   - Handle missing or partial results gracefully
   - Validate JSON structure from each sub-agent
   - Create target directory if it doesn't exist

2. **Decision Synthesis**
   - Merge related findings from different analyzers
   - Identify overlapping or duplicate decisions
   - Prioritize decisions by impact and evidence strength
   - Group related decisions appropriately

3. **ADR File Generation**
   - Follow existing ADR format if found, otherwise use MADR
   - Assign appropriate ADR numbers based on existing sequence
   - Create clear, concise titles for each decision
   - Write each ADR as a separate markdown file in the target directory
   - Use filename format: `NNNN-title-with-hyphens.md`

4. **Cross-Reference Management**
   - Link related ADRs appropriately
   - Update superseded decisions
   - Create decision dependency maps
   - Ensure bidirectional references

5. **Quality Assurance**
   - Verify each ADR has complete sections
   - Ensure rationale is evidence-based
   - Check for conflicting decisions
   - Validate consequences are realistic

## Output Format

1. **ADR Files**: Write each ADR as a markdown file to the target directory with this structure:

```markdown
# <ADR-NUMBER>. <Title>

Date: <YYYY-MM-DD>

## Status

<Proposed|Accepted|Deprecated|Superseded>

## Context

<Comprehensive background explaining why this decision is needed>

## Decision

<Clear statement of the architectural decision made>

## Rationale

<Evidence-based explanation including:>
- Technical reasons from static analysis
- Operational considerations from infrastructure analysis
- Data/API requirements from integration analysis
- Historical context from git history
- Team and project constraints

## Consequences

### Positive
- <Positive outcome 1>
- <Positive outcome 2>

### Negative
- <Negative outcome or trade-off 1>
- <Negative outcome or trade-off 2>

### Neutral
- <Neutral impact or consideration>

## References

- <Related ADRs>
- <External documentation>
- <Relevant commits or PRs>
```

2. **Return JSON Summary**:

```json
{
  "target_directory": "<path>",
  "generation_timestamp": "<ISO_8601>",
  "total_adrs_generated": <number>,
  "generated_files": [
    {
      "filename": "0001-use-postgresql-database.md",
      "title": "Use PostgreSQL as Primary Database",
      "status": "Accepted",
      "category": "data-management",
      "confidence": "high"
    }
  ],
  "coverage": {
    "areas_documented": ["database", "architecture", "security"],
    "gaps_remaining": ["monitoring", "backup-strategy"]
  },
  "quality_metrics": {
    "average_evidence_sources": 3.5,
    "decisions_with_rationale": 100,
    "decisions_with_consequences": 100
  }
}
```

## Success Criteria

- Target directory created and populated with ADR markdown files
- All significant architectural decisions documented as separate files
- Each ADR follows consistent format and sequential numbering
- Clear rationale provided based on analyzer evidence
- Proper cross-references between related decisions
- No duplicate or conflicting ADRs generated
- JSON summary accurately reflects generated files

## $ARGUMENTS

Input: JSON object containing target directory path and all sub-agent analysis results