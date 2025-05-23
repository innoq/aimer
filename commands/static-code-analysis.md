# Static Code Analysis

## Purpose
Systematically evaluate code quality, identify structural issues, and detect potential bugs or vulnerabilities through automated and manual analysis. Focus on finding patterns that indicate deeper architectural or process problems.

## Context
Static code analysis provides objective data about code quality and helps identify areas where code complexity, technical debt, or poor practices create maintainability risks. This analysis should complement dynamic analysis and look for root causes, not just symptoms.

## Instructions

### 1. Analysis Strategy and Tool Selection

#### A. Multi-Layered Analysis Approach
Combine multiple analysis techniques:

**Automated Static Analysis**:
- Code complexity tools (SonarQube, CodeClimate, ESLint)
- Security scanners (CodeQL, Bandit, Brakeman)
- Dependency vulnerability scanners
- License compliance checkers

**Manual Code Review**:
- Architecture pattern adherence
- Business logic correctness
- Error handling patterns
- Performance implications

#### B. Language-Specific Tool Configuration
Ensure tools are properly configured for:
- Language-specific best practices
- Framework-specific patterns
- Project-specific rules and exceptions
- Security vulnerability patterns
- Performance anti-patterns

### 2. Code Quality Metrics Analysis

#### A. Complexity Metrics Assessment

**Structural Complexity**:
- **Cyclomatic Complexity**: Decision point analysis
  - Target: Functions < 10, Classes < 20
  - Identify functions > 15 (high risk)
- **Cognitive Complexity**: Mental overhead measurement
- **Nesting Depth**: Deeply nested code identification
- **Function/Method Length**: Oversized function detection
- **Class Size**: God class identification

**Maintainability Metrics**:
- **Halstead Complexity**: Program difficulty measures
- **Maintainability Index**: Overall maintainability score
- **Technical Debt Ratio**: Effort to fix vs. build time

#### B. Code Organization Assessment

**Coupling Analysis**:
- **Afferent Coupling (Ca)**: Incoming dependencies
- **Efferent Coupling (Ce)**: Outgoing dependencies
- **Instability (I)**: Ce / (Ca + Ce)
- **Abstractness (A)**: Abstract classes ratio
- **Distance from Main Sequence**: Balance of abstractness and stability

**Cohesion Analysis**:
- **Lack of Cohesion of Methods (LCOM)**: Class responsibility focus
- **Single Responsibility Principle** adherence
- **Interface Segregation** effectiveness

### 3. Code Smell Detection and Categorization

#### A. Systematic Code Smell Inventory

**Design Smells**:
- **Large Classes**: Classes with too many responsibilities
- **Long Methods**: Methods doing too much
- **Feature Envy**: Methods using other classes' data excessively
- **Data Classes**: Classes with only getters/setters
- **Refused Bequest**: Subclasses not using inherited methods

**Implementation Smells**:
- **Duplicated Code**: Copy-paste programming
- **Dead Code**: Unreachable or unused code
- **Primitive Obsession**: Overuse of primitive types
- **Long Parameter Lists**: Methods with too many parameters
- **Magic Numbers**: Hard-coded values without explanation

**Architectural Smells**:
- **Shotgun Surgery**: Changes scattered across many classes
- **Divergent Change**: Class changing for multiple reasons
- **Parallel Inheritance Hierarchies**: Coupled inheritance trees
- **Inappropriate Intimacy**: Classes knowing too much about each other

#### B. Smell Impact Assessment
For each smell category:
- **Prevalence**: How widespread is this smell?
- **Severity**: How much does it impact maintainability?
- **Trend**: Is it getting better or worse over time?
- **Root Cause**: Why does this smell occur in this codebase?

### 4. Security and Reliability Analysis

#### A. Security Vulnerability Detection

**Common Vulnerability Patterns**:
- **Input Validation Issues**: Injection vulnerabilities
- **Authentication/Authorization Flaws**: Access control problems
- **Cryptographic Issues**: Weak encryption, poor key management
- **Error Handling Problems**: Information disclosure risks
- **Resource Management Issues**: Memory leaks, resource exhaustion

**Dependency Security Assessment**:
- Known vulnerabilities in dependencies (CVE database)
- Outdated library versions
- Transitive dependency risks
- License compliance issues

#### B. Reliability Issue Detection

**Potential Bug Patterns**:
- **Null Pointer Risks**: Unguarded null dereferences
- **Resource Leaks**: Unclosed files, connections, streams
- **Concurrency Issues**: Race conditions, deadlock potential
- **Exception Handling Gaps**: Unhandled exceptions, poor error recovery
- **Type Safety Issues**: Unsafe casts, conversion problems

### 5. Performance and Scalability Analysis

#### A. Performance Anti-Pattern Detection

**Common Performance Issues**:
- **N+1 Query Problems**: Database query inefficiencies
- **Premature Optimization**: Complex code without benefit
- **Memory Inefficiencies**: Unnecessary object creation
- **Algorithm Inefficiencies**: Poor algorithm choices
- **Caching Opportunities**: Repeated expensive calculations

#### B. Scalability Risk Assessment
- **Resource Usage Patterns**: Memory and CPU intensive operations
- **Synchronization Points**: Potential bottlenecks
- **State Management**: Session state, global variables
- **External Dependencies**: Blocking calls, timeouts

### 6. Code Style and Convention Analysis

#### A. Consistency Assessment

**Naming Conventions**:
- Variable, function, class naming consistency
- Package/module organization patterns
- Constant and configuration naming

**Code Structure**:
- Indentation and formatting consistency
- Comment quality and frequency
- Import organization
- File organization patterns

#### B. Documentation Quality
- **API Documentation**: Public interface documentation
- **Inline Comments**: Code explanation quality
- **README and Setup**: Project documentation
- **Architecture Documentation**: High-level design docs

### 7. Trend Analysis and Historical Context

#### A. Quality Trend Tracking
If historical data is available:
- Code quality metric trends over time
- Technical debt accumulation patterns
- Defect injection rates
- Refactoring effectiveness

#### B. Correlation Analysis
- Relationship between complexity and bug reports
- Connection between code smells and maintenance effort
- Impact of coding standards on quality metrics

## Output Format

### 1. Executive Summary

**Code Quality Overview**:
- Overall quality score (if available)
- Critical issues requiring immediate attention
- Technical debt estimation (hours/days to resolve)
- Quality trend assessment

**Top Priority Issues**:
1. **[Critical Issue]**: Business impact and urgency
2. **[High Priority]**: Risk assessment and timeline
3. **[Medium Priority]**: Monitoring and improvement approach

### 2. Detailed Metrics Report

#### Code Complexity Analysis
| Component | Cyclomatic Complexity | Cognitive Complexity | Lines of Code | Maintainability Index |
|-----------|----------------------|---------------------|---------------|----------------------|
| PaymentService | 45 (High) | 67 (Very High) | 850 | 23 (Poor) |
| UserController | 28 (Medium) | 31 (Medium) | 420 | 68 (Good) |

#### Coupling and Cohesion Assessment
| Module | Afferent Coupling | Efferent Coupling | Instability | Abstractness | Distance |
|--------|------------------|------------------|-------------|--------------|----------|
| Core | 12 | 3 | 0.2 | 0.8 | 0.0 |
| Utils | 8 | 15 | 0.65 | 0.1 | 0.45 |

### 3. Code Smell Analysis

#### Critical Code Smells (Fix Immediately)
For each critical smell:

**Smell: [Name]**
- **Location**: [File paths and line numbers]
- **Instances**: [Number of occurrences]
- **Impact**: [Maintainability/Performance/Security impact]
- **Root Cause**: [Why this smell exists]
- **Refactoring Strategy**: [How to fix]
- **Effort Estimate**: [Time to resolve]

#### Code Smell Distribution
```
God Classes: 8 instances (Core: 5, Utils: 2, UI: 1)
Long Methods: 23 instances (Services: 15, Controllers: 8)
Duplicated Code: 35% similarity in payment modules
Dead Code: 12% of codebase (mostly in legacy modules)
```

### 4. Security and Reliability Issues

#### Security Vulnerabilities
| Severity | Type | Count | Examples | Remediation Priority |
|----------|------|-------|----------|---------------------|
| Critical | SQL Injection | 3 | UserService.findBy() | Immediate |
| High | XSS | 7 | Comment rendering | This sprint |
| Medium | Info Disclosure | 12 | Error messages | Next sprint |

#### Reliability Risks
- **Null Pointer Risks**: 45 potential locations
- **Resource Leaks**: 8 unclosed file handles
- **Exception Handling**: 23 unhandled exception paths

### 5. Performance Analysis

#### Performance Hotspots
1. **[Component]**: Performance issue and optimization opportunity
2. **[Component]**: Scalability concern and mitigation approach

#### Algorithm Efficiency
- Inefficient sorting algorithms in DataProcessor
- O(n²) operations in ReportGenerator
- Missing caching in ConfigurationService

### 6. Code Style and Documentation Assessment

#### Style Consistency Score
- **Naming Conventions**: 85% consistent
- **Formatting**: 92% consistent  
- **Comment Coverage**: 35% of public APIs documented
- **Architecture Documentation**: 60% complete

### 7. Prioritized Improvement Roadmap

#### Immediate Actions (< 1 week)
- Fix critical security vulnerabilities
- Address highest complexity functions
- Remove dead code

#### Short-term Improvements (1-4 weeks)
- Refactor god classes
- Implement missing error handling
- Add unit tests for complex functions

#### Strategic Refactoring (1-3 months)
- Architecture pattern consistency improvements
- Comprehensive documentation update
- Technical debt reduction initiative

### 8. Quality Monitoring Strategy

#### Continuous Quality Gates
- Complexity thresholds for new code
- Code coverage requirements
- Security scanning integration
- Style checking automation

#### Quality Metrics Dashboard
- Daily quality metric tracking
- Technical debt trend monitoring
- Code smell introduction rates
- Refactoring effectiveness measurement

## Success Criteria
- Comprehensive code quality assessment with quantified metrics
- Identified critical issues with business impact assessment
- Clear prioritization based on risk and effort
- Actionable refactoring roadmap with timelines
- Quality monitoring strategy for continuous improvement
- Team awareness of code quality standards and practices

$ARGUMENTS