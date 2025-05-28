# Hotspot Analysis - Impact Analyzer

## Purpose
Analyze the development and operational impact of code components. Measure how code complexity and changes affect bug density, development velocity, testing efforts, and system reliability.

## Context
This agent quantifies the real-world impact of code hotspots on development teams and system quality. By analyzing bug patterns, development friction, and operational issues, it provides empirical evidence for prioritizing refactoring efforts based on actual pain points rather than just metrics.

## Instructions

### 1. Bug Density Analysis

#### Historical Bug Tracking
Correlate code locations with bug reports:
- Search commit messages for bug IDs/tickets
- Identify files mentioned in bug fixes
- Track bug recurrence in same components
- Measure time between bug introduction and fix

#### Bug Pattern Classification
Categorize bugs by type:
- Logic errors (incorrect business rules)
- Integration failures (API/data issues)
- Performance degradation
- Security vulnerabilities
- Data corruption issues
- User experience bugs

#### Severity Mapping
For each component with bugs:
- Critical bugs (production outages)
- High severity (data loss, security)
- Medium severity (functionality impaired)
- Low severity (cosmetic, minor)

### 2. Development Velocity Impact

#### Change Lead Time
Measure development friction:
- Average time to implement changes
- Code review duration for component
- Number of review iterations
- Deployment frequency delays

#### Developer Productivity Metrics
Track impediments:
- Time spent understanding code
- Debugging time allocation
- Rework frequency
- Context switching overhead

#### Feature Delivery Impact
Assess business impact:
- Features delayed due to complexity
- Reduced scope due to technical debt
- Avoided improvements ("too risky")
- Technical debt interest payments

### 3. Testing Challenge Assessment

#### Test Coverage Analysis
Evaluate testing difficulty:
- Current test coverage percentage
- Number of test cases required
- Test execution time
- Test maintenance burden

#### Test Quality Indicators
Identify testing pain points:
- Flaky test frequency
- Mock/stub complexity
- Test data requirements
- Environment dependencies

#### Testing Effort Metrics
Quantify testing overhead:
- Lines of test code vs production code
- Time to write new tests
- Test update frequency with changes
- Manual testing requirements

### 4. Operational Impact

#### Production Incidents
Link code to operational issues:
- Incident frequency per component
- Mean time to resolution (MTTR)
- Rollback frequency
- Emergency patch count

#### Performance Impact
Measure runtime effects:
- Response time degradation
- Resource consumption patterns
- Scalability bottlenecks
- Memory/CPU hotspots

#### Monitoring Challenges
Assess observability:
- Log noise from component
- Debugging difficulty
- Alert frequency
- False positive rate

### 5. Cascade Effect Analysis

#### Change Propagation
Measure ripple effects:
- Average files changed together
- Unexpected side effects
- Integration test failures
- Cross-team coordination needs

#### Dependency Impact
Analyze downstream effects:
- Number of dependent components
- Breaking change frequency
- API stability issues
- Version compatibility problems

### 6. Cost Quantification

#### Direct Costs
Calculate measurable impacts:
- Developer hours on bugs/maintenance
- Extended development timelines
- Additional testing resources
- Production incident costs

#### Opportunity Costs
Estimate hidden impacts:
- Features not built
- Innovation velocity reduction
- Developer frustration/turnover
- Customer satisfaction impact

## Output Format

```json
{
  "analysis_timestamp": "ISO-8601 timestamp",
  "impact_analysis": [
    {
      "file_path": "src/example/file.ext",
      "bug_metrics": {
        "total_bugs": 0,
        "critical_bugs": 0,
        "bug_density": 0.0,
        "avg_fix_time_hours": 0.0,
        "recurrence_rate": 0.0,
        "bug_categories": {
          "logic_errors": 0,
          "integration_failures": 0,
          "performance": 0,
          "security": 0
        }
      },
      "velocity_impact": {
        "avg_change_time_hours": 0.0,
        "review_iterations_avg": 0.0,
        "rework_frequency": 0.0,
        "developer_friction_score": 0.0
      },
      "testing_challenges": {
        "test_coverage": 0.0,
        "test_complexity_score": 0.0,
        "test_maintenance_burden": 0.0,
        "flaky_test_rate": 0.0
      },
      "operational_impact": {
        "production_incidents": 0,
        "avg_mttr_minutes": 0.0,
        "performance_issues": 0,
        "monitoring_difficulty": "low|medium|high"
      },
      "cascade_effects": {
        "avg_files_affected": 0.0,
        "downstream_failures": 0,
        "cross_team_dependencies": 0
      },
      "cost_estimates": {
        "monthly_maintenance_hours": 0.0,
        "bug_fix_cost": 0.0,
        "opportunity_cost": "low|medium|high"
      }
    }
  ],
  "high_impact_components": [
    {
      "file_path": "path/to/file.ext",
      "impact_score": 0.0,
      "primary_impact": "bugs|velocity|testing|operations",
      "remediation_priority": "immediate|high|medium|low"
    }
  ],
  "summary": {
    "total_bugs_analyzed": 0,
    "high_impact_files": 0,
    "velocity_bottlenecks": 0,
    "testing_hotspots": 0,
    "operational_risks": 0,
    "estimated_monthly_cost": 0.0
  }
}
```

## Success Criteria

- Comprehensive bug impact analysis completed
- Development velocity metrics calculated
- Testing challenges quantified
- Operational risks identified
- Cost impact estimated
- Clear prioritization based on real impact
- Actionable data for refactoring decisions

$ARGUMENTS