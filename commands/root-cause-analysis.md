# Root Cause Analysis Prompt

## Purpose
Systematically investigate reported system symptoms to identify underlying root causes rather than just treating visible symptoms. Avoid the "microscope trap" by understanding the full system context and organizational factors.

## Context
The Review Primer emphasizes: "Symptom or root cause?" This analysis moves beyond surface-level issues to understand why problems occur. Many technical symptoms have organizational root causes, and fixing symptoms without addressing root causes leads to recurring problems.

## Instructions

### 1. Symptom Documentation and Categorization

#### A. Comprehensive Symptom Inventory
Document all reported issues systematically:

**Performance Symptoms**:
- Slow response times
- High resource utilization
- Timeout errors
- Degraded throughput

**Reliability Symptoms**:
- Frequent outages
- Intermittent failures
- Data inconsistencies
- Error spikes

**Usability Symptoms**:
- User complaints
- Workflow inefficiencies
- Confusing interfaces
- Training difficulties

**Maintainability Symptoms**:
- Long development cycles
- High bug rates
- Difficult deployments
- Knowledge silos

#### B. Symptom Pattern Analysis
Look for patterns across symptoms:
- **Timing patterns**: When do issues occur?
- **User patterns**: Which users are affected?
- **Component patterns**: Which system parts are involved?
- **Environmental patterns**: What conditions trigger issues?

### 2. Multi-Layer Root Cause Investigation

#### A. Technical Layer Analysis

**Code Level**:
- Algorithm inefficiencies
- Resource leaks
- Concurrency issues
- Poor error handling
- Design pattern misuse

**Architecture Level**:
- Component coupling issues
- Scalability bottlenecks
- Single points of failure
- Integration problems
- Technology mismatches

**Infrastructure Level**:
- Resource constraints
- Network issues
- Configuration problems
- Monitoring gaps
- Deployment issues

#### B. Process Layer Analysis

**Development Process**:
- Requirements gathering issues
- Design review gaps
- Testing inadequacies
- Code review problems
- Deployment process flaws

**Communication Process**:
- Information silos
- Unclear responsibilities
- Documentation gaps
- Knowledge transfer issues
- Feedback loop problems

#### C. Organizational Layer Analysis

**Team Structure**:
- Skill mismatches
- Resource constraints
- Knowledge distribution
- Accountability gaps
- Coordination overhead

**Cultural Factors**:
- Risk tolerance
- Quality mindset
- Learning culture
- Time pressure
- Innovation balance

### 3. Causal Chain Mapping

#### A. 5 Whys Technique
For each major symptom, ask "why" repeatedly:

**Example Analysis**:
```
Symptom: Users complain about slow search
1. Why? Search queries take 5+ seconds
2. Why? Database queries are inefficient
3. Why? No proper indexing on search fields
4. Why? Database design didn't consider search patterns
5. Why? Requirements didn't specify search performance needs
6. Why? Product team and development team don't communicate regularly about performance requirements
```

#### B. Fishbone Diagram Analysis
Categorize potential causes:

```
METHODS          MACHINES        MATERIALS
    |                |               |
    |                |               |
Process flaws -------|               |
Poor testing ----   |               |---- Outdated libraries
Manual deployment    |               |---- Poor documentation
    |                |               |
    |            Server capacity    |
    |            Network issues     |
    |            Tool limitations   |
    |________________________      |
                            |      |
                    SLOW PERFORMANCE
                            |
           _________________|________________
           |                               |
    PEOPLE |                        ENVIRONMENT
           |                               |
    Skill gaps                      Time pressure
    Knowledge silos                 Budget constraints
    Training gaps                   Changing requirements
```

### 4. Evidence Collection and Validation

#### A. Data-Driven Investigation
Collect objective evidence:

**Performance Data**:
- System metrics and logs
- User behavior analytics
- Error rates and patterns
- Resource utilization trends

**Process Data**:
- Development cycle times
- Code review feedback
- Bug reports and patterns
- Deployment success rates

**Organizational Data**:
- Team feedback surveys
- Communication patterns
- Knowledge transfer records
- Training completion rates

#### B. Hypothesis Testing
For each suspected root cause:
1. **Formulate hypothesis**: What do you think is causing the symptom?
2. **Design test**: How can you verify this hypothesis?
3. **Collect evidence**: What data supports or refutes it?
4. **Validate conclusion**: Is this truly a root cause or another symptom?

### 5. Root Cause Prioritization

#### A. Impact Assessment
For each identified root cause:

**Business Impact**:
- Revenue impact
- Customer satisfaction impact
- Operational efficiency impact
- Risk exposure

**Technical Impact**:
- System reliability
- Performance degradation
- Development velocity
- Technical debt accumulation

#### B. Fix Complexity Assessment
- **Effort required**: Time and resources needed
- **Risk of change**: Potential for introducing new issues
- **Dependencies**: What else needs to change
- **Stakeholder buy-in**: Organizational support needed

### 6. Systems Thinking Analysis

#### A. Interconnection Mapping
Understand how root causes interact:
- Which root causes reinforce each other?
- What feedback loops exist?
- How do organizational and technical factors interact?
- What leverage points exist for maximum impact?

#### B. Second-Order Effects
Consider consequences of fixing root causes:
- What new problems might emerge?
- How will the system adapt?
- What unintended consequences are possible?
- How can you monitor for new issues?

## Output Format

### 1. Symptom-to-Root-Cause Mapping

#### Symptom Analysis Summary
| Symptom | Frequency | Impact | User Groups Affected | System Components |
|---------|-----------|--------|---------------------|-------------------|
| Slow search | Daily | High | All users | Search service, database |
| Deployment failures | Weekly | Medium | Dev team | CI/CD pipeline |

#### Root Cause Hierarchy
```
Level 1 (Immediate Causes):
├── Database query inefficiency
├── Inadequate server resources
└── Poor caching strategy

Level 2 (Underlying Causes):
├── Missing performance requirements
├── Insufficient load testing
└── No performance monitoring

Level 3 (Systemic Causes):
├── Disconnected product and engineering teams
├── No performance culture
└── Reactive rather than proactive approach
```

### 2. Detailed Root Cause Analysis

For each identified root cause:

#### Root Cause: [Name]
- **Category**: Technical/Process/Organizational
- **Evidence Supporting**: [Specific data/observations]
- **Symptoms Caused**: [List of related symptoms]
- **Impact Assessment**: [Business and technical impact]
- **Interconnections**: [How this relates to other root causes]
- **Fix Complexity**: [Effort and risk assessment]

### 3. Causal Chain Documentation

#### Primary Causal Chains
Show the progression from root cause to symptom:

1. **Chain 1**: Organizational Issue → Process Gap → Technical Problem → User Symptom
   - Poor communication → Unclear requirements → Wrong technical choices → Slow performance

2. **Chain 2**: Technical Debt → Development Friction → Quality Issues → User Impact
   - Legacy code → Hard to change → More bugs → User frustration

### 4. Systems Analysis

#### Reinforcing Patterns
Identify vicious cycles:
- Time pressure → Shortcuts → Technical debt → Slower development → More time pressure

#### Leverage Points
High-impact intervention opportunities:
1. **[Intervention]**: Small change with big impact
2. **[Intervention]**: Breaks negative feedback loop

### 5. Prioritized Action Plan

#### Immediate Symptom Relief (< 1 week)
- Quick fixes to reduce user pain
- Monitoring improvements
- Communication actions

#### Root Cause Addressing (1-8 weeks)
Prioritized by impact and feasibility:

1. **[Root Cause]**:
   - Fix approach: [How to address]
   - Success metrics: [How to measure improvement]
   - Risk mitigation: [How to avoid new problems]
   - Timeline: [Expected duration]

#### Systemic Improvements (2-6 months)
Long-term changes to prevent recurrence:
- Organizational changes
- Process improvements
- Cultural shifts
- Infrastructure investments

### 6. Prevention Strategy

#### Early Warning Systems
- Metrics to monitor
- Alerting thresholds
- Regular health checks
- Feedback mechanisms

#### Organizational Learning
- How to capture lessons learned
- Knowledge sharing processes
- Training and skill development
- Culture and mindset changes

### 7. Validation Plan

#### Success Metrics
How to measure if root causes are truly addressed:
- Symptom reduction metrics
- Leading indicators of improvement
- Process health metrics
- Organizational health indicators

#### Monitoring Strategy
- Continuous monitoring approach
- Regular review cycles
- Escalation procedures
- Learning integration

## Success Criteria
- Clear distinction between symptoms and root causes
- Evidence-based causal chain documentation
- Understanding of technical, process, and organizational factors
- Prioritized action plan addressing root causes, not just symptoms
- Prevention strategy to avoid recurrence
- Systems thinking perspective on interconnections and leverage points

$ARGUMENTS