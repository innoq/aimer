# Quality Scenario Analysis

## Purpose

Systematically evaluate architecture against quality requirements using concrete, measurable scenarios. Identify architectural trade-offs and risks that impact system quality attributes based on ISO 25010 and the ATAM methodology.

## Context

Quality scenarios transform vague requirements like "the system should be fast" into concrete, testable specifications. This analysis reveals whether the architecture can deliver required quality attributes and where trade-offs create risks.

## Instructions

### 1. Quality Attribute Prioritization

First, determine which quality attributes matter most for this system:

#### ISO 25010 Quality Attributes

Rate business importance (1-5) for each:

- **Functional Suitability**: Does the system do what it should?
- **Performance Efficiency**: Response time, throughput, resource usage
- **Compatibility**: Interoperability, co-existence with other systems
- **Usability**: Learnability, operability, user satisfaction
- **Reliability**: Availability, fault tolerance, recoverability
- **Security**: Confidentiality, integrity, authenticity
- **Maintainability**: Modularity, reusability, analyzability, modifiability
- **Portability**: Adaptability, installability, replaceability

Focus detailed analysis on attributes rated 4-5.

#### Q42 Quality Tags for Practical Orientation

As an alternative or complement to ISO 25010, consider the 8 Q42 quality tags from quality.arc42.org:

- **#reliable**: Availability, fault tolerance, recoverability
- **#flexible**: Adaptability, extensibility, configurability  
- **#efficient**: Performance, resource usage, scalability
- **#usable**: Usability, learnability, accessibility
- **#safe**: Operational safety, error handling, fail-safety
- **#secure**: Confidentiality, integrity, authenticity
- **#suitable**: Functional completeness, correctness, appropriateness
- **#operable**: Operability, monitorability, administrability

→ Visit quality.arc42.org for 161 detailed quality properties and 104 concrete examples

### 2. Scenario Development Template

For each important quality attribute, create 3-5 concrete scenarios using:

**Source** → **Stimulus** → **Artifact** → **Environment** → **Response** → **Response Measure**

#### Examples

**Performance Scenario**:

- **Source**: 1,000 concurrent users
- **Stimulus**: Submit search query
- **Artifact**: Search service
- **Environment**: Normal operation, peak hours
- **Response**: Return search results
- **Response Measure**: 95% of queries complete in < 200ms

**Reliability Scenario**:

- **Source**: Infrastructure
- **Stimulus**: Primary database fails
- **Artifact**: Data access layer
- **Environment**: Production, business hours
- **Response**: Failover to replica
- **Response Measure**: < 30 seconds downtime, zero data loss

**Security Scenario**:

- **Source**: External attacker
- **Stimulus**: Attempts SQL injection via web form
- **Artifact**: User input handling
- **Environment**: Production environment
- **Response**: Block attack, log attempt, maintain service
- **Response Measure**: 100% of injection attempts blocked

#### Q42 Scenario Examples

For additional scenario inspiration, quality.arc42.org provides 104 concrete examples across all quality properties:

**#efficient - Scalability Example**:

- **Source**: Black Friday traffic spike
- **Stimulus**: 10x normal user load
- **Response Measure**: Auto-scaling to 50 instances in < 2 minutes

**#operable - Monitorability Example**:

- **Source**: Operations team
- **Stimulus**: Performance degradation detected
- **Response Measure**: Root cause identified in < 5 minutes via dashboards

Use the Q42 library as inspiration for domain-specific scenarios.

### 3. Architectural Analysis per Scenario

For each scenario, analyze:

#### A. Architectural Support Assessment

Rate 1-5 how well current architecture supports the scenario:

- 5: Fully supports with margin
- 4: Supports adequately
- 3: Marginal support, at risk
- 2: Significant gaps
- 1: Cannot support

#### B. Architectural Decisions Impact

Identify which architectural decisions affect this scenario:

- **Positive influences**: Decisions that help achieve the quality
- **Negative influences**: Decisions that hinder the quality
- **Sensitivity points**: Where small changes have large impacts
- **Trade-off points**: Where this quality conflicts with others

#### C. Risk Identification

- What could cause the scenario to fail?
- How likely is failure? (High/Medium/Low)
- What's the business impact of failure?
- Are there early warning indicators?

### 4. Q42 Tag-based Trade-off Analysis

Use Q42 tags for quick trade-off identification:

| Q42 Tag A | Q42 Tag B | Typical Conflict | Solution Approaches |
|-----------|-----------|-----------------|--------------------|
| #efficient | #flexible | Optimization vs. Generalization | Domain-specific Languages |
| #secure | #usable | Security measures vs. UX | Risk-based Authentication |
| #reliable | #efficient | Redundancy vs. Resources | Selective Redundancy |

### 5. Quality Attribute Trade-offs Analysis

Map conflicting quality attributes:

| Quality A | Quality B | Conflict Description | Current Balance | Optimal Balance |
|-----------|-----------|---------------------|-----------------|-----------------|
| Performance | Security | Encryption overhead | Favors performance | Need more security |
| Availability | Consistency | CAP theorem | Eventual consistency | Evaluate per use case |

### 6. Architectural Patterns Evaluation

Assess how current patterns support quality scenarios:

| Pattern | Scenarios Supported | Scenarios Hindered | Net Impact |
|---------|--------------------|--------------------|------------|
| Microservices | Maintainability+, Scalability+ | Performance-, Complexity- | Positive for this system |
| Event Sourcing | Auditability+, Reliability+ | Query Performance- | Mixed, needs optimization |

### 7. Scenario Testing Strategy

For each scenario, define:

- **How to test**: Load test, chaos engineering, security scan, etc.
- **Test frequency**: Continuous, nightly, weekly, release
- **Current test coverage**: Fully tested, partially tested, not tested
- **Test environment requirements**: Production-like, special tools needed

## Output Format

### 1. Quality Attribute Priority Matrix

| Quality Attribute | Business Priority (1-5) | Current Support (1-5) | Gap | Risk Level |
|------------------|------------------------|---------------------|-----|------------|
| Performance | 5 | 3 | -2 | High |
| Security | 5 | 4 | -1 | Medium |
| Maintainability | 4 | 2 | -2 | High |

### 2. Critical Scenarios Analysis

For each high-priority scenario:

#### Scenario: [Name]

- **Full Specification**: Source → Stimulus → ... → Response Measure
- **Current Architecture Score**: X/5
- **Key Architectural Influences**:
  - Helps: [Decisions/patterns that support]
  - Hinders: [Decisions/patterns that obstruct]
- **Risks Identified**: [Specific risks with likelihood/impact]
- **Improvement Options**: [Architectural changes to better support]

### 3. Trade-off Decisions Required

Business decisions needed on quality trade-offs:

1. **[Trade-off Name]**
   - Conflict: [Quality A] vs [Quality B]
   - Current state: [Description]
   - Options:
     - Option 1: [Description, impact]
     - Option 2: [Description, impact]
   - Recommendation: [Which option and why]

### 4. Architectural Risk Register

| Risk | Related Scenarios | Likelihood | Impact | Mitigation Strategy |
|------|------------------|------------|--------|---------------------|
| Database bottleneck | Perf-1, Perf-3 | High | High | Read replicas, caching |

### 5. Testing Gap Analysis

| Scenario | Test Type Needed | Current Coverage | Priority | Next Steps |
|----------|-----------------|------------------|----------|------------|
| Perf-1 | Load test | None | High | Implement JMeter suite |

### 6. Architectural Recommendations

#### Immediate Improvements (< 2 weeks)

- Quick wins that improve quality scenarios
- Configuration changes
- Minor code modifications

#### Architectural Refactoring (1-3 months)

- Pattern changes needed
- Component redesigns
- Technology updates

#### Strategic Architecture Evolution (3-12 months)

- Major architectural shifts
- Platform migrations
- Fundamental redesigns

### 7. Quality Monitoring Dashboard

Proposed metrics to continuously track quality:

| Quality Attribute | Key Metrics | Target | Alert Threshold |
|------------------|-------------|--------|-----------------|
| Performance | p95 response time | <200ms | >500ms |
| Reliability | Uptime | 99.9% | <99.5% |
| Security | Failed auth attempts | <100/hour | >1000/hour |

## Success Criteria

- Concrete, measurable scenarios for all critical quality attributes
- Clear understanding of architectural support levels
- Identified all significant quality trade-offs
- Risk assessment with mitigation strategies
- Actionable improvement roadmap
- Test strategy for continuous quality validation

## Additional Resources

**Q42 Quality Model** (quality.arc42.org):

- 161 structured quality properties with definitions
- 104 concrete scenarios as templates
- Interactive tag-based navigation
- Direct links between related quality properties
- Field-tested formulations for stakeholder communication

Use Q42 especially for:

- Inspiration during scenario development
- Stakeholder-appropriate formulations
- Completeness checking (have we considered all relevant properties?)
- Trade-off identification through tag relationships

$ARGUMENTS
