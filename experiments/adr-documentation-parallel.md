# Architecture Decision Records (ADR) Parallel Documentation

## Purpose

Orchestrate parallel analysis of a software repository to identify and document key architectural decisions through Architecture Decision Records (ADRs).

## Context

This prompt coordinates multiple specialized sub-agents to analyze different aspects of a codebase in parallel. Each sub-agent focuses on specific architectural concerns, and their findings are consolidated into comprehensive ADR documentation. The generated ADRs are written as markdown files to a specified target directory.

## Instructions

1. **Extract Target Directory**
   - Parse the target directory path from $ARGUMENTS
   - Create the target directory if it doesn't exist
   - Write the target directory path to `./.adr-dir` file in the repository root

2. **Initialize Analysis Context**
   - Identify repository type and primary technology stack
   - Determine analysis scope and priorities
   - Prepare workspace for parallel execution

3. **Deploy Parallel Sub-Agents**
   Initialize parallel analysis by launching these specialized agents simultaneously:
   - Static Code Analyzer Agent (see adr-parallel-static-analyzer.md)
   - Infrastructure Analyzer Agent (see adr-parallel-infrastructure-analyzer.md)
   - Data and API Analyzer Agent (see adr-parallel-data-api-analyzer.md)
   - Git History Analyzer Agent (see adr-parallel-history-analyzer.md)
   - Existing ADR Scanner Agent (see adr-parallel-existing-adr-scanner.md)

4. **Coordinate Results**
   - Monitor sub-agent progress
   - Handle any analysis failures gracefully
   - Ensure all critical areas are covered

5. **Consolidate Findings**
   - Collect and validate results from each agent in JSON format
   - Pass all sub-agent outputs to the Consolidation Agent (see adr-parallel-consolidator.md)
   - Include the target directory path for the consolidator
   - Generate final ADR documentation set
   - Write each ADR as a separate markdown file to the target directory

## Output Format

1. **Create `.adr-dir` file** containing the target directory path

2. **Write ADR files** to the target directory:
   - Each ADR as a separate file: `NNNN-title-with-hyphens.md`
   - Full markdown content following standard ADR format

3. **Summary output**:
```
ADR Documentation Generated
Target Directory: <path>
Created .adr-dir file

Generated ADRs:
- 0001-use-postgresql-as-primary-database.md
- 0002-adopt-microservices-architecture.md
- 0003-implement-jwt-authentication.md
...

Total: <N> architectural decisions documented
```

## Success Criteria

- Target directory successfully created and `.adr-dir` file written
- All sub-agents complete their analysis or report clear failure reasons
- At least 5 significant architectural decisions identified
- Generated ADRs follow standard ADR format (Status, Context, Decision, Consequences)
- Each ADR is properly numbered and written to separate markdown files
- Cross-references between related ADRs are established
- No duplicate or conflicting ADRs generated

## $ARGUMENTS

Required argument: Target directory path for ADR documentation (e.g., `docs/adr` or `architecture/decisions`)