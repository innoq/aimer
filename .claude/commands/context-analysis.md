# Context Analysis

## Purpose
Analyze system boundaries, external interfaces, and neighboring systems to identify risks, dependencies, and potential integration issues.

## Instructions
1. Identify all external interfaces:
   - APIs (provided and consumed)
   - User interfaces
   - File interfaces
   - Message queues
   - Database connections
   - Third-party services
   - System integrations

2. For each external interface, document:
   - Interface specification or format
   - Communication protocol
   - Data format (JSON, XML, Binary, etc.)
   - Authentication mechanism
   - Rate limits or throughput constraints
   - Error handling procedures
   - SLAs or quality expectations

3. Analyze interface quality by checking:
   - Completeness of specifications
   - Versioning strategy
   - Backward compatibility provisions
   - Error reporting mechanisms
   - Monitoring capabilities
   - Test coverage

4. Identify particularly risky interfaces:
   - Interfaces with external parties/vendors
   - Manually operated interfaces
   - Interfaces without proper specifications
   - Interfaces with high volatility
   - Interfaces with high business criticality

5. Evaluate the interface implementation:
   - Adherence to specifications
   - Error handling robustness
   - Performance characteristics
   - Security measures
   - Resilience to failure
   - Monitoring and logging

6. Analyze external dependencies:
   - Which third-party services are critical?
   - What happens if external services fail?
   - Are there backup or contingency plans?
   - How are version updates to dependencies managed?

## Output Format
Provide a structured report with sections for:
1. System context diagram showing all external interfaces
2. Interface inventory with specifications and quality assessment
3. High-risk interfaces with detailed analysis
4. External dependencies and their impact
5. Recommendations for interface improvements