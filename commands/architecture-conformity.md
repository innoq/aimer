# Architecture Conformity Analysis

## Purpose
Evaluate how well the implemented system conforms to the intended architecture design, identifying drift, violations, and architectural debt.

## Instructions
1. Analyze the documented architecture:
   - Architectural patterns and styles
   - Component structure and responsibilities
   - Layer definitions and boundaries
   - Integration patterns
   - Technology selections
   - Defined constraints and principles
2. Extract the actual architecture from the codebase:
   - Component dependencies
   - Package structure
   - Import relationships
   - Service dependencies
   - Layer violations
   - Technology usage
3. Identify architectural conformity issues:
   - Layer violations (e.g., bypassing layers)
   - Inappropriate component dependencies
   - Misuse of architectural patterns
   - Technology stack deviations
   - Violation of design principles
   - Excessive coupling between components
4. Analyze architectural debt:
   - Outdated architectural decisions
   - Incomplete refactorings
   - Shortcut implementations
   - Inconsistent patterns
   - Duplicated functionality
   - Workarounds and temporary fixes
5. Evaluate evolution of architecture:
   - Recent architectural changes
   - Trend toward increased/decreased conformity
   - New architectural patterns introduced
   - Abandoned architectural elements
   - Modernization efforts
6. For each violation or drift, provide:
   - Severity and impact assessment
   - Specific location and evidence
   - Potential business impact
   - Technical implications
   - Suggested resolution approach

## Output Format
Provide a structured report with sections for:

1. Summary of documented vs. actual architecture
2. Visual representation of architectural conformity
3. Major architectural violations identified
4. Architectural debt assessment
5. Architecture evolution trends
6. Prioritized recommendations for improving architectural integrity

$ARGUMENTS
