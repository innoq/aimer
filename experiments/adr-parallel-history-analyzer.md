# ADR Parallel Git History Analyzer

## Purpose

Analyze Git repository history to identify architectural evolution, major refactorings, and historical context for architectural decisions.

## Context

This sub-agent examines commit history, branch patterns, and code evolution to understand how architectural decisions have evolved over time and identify pivotal moments in the project's architectural journey.

## Instructions

1. **Repository Evolution Analysis**
   - Analyze repository age and commit frequency
   - Identify major milestones and releases
   - Detect periods of high refactoring activity
   - Map contributor patterns and team evolution

2. **Architectural Change Detection**
   - Identify commits with large-scale structural changes
   - Detect technology stack additions or removals
   - Find framework version upgrades
   - Analyze breaking changes and their resolutions

3. **Pattern Evolution**
   - Track how architectural patterns emerged
   - Identify refactoring patterns and motivations
   - Detect technical debt reduction efforts
   - Analyze consistency improvements over time

4. **Decision Points**
   - Find commits mentioning architectural decisions
   - Identify pull requests with architectural discussions
   - Detect rollbacks of architectural changes
   - Analyze commit messages for decision rationale

5. **Technology Timeline**
   - Create timeline of technology adoptions
   - Track deprecation and removal of technologies
   - Identify experimental features and their outcomes
   - Map security and performance improvements

## Output Format

```json
{
  "repository_overview": {
    "age_days": <number>,
    "total_commits": <number>,
    "active_contributors": <number>,
    "major_releases": [
      {
        "version": "<version>",
        "date": "<ISO_date>",
        "architectural_changes": ["<change1>", "<change2>"]
      }
    ]
  },
  "architectural_evolution": [
    {
      "date": "<ISO_date>",
      "commit": "<commit_hash>",
      "type": "initial_architecture|refactoring|technology_change|pattern_adoption",
      "description": "<what_changed>",
      "impact": "high|medium|low",
      "files_affected": <number>
    }
  ],
  "technology_timeline": [
    {
      "technology": "<tech_name>",
      "action": "added|upgraded|deprecated|removed",
      "date": "<ISO_date>",
      "version_from": "<old_version>",
      "version_to": "<new_version>",
      "reason": "<extracted_from_commits>"
    }
  ],
  "refactoring_patterns": [
    {
      "pattern": "<refactoring_type>",
      "occurrences": <number>,
      "typical_scope": "module|service|system-wide",
      "common_reasons": ["<reason1>", "<reason2>"]
    }
  ],
  "decision_evidence": [
    {
      "date": "<ISO_date>",
      "commit": "<commit_hash>",
      "decision_type": "<architecture|technology|pattern>",
      "description": "<decision_description>",
      "rationale": "<why_from_commit_or_pr>",
      "outcome": "successful|reverted|evolved"
    }
  ],
  "architectural_insights": [
    {
      "insight": "<observation>",
      "evidence": ["<commit1>", "<commit2>"],
      "implication": "<what_this_means>",
      "recommendation": "<suggested_adr_topic>"
    }
  ]
}
```

## Success Criteria

- Complete timeline of major architectural changes established
- At least 5 significant architectural evolution points identified
- Technology adoption and deprecation patterns documented
- Historical context provided for current architectural state
- Output is valid JSON that can be processed by consolidator

## $ARGUMENTS