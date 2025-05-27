# C4 Architecture Documentation - Parallel Analysis

## Purpose
Orchestrate parallel analysis of a Git repository to generate comprehensive C4 architecture documentation through specialized sub-agents.

## Context
Complex software systems require multi-faceted analysis to create accurate C4 documentation. This prompt coordinates multiple specialized agents working in parallel to analyze different aspects of the system, then consolidates their findings into complete C4 documentation.

## Instructions

1. Initialize parallel analysis by launching these specialized agents simultaneously:
   - Static Code Analyzer Agent (see c4-parallel-static-code-analyzer.md)
   - Git History Analyzer Agent (see c4-parallel-git-history-analyzer.md)
   - Documentation Scanner Agent (see c4-parallel-documentation-scanner.md)
   - Infrastructure Analyzer Agent (see c4-parallel-infrastructure-analyzer.md)

2. Collect and validate results from each agent in JSON format

3. Consolidate findings into a unified data model using the Consolidation Agent (see c4-parallel-consolidation.md)

4. Generate C4 documentation files based on consolidated data:
   - README.md
   - context.md
   - containers.md
   - components.md
   - deployment.md
   - decisions.md
   - evolution.md

## Output Format

Seven markdown files containing:
- Complete C4 model documentation
- Embedded Mermaid diagrams
- Cross-referenced insights from all analysis agents
- Structured according to C4 model standards

## Success Criteria

- All four analysis agents complete successfully
- JSON results are valid and complete
- Generated documentation covers all C4 viewpoints
- Mermaid diagrams render correctly
- No conflicting information between sections

$ARGUMENTS