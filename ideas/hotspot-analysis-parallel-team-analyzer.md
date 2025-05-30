# Hotspot Analysis - Team Analyzer

## Purpose
Analyze organizational and team-related factors that contribute to code complexity and maintenance challenges. Identify knowledge silos, collaboration patterns, and team dynamics that affect code quality.

## Context
Technical debt and code complexity often have organizational roots. This agent examines how team structure, knowledge distribution, communication patterns, and organizational pressures create and perpetuate hotspots. Understanding these human factors is crucial for sustainable improvement strategies.

## Instructions

### 1. Knowledge Distribution Analysis

#### Code Ownership Mapping
Identify knowledge concentration:
- Primary contributors per component
- Percentage of commits by top contributor  
- Bus factor calculation (minimum contributors with 50% knowledge)
- Knowledge depth vs breadth per developer

#### Expertise Silos
Detect single points of failure:
- Components with single active maintainer
- Technologies known by few team members
- Undocumented domain knowledge
- Critical components with low bus factor

#### Knowledge Transfer Indicators
Assess knowledge sharing:
- Pair programming frequency
- Code review participation diversity
- Documentation contribution patterns
- Mentoring relationships in git history

### 2. Team Collaboration Patterns

#### Cross-Team Dependencies
Map organizational boundaries in code:
- Components modified by multiple teams
- Handoff points between teams
- Integration layer ownership
- Cross-team code review patterns

#### Communication Efficiency
Analyze collaboration indicators:
- PR review response times
- Number of review cycles
- Comment density on complex code
- Question patterns in commit messages

#### Team Stability
Track team dynamics:
- Developer turnover per component
- Onboarding patterns (new contributor ramp-up)
- Team size fluctuations
- Remote vs co-located collaboration

### 3. Organizational Pressure Indicators

#### Deadline-Driven Development
Identify rushed work patterns:
- Commit message urgency indicators
- After-hours commit frequency
- Weekend/holiday commits
- "Quick fix" pattern detection

#### Technical Debt Accumulation
Track debt indicators:
- TODO/FIXME comment growth
- Workaround implementations
- Deferred refactoring mentions
- "Temporary" solution patterns

#### Process Maturity Signals
Assess development practices:
- Code review coverage
- Testing discipline indicators
- Documentation maintenance
- Refactoring frequency

### 4. Team Cognitive Load

#### Context Switching
Measure focus fragmentation:
- Number of different components per developer
- Technology stack diversity per person
- Concurrent project involvement
- Interrupt-driven change patterns

#### Learning Curve Indicators
Identify complexity barriers:
- New developer productivity lag
- Mistake patterns in components
- Question frequency about code
- Avoided components pattern

#### Mental Model Alignment
Detect conceptual mismatches:
- Inconsistent naming conventions
- Conflicting design patterns
- Architecture violation frequency
- Style guide deviations

### 5. Organizational Structure Impact

#### Conway's Law Manifestation
Map organization to architecture:
- Team boundaries in code structure
- Communication paths in dependencies
- Decision-making bottlenecks
- Ownership ambiguities

#### Power Distance Effects
Identify hierarchy impacts:
- Senior developer code dominance
- Review approval patterns
- Decision reversal frequency
- Innovation distribution

### 6. Team Health Metrics

#### Burnout Indicators
Detect sustainability issues:
- Increasing error rates
- Declining commit quality
- Reduced collaboration
- Code abandonment patterns

#### Morale Signals
Track team sentiment:
- Commit message tone
- Humor/frustration in comments
- Voluntary refactoring efforts
- Code craftsmanship indicators

## Output Format

```json
{
  "analysis_timestamp": "ISO-8601 timestamp",
  "team_analysis": [
    {
      "file_path": "src/example/file.ext",
      "knowledge_metrics": {
        "primary_contributor": "developer_name",
        "contribution_percentage": 0.0,
        "bus_factor": 0,
        "knowledge_risk": "critical|high|medium|low",
        "last_knowledge_transfer": "ISO-8601 date"
      },
      "collaboration_patterns": {
        "unique_contributors": 0,
        "cross_team_changes": 0,
        "avg_review_cycles": 0.0,
        "collaboration_score": 0.0
      },
      "organizational_factors": {
        "rush_job_indicators": 0,
        "technical_debt_mentions": 0,
        "after_hours_commits": 0,
        "process_maturity_score": 0.0
      },
      "cognitive_load": {
        "complexity_complaints": 0,
        "learning_curve_steep": true,
        "context_switches": 0,
        "avoidance_pattern": false
      },
      "team_health": {
        "stability_score": 0.0,
        "burnout_risk": "low|medium|high",
        "ownership_clarity": "clear|ambiguous|contested"
      }
    }
  ],
  "organizational_insights": {
    "knowledge_silos": [
      {
        "component": "path/to/component",
        "expert": "developer_name",
        "risk_level": "critical|high|medium"
      }
    ],
    "team_boundaries": [
      {
        "boundary": "team_a_to_team_b",
        "friction_points": ["file1.ext", "file2.ext"],
        "coordination_overhead": "low|medium|high"
      }
    ],
    "process_gaps": [
      {
        "issue": "Insufficient code review coverage",
        "affected_components": ["path1", "path2"],
        "impact": "Quality degradation"
      }
    ]
  },
  "summary": {
    "critical_knowledge_risks": 0,
    "team_friction_points": 0,
    "organizational_debt": 0,
    "collaboration_health_score": 0.0,
    "recommended_interventions": [
      "Knowledge sharing sessions",
      "Cross-team pairing",
      "Documentation sprints"
    ]
  }
}
```

## Success Criteria

- Complete team and knowledge distribution mapped
- Organizational patterns identified and quantified
- Collaboration bottlenecks highlighted
- Knowledge risks assessed with mitigation strategies
- Team health indicators calculated
- Actionable organizational improvements suggested
- Human factors integrated into hotspot analysis

$ARGUMENTS