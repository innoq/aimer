# Architecture Conformity Analysis Prompt

## Purpose
Evaluate how well the implemented system conforms to intended architectural design, identify architectural drift and erosion, and assess the impact of architectural debt on system maintainability and evolution.

## Context
Architecture conformity analysis reveals the gap between "architecture as designed" and "architecture as implemented." This gap often explains why systems become difficult to maintain, why changes take longer than expected, and why quality attributes degrade over time.

## Instructions

### 1. Architecture Documentation Assessment

#### A. Gather Architecture Artifacts
Collect and evaluate available documentation:
- Architecture decision records (ADRs)
- Component/service diagrams
- Deployment diagrams
- Sequence/flow diagrams
- Technology stack documentation
- Coding guidelines and standards

Rate documentation quality:
- **Completeness** (1-5): Are all aspects documented?
- **Currency** (1-5): How up-to-date is it?
- **Clarity** (1-5): How understandable is it?
- **Accessibility** (1-5): Can team members easily find and use it?

#### B. Extract Intended Architecture Rules
Document the explicit and implicit rules:

**Structural Rules**:
- Layer boundaries (e.g., "UI may not directly access database")
- Component responsibilities
- Allowed dependencies between modules
- Prohibited circular dependencies

**Technology Rules**:
- Approved technology stack
- Library/framework constraints
- Version requirements
- Platform limitations

**Pattern Rules**:
- Required design patterns
- Communication patterns (sync/async)
- Data access patterns
- Error handling patterns

### 2. Implementation Analysis

#### A. Static Architecture Extraction
Use tools and code analysis to extract actual architecture:

**Dependency Analysis**:
```
Module/Package Dependencies:
- Identify all import/usage relationships
- Map actual vs. intended dependencies
- Find dependency cycles
- Calculate coupling metrics
```

**Layer Violation Detection**:
```
For each architectural layer:
- List components that should be in this layer
- Find components accessing wrong layers
- Identify bypass patterns
- Quantify violation severity
```

#### B. Technology Stack Conformity
| Category | Intended | Actual | Conformity | Impact |
|----------|----------|---------|------------|---------|
| Web Framework | Spring Boot 2.7 | Mixed: 2.7 & 2.4 | Partial | Security vulnerabilities |
| Database | PostgreSQL only | PostgreSQL + MongoDB | Violation | Complexity increase |
| Messaging | Kafka | Kafka + RabbitMQ | Violation | Operational overhead |

### 3. Architectural Drift Patterns

#### A. Identify Common Drift Types

**Erosion Patterns**:
- **Big Ball of Mud**: Loss of clear boundaries
- **Layer Skipping**: Direct access bypassing layers
- **God Classes**: Responsibilities accumulation
- **Distributed Monolith**: Microservices with tight coupling
- **Technology Sprawl**: Uncontrolled tech diversity

**For Each Pattern Found**:
1. Specific locations/examples
2. How it evolved (git history analysis)
3. Business pressure that caused it
4. Technical impact assessment
5. Remediation effort estimate

#### B. Drift Timeline Analysis
Track when and why drift occurred:
- Major drift events (from git history)
- Correlation with team changes
- Relationship to deadline pressure
- Impact of quick fixes becoming permanent

### 4. Architectural Debt Assessment

#### A. Quantify Architectural Debt
| Debt Type | Instances | Severity | Fix Effort | Business Impact |
|-----------|-----------|----------|------------|-----------------|
| Layer violations | 47 | High | 3 weeks | Slow feature delivery |
| Outdated libraries | 12 | Medium | 1 week | Security risk |
| Missing abstractions | 8 | High | 4 weeks | Testing difficulties |

#### B. Debt Impact Analysis
For each significant debt item:
- **Development Impact**: How much does it slow development?
- **Quality Impact**: Which quality attributes suffer?
- **Risk Assessment**: What could fail because of this?
- **Propagation Risk**: Will this debt create more debt?

### 5. Conformity Heat Map

Create visual representation showing:
- **Green**: Full conformity
- **Yellow**: Minor deviations
- **Orange**: Significant drift
- **Red**: Major violations

```
Component Architecture Conformity:
┌─────────────┬─────────────┬─────────────┐
│ UI Layer    │ Service     │ Data Layer  │
│   YELLOW    │   ORANGE    │    RED      │
├─────────────┼─────────────┼─────────────┤
│ Auth Module │ Core Logic  │ Integration │
│   GREEN     │    RED      │   YELLOW    │
└─────────────┴─────────────┴─────────────┘
```

### 6. Root Cause Analysis

For major conformity violations, identify root causes:

#### A. Technical Causes
- Missing architectural enforcement tools
- Inadequate code review focus on architecture
- Lack of architectural tests
- Poor development environment setup

#### B. Organizational Causes
- Time pressure leading to shortcuts
- Team turnover losing architectural knowledge
- Insufficient architecture ownership
- Poor communication of architectural decisions

#### C. Process Causes
- No architecture review in development process
- Missing architectural fitness functions
- Inadequate onboarding on architecture
- No regular architecture debt reviews

## Output Format

### 1. Executive Summary
- Overall conformity score (percentage)
- Critical violations requiring immediate attention
- Estimated technical debt in person-weeks
- Risk assessment for continued operation

### 2. Detailed Conformity Report

#### A. Layer Conformity Analysis
| Layer | Intended Rules | Violations Found | Severity | Remediation |
|-------|----------------|------------------|----------|-------------|
| Presentation | No business logic | 12 instances of logic | Medium | Extract to service layer |

#### B. Component Conformity Matrix
| Component | Documented Responsibility | Actual Responsibility | Drift Assessment |
|-----------|-------------------------|---------------------|------------------|
| UserService | User CRUD only | User CRUD + Notifications + Auth | Significant scope creep |

### 3. Critical Violations

For each critical violation:
#### Violation: [Name]
- **Description**: What rule is being violated
- **Locations**: Specific files/modules
- **Evidence**: Code examples or metrics
- **Impact**: How this affects the system
- **Root Cause**: Why this violation occurred
- **Fix Strategy**: How to remediate
- **Effort Estimate**: Time/resources needed

### 4. Architectural Debt Register

| ID | Debt Description | Type | Impact | Fix Effort | Priority | Owner |
|----|-----------------|------|---------|------------|----------|--------|
| AD-001 | Database access from UI | Layer violation | High | 2 weeks | Critical | Team A |

### 5. Trend Analysis

Show how conformity has changed over time:
- Conformity score evolution (graph)
- New violations introduced per month
- Violations fixed per month
- Correlation with major releases/events

### 6. Recommendations

#### Immediate Actions (< 1 week)
- Stop the bleeding: Prevent new violations
- Quick fixes for critical issues
- Team alignment on architecture

#### Short-term Improvements (1-4 weeks)
- Implement architecture tests
- Refactor highest-impact violations
- Update documentation

#### Long-term Strategy (1-3 months)
- Establish architectural fitness functions
- Implement continuous conformity checking
- Major refactoring initiatives
- Team training on architecture

### 7. Architectural Governance Recommendations

**Tools and Automation**:
- Architecture conformity checking tools
- Pre-commit hooks for layer violations
- Automated dependency analysis
- Architecture documentation generators

**Process Improvements**:
- Architecture review checkpoints
- Regular debt assessment meetings
- Architecture decision record process
- Conformity metrics in team dashboards

**Team Practices**:
- Architecture champions per team
- Regular architecture workshops
- Pair programming for complex changes
- Architecture-focused code reviews

## Success Criteria
- Complete mapping of intended vs actual architecture
- Identified all major conformity violations
- Quantified architectural debt with business impact
- Root cause analysis for major drift patterns
- Actionable remediation plan with priorities
- Governance recommendations to prevent future drift

$ARGUMENTS