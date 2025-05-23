# Development Process Analysis

## Purpose
Identify organizational and process issues that manifest as technical problems. Many technical symptoms have their root causes in team dynamics, communication patterns, and development workflows.

## Context
As the Review Primer emphasizes: "Viele technische Probleme sind lediglich Symptome von organisatorischen Defiziten." This analysis reveals how process inefficiencies, knowledge silos, and organizational friction create technical debt and quality issues.

## Instructions

### 1. Team Structure and Dynamics Assessment

#### A. Team Organization Analysis
Map the development ecosystem:

**Team Boundaries**:
- How many teams work on this system?
- What are team responsibilities and ownership areas?
- How are cross-cutting concerns handled?
- Which teams have dependencies on each other?

**Knowledge Distribution**:
- Key person dependencies (bus factor analysis)
- Domain expertise location
- Technical skill distribution
- Documentation ownership

**Decision Making**:
- Who makes architectural decisions?
- How are priorities set and communicated?
- What's the escalation path for conflicts?
- How are technical standards enforced?

#### B. Collaboration Patterns
Analyze how teams work together:

| Team A | Team B | Interaction Frequency | Communication Method | Friction Points |
|--------|--------|--------------------|---------------------|----------------|
| Frontend | Backend | Daily | Slack, standups | API contract changes |
| Platform | Product | Weekly | Email, meetings | Priority conflicts |

**Collaboration Health Indicators**:
- Response time to requests between teams
- Number of escalations or conflicts
- Shared understanding of interfaces
- Joint problem-solving sessions

### 2. Development Workflow Efficiency Analysis

#### A. Value Stream Mapping
Trace the flow from idea to production:

```
Idea → Requirements → Design → Development → Review → Testing → Deployment → Monitoring
  ↓        ↓           ↓          ↓            ↓        ↓          ↓            ↓
[Time]   [Time]     [Time]    [Time]      [Time]   [Time]    [Time]      [Time]
[Waste]  [Waste]    [Waste]   [Waste]     [Waste]  [Waste]   [Waste]     [Waste]
```

**For each stage, identify**:
- Cycle time (how long it takes)
- Wait time (delays between stages)
- Handoff friction
- Rework frequency
- Bottlenecks and constraints

#### B. Development Metrics Analysis
If available, analyze:
- **Lead Time**: Idea to production
- **Cycle Time**: Development start to completion
- **Deployment Frequency**: How often releases happen
- **Change Failure Rate**: Percentage of deployments causing issues
- **Mean Time to Recovery**: How quickly issues are resolved

#### C. Process Bottleneck Identification

**Common Bottleneck Patterns**:
- **Review Bottlenecks**: Limited reviewers, slow review cycles
- **Environment Bottlenecks**: Limited test environments, access issues
- **Approval Bottlenecks**: Lengthy approval processes
- **Knowledge Bottlenecks**: Waiting for specific experts
- **Tool Bottlenecks**: Inadequate development infrastructure

### 3. Communication Pattern Analysis

#### A. Communication Effectiveness Assessment

**Information Flow Analysis**:
- How do requirements reach developers?
- How are architectural decisions communicated?
- How is domain knowledge shared?
- How are incidents and learnings communicated?

**Communication Channels Evaluation**:
| Channel | Usage | Effectiveness | Information Loss | Recommendations |
|---------|-------|---------------|------------------|-----------------|
| Slack | High | Medium | High (async) | Better threading, documentation |
| Standups | Daily | Low | Medium | Focus on blockers, not status |
| Documentation | Low | High | Low | Increase usage, improve findability |

#### B. Knowledge Management Assessment
- **Documentation Quality**: Currency, completeness, accessibility
- **Knowledge Transfer**: Onboarding effectiveness, learning resources
- **Tribal Knowledge**: Undocumented critical knowledge
- **Learning Culture**: How mistakes are handled, knowledge sharing incentives

### 4. Quality Assurance Process Evaluation

#### A. Testing Strategy Assessment

**Test Coverage Analysis**:
- Unit test coverage and quality
- Integration test completeness
- End-to-end test reliability
- Performance test adequacy
- Security test coverage

**Test Process Efficiency**:
- Test execution time
- Test maintenance burden
- False positive rate
- Test environment management
- Automated vs manual testing ratio

#### B. Quality Gates and Standards

**Code Quality Process**:
- Code review effectiveness and consistency
- Static analysis tool usage
- Quality metrics tracking
- Technical debt management
- Coding standards adherence

**Definition of Done Clarity**:
- Are quality criteria clear and consistently applied?
- How are quality trade-offs decided?
- What triggers quality improvements?

### 5. Incident and Change Management

#### A. Incident Response Analysis
- **Detection Time**: How quickly are problems identified?
- **Response Coordination**: Who responds and how?
- **Resolution Process**: Systematic vs ad-hoc problem solving
- **Learning Integration**: How are lessons learned captured and applied?

#### B. Change Management Process
- **Change Planning**: How are changes analyzed for risk?
- **Rollback Capability**: How quickly can changes be undone?
- **Change Communication**: How are changes communicated to stakeholders?
- **Change Validation**: How is change success measured?

### 6. Root Cause Analysis of Process Issues

For each identified process problem:

#### A. Symptom vs Root Cause Analysis
- **Symptoms**: What process pain points are visible?
- **Immediate Causes**: What directly causes these symptoms?
- **Root Causes**: What organizational factors create these conditions?
- **System Factors**: How do policies/structures contribute?

#### B. 5 Whys Analysis Example
**Symptom**: Deployment takes 4 hours
1. Why? Manual testing required before each release
2. Why? Automated tests are unreliable
3. Why? Tests are poorly maintained and environment-dependent
4. Why? No dedicated time/ownership for test maintenance
5. Why? Team is measured only on feature delivery, not quality

## Output Format

### 1. Process Health Dashboard

| Process Area | Health Score (1-5) | Key Issues | Impact on Development |
|--------------|-------------------|------------|---------------------|
| Requirements | 2 | Unclear, changing | 40% rework |
| Code Review | 3 | Slow, inconsistent | 2-day delays |
| Testing | 2 | Manual, unreliable | Fear of deployment |
| Deployment | 2 | Manual, risky | Infrequent releases |

### 2. Team Dynamics Assessment

#### Cross-Team Dependencies
Visual map showing:
- Team relationships and dependencies
- Communication frequency and effectiveness
- Known friction points
- Coordination overhead

#### Knowledge Risk Analysis
- **Critical knowledge holders**: [Names and areas]
- **Bus factor assessment**: [Areas with single points of failure]
- **Knowledge gaps**: [Areas lacking expertise]

### 3. Workflow Efficiency Analysis

#### Value Stream Map
Show current state with:
- Process steps and cycle times
- Wait times and bottlenecks
- Handoff points and friction
- Waste identification

#### Improvement Opportunities
| Opportunity | Current State | Target State | Effort | Impact |
|-------------|---------------|--------------|--------|--------|
| Automate testing | 4h manual testing | 30min automated | Medium | High |
| Improve review process | 2-day review delays | Same-day reviews | Low | Medium |

### 4. Communication Effectiveness Report

#### Information Flow Issues
1. **[Issue]**: How information gets lost or delayed
2. **[Issue]**: Where communication breaks down

#### Knowledge Management Gaps
1. **[Gap]**: What knowledge is missing or poorly documented
2. **[Gap]**: Where tribal knowledge creates risks

### 5. Quality Process Assessment

#### Current Quality Practices
- What's working well
- What's causing quality issues
- Where quality gates are missing
- How quality debt accumulates

#### Testing and Review Effectiveness
- Test coverage gaps
- Review process bottlenecks
- Quality metric trends
- Technical debt patterns

### 6. Root Cause Analysis Summary

#### Organizational Root Causes
For each major process issue:
1. **[Issue]**: Organizational factors contributing to technical problems

#### Systemic Issues
Patterns that affect multiple areas:
1. **[Pattern]**: How this manifests across different processes

### 7. Prioritized Improvement Recommendations

#### Immediate Actions (< 2 weeks)
- Quick wins that improve process flow
- Communication improvements
- Tool or automation quick fixes

#### Short-term Improvements (1-2 months)
- Process redesign initiatives
- Team structure adjustments
- Tool implementations

#### Strategic Changes (3-6 months)
- Organizational structure changes
- Culture and incentive changes
- Major process overhauls

### 8. Process Monitoring Strategy

#### Key Process Metrics
Metrics to track improvement:
- Lead time and cycle time
- Deployment frequency and success rate
- Review and testing efficiency
- Communication effectiveness

#### Regular Health Checks
- Monthly process retrospectives
- Quarterly team dynamics assessment
- Continuous workflow monitoring

## Success Criteria
- Identified how organizational issues manifest as technical problems
- Clear understanding of process bottlenecks and inefficiencies
- Root cause analysis connecting team dynamics to technical debt
- Actionable recommendations addressing both symptoms and causes
- Monitoring strategy for continuous process improvement
- Team alignment on process improvement priorities

$ARGUMENTS