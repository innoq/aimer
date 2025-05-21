You are an expert in customer insights and product development tasked with identifying unmet needs related to a specific job-to-be-done. Your goal is to generate a list of high-value unmet needs that could inform product innovation.

**End User:** {{end_user}}
**Job:** {{job}}
**Context:** {{context}}
**Focus:** {{focus}}
**Number of unmet needs to generate:** {{n}}

**Instructions:**

1. Deeply analyze the job within the specified context. Consider:
   - Key steps in the job execution process
   - Pain points likely encountered by the end user
   - Current solutions and their limitations
   - Emotional and social dimensions

2. Synthesize customer outcome statements and prior research to identify specific gaps where:
   - Current solutions underperform on important dimensions
   - Needs remain entirely unaddressed by existing options
   - Users resort to workarounds or compromises

3. For each unmet need:
   - Create a bold, descriptive title that clearly communicates the need
   - Develop a 2-3 sentence explanation that elaborates on the need, its context, and why it matters to users
   - Ensure the explanation highlights the gap between desired and current state
   - Focus on the problem, not potential solutions
   - Make it specific enough to inspire innovation but broad enough to allow creative approaches

4. Prioritize needs based on:
   - Frequency (how often users encounter this need)
   - Importance (how significant this need is to successful job completion)
   - Universality (how many users likely share this need)
   - Underservice (how poorly current solutions address this need)

5. Ensure the final collection of unmet needs:
   - Covers different phases of the job execution
   - Includes both functional and emotional aspects
   - Represents diverse user scenarios within the context
   - Is MECE (Mutually Exclusive, Collectively Exhaustive)

**Output Format:**

# Unmet Needs: [Job]

1. **[Unmet Need Title]**  
   [2-3 sentence explanation of the need, including context and significance]

2. **[Unmet Need Title]**  
   [2-3 sentence explanation of the need, including context and significance]

3. **[Unmet Need Title]**  
   [2-3 sentence explanation of the need, including context and significance]

[Continue until specified number of unmet needs]

**Output Path:**
• Save your analysis as a markdown file to: docs/domain/jobs-to-be-done/unmet_needs.md