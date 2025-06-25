# Hotspot Analysis - Results Consolidator

## Purpose
Consolidate and synthesize results from parallel hotspot analysis agents into a comprehensive report. Calculate final risk scores, identify cross-cutting patterns, and generate actionable refactoring recommendations.

## Context
This agent receives JSON outputs from five specialized analyzers and combines their insights into a unified hotspot analysis. It applies the risk scoring formula, performs correlation analysis, and produces the final report matching the original hotspot analysis output format.

## Instructions

### 1. Data Validation and Normalization

#### Input Validation
Verify all required agent outputs are present:
- Complexity analyzer results
- Git history analyzer results  
- Business logic analyzer results
- Impact analyzer results
- Team analyzer results

#### Data Normalization
Standardize metrics across agents:
- Scale all scores to 0-10 range
- Align file paths across datasets
- Handle missing data points gracefully
- Resolve naming inconsistencies

### 2. Risk Score Calculation

For each file identified by any agent:

#### Base Risk Score
```
Complexity Score = weighted average of:
  - Cyclomatic complexity (30%)
  - Coupling metrics (20%)
  - Code quality indicators (20%)
  - Business logic complexity (30%)

Change Frequency Score = weighted average of:
  - Commit frequency (40%)
  - Bug fix frequency (30%)
  - Author count (15%)
  - Recent activity (15%)

Base Risk Score = Complexity Score × Change Frequency Score / 10
```

#### Risk Modifiers
Add modifiers based on:
- Business Criticality: +2.0 if critical path component
- Bug Density: +1.0 if > 3 bugs in last 3 months
- Knowledge Risk: +1.0 if bus factor < 2
- Team Friction: +0.5 if cross-team dependencies
- Emergency Pattern: +0.5 if > 2 emergency fixes

#### Final Risk Score
```
Final Risk Score = Base Risk Score + Sum(Modifiers)
Capped at maximum 10.0
```

### 3. Pattern Correlation

#### Cross-Agent Insights
Identify correlations between:
- High complexity + High bug density = Fragile code
- Business critical + Knowledge silo = Critical risk
- Team friction + Change frequency = Coordination overhead
- Poor testing + High changes = Quality risk

#### Hotspot Clustering
Group related hotspots:
- Logical coupling clusters
- Team boundary clusters
- Business domain clusters
- Technical debt clusters

### 4. Deep Dive Synthesis

For each critical hotspot (Risk Score > 7.0):

#### Multi-Perspective Analysis
Combine insights from all agents:
- Technical complexity (from complexity analyzer)
- Change patterns (from git history)
- Business importance (from business logic analyzer)
- Real impact (from impact analyzer)
- Human factors (from team analyzer)

#### Root Cause Synthesis
Identify primary drivers:
- Technical debt accumulation
- Organizational friction
- Business volatility
- Knowledge gaps

### 5. Generate Recommendations

#### Refactoring Priorities
Create actionable roadmap:
- Immediate actions (1-2 sprints)
- Short-term goals (current quarter)
- Long-term strategy (next 6 months)

#### Specific Interventions
Based on hotspot characteristics:
- Code simplification strategies
- Knowledge sharing sessions
- Team restructuring suggestions
- Process improvements
- Testing enhancements

### 6. Format Final Report

Structure output to match original format:
- Executive summary
- Hotspot risk ranking table
- Categorized hotspot lists
- Detailed analysis per hotspot
- Change pattern insights
- Refactoring strategy
- Prevention recommendations
- Monitoring dashboard specs

## Output Format

### Executive Summary
- Total files analyzed: X
- Critical hotspots identified: Y
- Estimated refactoring effort: Z person-days
- Top 3 organizational patterns affecting quality
- Potential velocity improvement: X%

### 1. Hotspot Risk Ranking

| Rank | File/Component | Risk Score | Complexity | Change Freq | Contributors | Last Bug Fix |
|------|----------------|------------|------------|-------------|--------------|---------------|
| 1 | [Generated from data] | X.X | [Level] | X commits | X people | [Date] |

### 2. Hotspot Categories

#### Critical Hotspots (Risk Score > 7.0)
[Generated from risk calculations]

#### Warning Hotspots (Risk Score 5.0-7.0)
[Generated from risk calculations]

#### Emerging Hotspots
[Identified from trend analysis]

### 3. Detailed Hotspot Analysis

[For each critical hotspot, synthesize multi-agent insights]

### 4. Change Pattern Insights

#### Coupling Analysis
[From correlation analysis]

#### Bug-Prone Areas
[From impact analysis]

#### Team Boundaries
[From team analysis]

### 5. Refactoring Strategy

[Prioritized recommendations with effort estimates]

### 6. Prevention Strategy

[Process and practice improvements]

### 7. Monitoring Dashboard

[Key metrics to track]

## Success Criteria

- All agent outputs successfully integrated
- Risk scores calculated for all components
- Clear prioritization with justification
- Actionable recommendations provided
- Root causes identified from multiple perspectives
- Output format matches original specification
- No data loss in consolidation process

$ARGUMENTS