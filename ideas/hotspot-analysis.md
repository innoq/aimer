# Hotspot Analysis

## Purpose
Identify high-risk code areas by combining complexity metrics with change frequency from version control history. Focus refactoring efforts on code that is both complex and frequently modified, as this represents the highest maintenance burden.

## Context
Hotspot analysis reveals where teams spend most of their debugging and modification time. Code that is both complex and frequently changed creates a compounding risk - each change becomes harder and more error-prone. This analysis helps prioritize technical debt reduction efforts.

## Instructions

### 1. Complexity Metrics Collection

#### A. Code Complexity Measurement
For each file/function, calculate:

**Structural Complexity**:
- **Cyclomatic Complexity**: Number of decision points + 1
- **Cognitive Complexity**: Mental overhead to understand code
- **Nesting Depth**: Maximum level of nested structures
- **Function Length**: Lines of code per function
- **Class Size**: Number of methods and fields

**Coupling Metrics**:
- **Afferent Coupling**: How many modules depend on this one
- **Efferent Coupling**: How many modules this one depends on
- **Dependency Cycles**: Circular dependency participation

**Code Quality Indicators**:
- **Comment Density**: Ratio of comments to code
- **Parameter Count**: Number of function parameters
- **Return Points**: Multiple exit points in functions

#### B. Business Logic Complexity
Identify components with high business complexity:
- Decision-heavy algorithms
- Complex domain rules
- Integration orchestration
- State machines
- Calculation engines

### 2. Change Frequency Analysis

#### A. Version Control Mining
Extract from git history (last 6-12 months):

```bash
# Change frequency per file
git log --format=format: --name-only | grep -v "^$" | sort | uniq -c | sort -rn

# Contributors per file
git log --format='%an' --name-only | grep -v "^$" | sort | uniq -c

# Recent activity (last 3 months)
git log --since="3 months ago" --format=format: --name-only
```

**Key Metrics**:
- **Total Commits**: Number of commits touching each file
- **Unique Authors**: How many different people modified it
- **Recent Activity**: Changes in last 3 months
- **Bug Fix Frequency**: Commits with "fix", "bug", "hotfix" keywords
- **Churn Rate**: Lines added + lines deleted over time

#### B. Activity Patterns
- Files changed together frequently (coupling)
- Files that break often after changes
- Files modified during emergency fixes
- Files that require multiple attempts to get right

### 3. Hotspot Identification

#### A. Risk Scoring Formula
```
Hotspot Risk Score = (Complexity Score × Change Frequency Score) + Modifiers

Where:
- Complexity Score: Normalized cyclomatic complexity (0-10)
- Change Frequency Score: Normalized commit frequency (0-10)
- Modifiers: Business criticality (+2), Recent bugs (+1), Multiple authors (+1)
```

#### B. Categorization Matrix

| Complexity | Change Frequency | Category | Priority | Action |
|------------|------------------|----------|----------|---------|
| High | High | **Critical Hotspot** | P0 | Immediate refactoring |
| High | Low | **Sleeping Giant** | P2 | Monitor, document |
| Low | High | **Frequent Flyer** | P1 | Simplify interfaces |
| Low | Low | **Stable Code** | P3 | Leave alone |

### 4. Hotspot Deep Dive Analysis

For each critical hotspot (Risk Score > 7):

#### A. Change Pattern Analysis
- **Why is it changing so often?**
  - New features being added
  - Bug fixes and patches
  - Configuration changes
  - Refactoring attempts

- **Who is changing it?**
  - Single person (knowledge silo)
  - Multiple junior developers (learning curve)
  - Different teams (coordination issues)
  - Emergency fix pattern

#### B. Complexity Root Causes
- **Architectural Issues**:
  - God class anti-pattern
  - Mixed abstraction levels
  - Violation of single responsibility
  - Lack of proper encapsulation

- **Business Logic Issues**:
  - Complex domain rules
  - Multiple use cases in one place
  - Legacy decision logic
  - Undocumented edge cases

#### C. Impact Assessment
- **Development Velocity**: How much does this slow down development?
- **Bug Density**: How many bugs originate here?
- **Knowledge Dependencies**: Who understands this code?
- **Testing Challenges**: How hard is it to test changes?

### 5. Visualization and Communication

#### A. Hotspot Map Creation
Create visual representation where:
- **Size of circle** = Code complexity (lines of code or complexity score)
- **Color intensity** = Change frequency (red = high frequency)
- **Position** = Logical grouping (package/module)

#### B. Trend Analysis
Show hotspot evolution over time:
- How has complexity changed?
- Are hotspots getting worse or better?
- Impact of refactoring efforts
- New hotspots emerging

### 6. Root Cause Investigation

For top 5 hotspots, investigate:

#### A. Historical Analysis
- When did this become a hotspot?
- What triggered the complexity growth?
- Previous refactoring attempts and outcomes
- Correlation with team/business changes

#### B. Organizational Factors
- Time pressure leading to quick fixes
- Lack of architectural oversight
- Knowledge silos and handoffs
- Insufficient testing infrastructure

## Output Format

### 1. Hotspot Risk Ranking

| Rank | File/Component | Risk Score | Complexity | Change Freq | Contributors | Last Bug Fix |
|------|----------------|------------|------------|-------------|--------------|---------------|
| 1 | PaymentProcessor.java | 9.2 | Very High | 47 commits | 8 people | 2 days ago |
| 2 | UserService.cs | 8.7 | High | 32 commits | 5 people | 1 week ago |

### 2. Hotspot Categories

#### Critical Hotspots (Risk Score > 7.0)
Require immediate attention:
1. **[Component Name]**: Why critical, business impact, recommended action

#### Warning Hotspots (Risk Score 5.0-7.0)
Monitor and plan refactoring:
1. **[Component Name]**: Risk factors, monitoring strategy

#### Emerging Hotspots (Rapid Trend Increase)
New areas of concern:
1. **[Component Name]**: Why emerging, preventive actions

### 3. Detailed Hotspot Analysis

For each critical hotspot:

#### Hotspot: [Name]
- **Risk Score**: X.X/10
- **Location**: [File path and key functions]
- **Complexity Drivers**: [What makes it complex]
- **Change Drivers**: [Why it changes frequently]
- **Recent Activity**: [Last 3 months summary]
- **Business Impact**: [How failures affect business]
- **Knowledge Risk**: [Who understands this code]

### 4. Change Pattern Insights

#### Files That Change Together
Identify coupling hotspots:
- FileA + FileB change together 80% of the time → suggests tight coupling

#### Bug-Prone Areas
Components with highest bug-fix frequency:
- [Component]: X bug fixes in last 6 months

#### Emergency Fix Patterns
Code that requires urgent fixes:
- [Component]: Y emergency fixes, suggests instability

### 5. Refactoring Strategy

#### Priority 1: Critical Hotspots (Next 1-2 sprints)
1. **[Component]**:
   - Refactoring approach: [Strategy]
   - Expected effort: [Time estimate]
   - Risk mitigation: [How to safely refactor]
   - Success metrics: [How to measure improvement]

#### Priority 2: Strategic Refactoring (Next quarter)
1. **[Component]**:
   - Long-term strategy
   - Dependencies to address first
   - Team coordination needs

### 6. Prevention Strategy

#### Code Quality Gates
- Complexity thresholds for new code
- Review requirements for hotspot changes
- Automated complexity monitoring

#### Team Practices
- Pair programming for hotspot modifications
- Documentation requirements for complex areas
- Regular refactoring time allocation

### 7. Monitoring Dashboard

Proposed metrics to track:
- Hotspot risk scores over time
- Complexity trends for critical components
- Change frequency patterns
- Bug density in hotspots
- Refactoring progress metrics

## Success Criteria
- Identified all code hotspots with quantified risk scores
- Clear understanding of why hotspots exist
- Prioritized refactoring roadmap with effort estimates
- Prevention strategy to avoid new hotspots
- Monitoring approach for continuous improvement
- Team alignment on technical debt priorities

$ARGUMENTS