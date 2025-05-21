# Static Code Analysis Prompt

## Purpose
Perform a comprehensive static analysis of the codebase to evaluate code quality, identify structural issues, and detect potential bugs or vulnerabilities.

## Instructions
1. Calculate and analyze code complexity metrics:
   - Cyclomatic complexity
   - Cognitive complexity
   - Method/function length
   - Class size
   - Nesting depth
   - Parameter count
   - Lines of code per module

2. Evaluate code structure and organization:
   - Package/module dependencies
   - Coupling between components
   - Inheritance hierarchies
   - Interface usage
   - Cohesion within classes/modules
   - Component isolation

3. Identify common code smells:
   - Duplicated code
   - Long methods
   - Large classes
   - Primitive obsession
   - Long parameter lists
   - Inappropriate intimacy
   - Feature envy
   - Data classes
   - Refused bequest
   - Shotgun surgery

4. Check for potential bugs and errors:
   - Null pointer dereferences
   - Resource leaks
   - Exception handling issues
   - Undefined behavior
   - Type conversion issues
   - Overflow/underflow risks
   - Off-by-one errors
   - Concurrency issues

5. Analyze code style and best practices:
   - Naming conventions
   - Comment quality and frequency
   - Consistent formatting
   - Use of design patterns
   - Adherence to language idioms
   - API usage correctness
   - Clean code principles

6. For each issue identified, provide:
   - Severity rating
   - Specific file and line numbers
   - Description of the problem
   - Potential impact
   - Suggested fix or improvement

## Output Format
Provide a structured report with sections for:
1. Executive summary with key metrics
2. Complexity hotspots with metrics
3. Structural issues identified
4. Code smells categorized by type
5. Potential bugs and defects
6. Style and best practice violations
7. Prioritized recommendations for improvement