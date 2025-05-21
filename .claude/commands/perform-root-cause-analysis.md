# Root Cause Analysis Prompt

## Purpose
Perform a systematic root cause analysis of reported system symptoms to identify underlying causes rather than treating visible symptoms.

## Instructions
1. Analyze the following system symptoms: 
   - [List reported symptoms such as slow performance, poor UI responsiveness, etc.]

2. For each symptom, identify possible technical causes across different system layers:
   - Frontend (UI, client-side code)
   - Backend services
   - Database
   - Network
   - Infrastructure
   - External dependencies

3. Trace connections between symptoms and potential root causes by analyzing:
   - Log files and error messages
   - Performance metrics
   - System monitoring data
   - Code structure and dependencies
   - Recent changes and deployments

4. For each symptom, provide:
   - Likely root cause(s)
   - Evidence supporting this determination
   - Whether multiple symptoms may trace back to the same root cause
   - Severity assessment (critical, high, medium, low)

5. Prioritize identified root causes based on:
   - Impact on system functionality
   - Number of symptoms affected
   - Business criticality
   - User experience degradation

6. For each prioritized root cause, recommend:
   - Diagnostic steps to confirm the cause
   - Short-term mitigation strategies
   - Long-term resolution approaches

## Output Format
Provide a structured report with sections for:
1. Summary of symptoms analyzed
2. Root causes identified with supporting evidence
3. Symptom-to-cause mapping
4. Prioritized remediation recommendations