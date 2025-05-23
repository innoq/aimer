# Quality Scenario Analysis

## Purpose
Evaluate architecture against quality requirements using concrete, measurable scenarios based on the ATAM (Architecture Tradeoff Analysis Method) approach.

## Instructions
1. For each quality attribute (from ISO 25010) relevant to the system:
   - Performance efficiency
   - Reliability
   - Security
   - Maintainability
   - Usability
   - Compatibility
   - Portability
   - Functional suitability
2. Create concrete quality scenarios using this template:
   - **Source**: What triggers the scenario (user, system, external)
   - **Stimulus**: The specific event or condition
   - **Artifact**: Which part of the system is affected
   - **Environment**: Under what conditions (normal, peak load, failure)
   - **Response**: How the system should react
   - **Response Measure**: How to quantitatively measure success
3. For each scenario, analyze:
   - If the current architecture supports this requirement
   - Which architectural decisions influence this scenario
   - Tradeoffs made that affect this quality attribute
   - Architectural risks related to this scenario
   - Sensitivity points where small changes have large quality impacts
4. Evaluate each scenario by:
   - Rating how well the current architecture supports it (1-5)
   - Identifying architectural decisions that positively or negatively affect it
   - Determining if there are architectural approaches that would better support it
   - Assessing difficulty of implementing necessary changes
5. Identify quality attribute tradeoffs:
   - Where improving one quality attribute degrades another
   - Whether current tradeoffs align with business priorities
   - Alternative approaches with different tradeoff balances

## Output Format
Provide a structured report with sections for:
1. Quality attributes analyzed and their business importance
2. Concrete scenarios for each quality attribute
3. Architectural support evaluation for each scenario
4. Identified risks, sensitivity points, and tradeoffs
5. Recommended architectural improvements

$ARGUMENTS
