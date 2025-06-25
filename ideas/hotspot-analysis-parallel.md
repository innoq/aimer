# Hotspot Analysis - Parallel Orchestrator

## Purpose
Coordinate parallel execution of specialized agents to identify high-risk code areas by combining complexity metrics with change frequency from version control history. Aggregate results to focus refactoring efforts on code that is both complex and frequently modified.

## Context
This orchestrator manages multiple specialized agents that analyze different aspects of code quality and change patterns simultaneously. By parallelizing the analysis, we achieve faster results while maintaining depth of analysis. Each agent focuses on a specific domain, enabling specialized expertise and independent scaling.

## Instructions

### 1. Initialize Parallel Analysis

Launch these specialized agents simultaneously to analyze different aspects of the codebase:
- Complexity Analyzer Agent (see hotspot-analysis-parallel-complexity-analyzer.md)
- Git History Analyzer Agent (see hotspot-analysis-parallel-git-history-analyzer.md)
- Business Logic Analyzer Agent (see hotspot-analysis-parallel-business-logic-analyzer.md)
- Impact Analyzer Agent (see hotspot-analysis-parallel-impact-analyzer.md)
- Team Analyzer Agent (see hotspot-analysis-parallel-team-analyzer.md)

### 2. Collect Agent Results

Wait for all agents to complete and collect their JSON outputs:

- **Complexity Analyzer**: Structural metrics, coupling data, code quality indicators
- **Git History Analyzer**: Change frequencies, author patterns, churn rates
- **Business Logic Analyzer**: Domain complexity, critical paths, state machines
- **Impact Analyzer**: Bug densities, velocity impacts, testing challenges
- **Team Analyzer**: Knowledge distribution, organizational factors, collaboration patterns

### 3. Calculate Hotspot Risk Scores

For each file/component identified by agents:

```
Base Risk Score = (Complexity Score × Change Frequency Score)

Adjusted Risk Score = Base Risk Score + Modifiers

Where Modifiers include:
- Business Criticality (+2 if critical)
- Recent Bug Density (+1 if > 3 bugs in 3 months)
- Knowledge Risk (+1 if < 2 active contributors)
- Emergency Fix Pattern (+1 if > 2 emergency fixes)
```

### 4. Categorize Hotspots

Apply the risk matrix:

| Risk Score | Category | Priority | Action |
|------------|----------|----------|---------|
| > 7.0 | Critical Hotspot | P0 | Immediate refactoring |
| 5.0-7.0 | Warning Hotspot | P1 | Planned refactoring |
| 3.0-5.0 | Emerging Hotspot | P2 | Monitor closely |
| < 3.0 | Stable Code | P3 | Maintain quality |

### 5. Correlation Analysis

Identify patterns across agent results:

- Files with high complexity AND high change frequency
- Components with business criticality AND knowledge silos
- Areas with bug density AND team fragmentation
- Code with testing challenges AND frequent changes

### 6. Deep Dive Synthesis

For critical hotspots (Risk Score > 7.0):

Combine insights from all agents:
- Root cause analysis from multiple perspectives
- Cross-functional impact assessment
- Comprehensive refactoring strategy
- Risk mitigation approaches

### 7. Generate Consolidated Report

Process the aggregated data using the Consolidation Agent (see hotspot-analysis-parallel-consolidator.md) with the collected results from all analysis agents.

### 8. Quality Assurance

Verify completeness:
- All identified files have risk scores
- No analysis gaps between agents
- Consistent categorization applied
- Actionable recommendations provided

## Output Format

### Executive Summary
- Total hotspots identified by risk category
- Top 5 critical hotspots requiring immediate attention
- Key organizational patterns affecting code quality
- Estimated refactoring effort and impact

### Detailed Analysis
Present the consolidated report from the consolidator agent, including:
- Complete hotspot ranking with multi-dimensional scores
- Deep dive analysis for critical components
- Refactoring roadmap with priorities
- Prevention strategies and monitoring approach

## Success Criteria

- All parallel agents completed successfully
- Risk scores calculated for 100% of analyzed codebase
- Clear prioritization of refactoring efforts
- Actionable recommendations with effort estimates
- Cross-functional insights integrated coherently
- Output matches original hotspot analysis format

$ARGUMENTS