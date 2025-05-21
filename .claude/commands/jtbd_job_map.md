You are an expert in Jobs-to-be-Done (JTBD) theory tasked with creating a comprehensive job map. Your goal is to generate a list of job steps that consider each phase of the JTBD framework for the following scenario:

**Job:** {{job}}
**Context:** {{context}}
**Focus:** {{focus}}
**End User:** {{end_user}}
**Fidelity:** {{fidelity}}
**Start Point:** {{start_point}}
**End Point:** {{end_point}}

Before generating the job map, carefully consider these eight (8) instructions.

1. JTBD Framework: Cover these 9 sequential phases in your job map:
   ◦ Define - in the define phase, we want to know what aspects of getting the job done need to be defined, planned, or assessed by the {{end_user}} upfront in order to proceed.
   ◦ Locate - in the locate phase, we want to know what items or resources - tangible or intangible - must be located, gathered, collected, accessed, or retrieved by the {{end_user}} to do the job.
   ◦ Prepare - in the prepare phase, we want to know how the {{end_user}} must prepare or integrate the inputs, or the environment(s), from the Locate step to do the job.
   ◦ Confirm - in the confirm phase, we want to know what the {{end_user}} must verify, prioritize, or decide before doing the job in order to be successful.
   ◦ Execute - in the execute phase, we want to know the primary thing the {{end_user}} must do to execute the job successfully.
   ◦ Monitor - in the monitor phase, we want to know what the {{end_user}} must monitor in order to ensure the job is executed successfully.
   ◦ Resolve - in the resolve phase, we want to know what problem the {{end_user}} might need to troubleshoot, restore, or fix for the job to be completed successfully,
   ◦ Modify - in the modify phase, we want to know what the {{end_user}} might need to alter, adjust, or modify for the job to completed successfully.
   ◦ Conclude - in the conclude phase, we want to know what the {{end_user}} must do to finish the job.
   
   Each phase represents what the user must accomplish, not how they do it.

2. Step Generation:
   ◦ Create at least one step per phase, more if necessary.
   ◦ Begin each step with a verb.
   ◦ Focus on what the user is trying to accomplish faster, with better output, or better throughput.
   ◦ Don't assume methods or solutions unless explicitly provided in the job or context.
   ◦ Only reference the phase name in a job step if absolutely necessary.

3. Fidelity Requirements: Prioritize adherence to the specified fidelity level, and only deviate if necessary with explicit justification.
   ◦ Low: 10-12 steps
   ◦ Medium: 13-14 steps
   ◦ High: High (15-18 steps, deviation only with thorough justification)
   
   If you determine a deviation from the fidelity range is needed for a more complete job map, you MUST provide a detailed explanation of why the additional steps are necessary, how they maintain MECE, and why they add value beyond the established scope. Never skip this instruction.

4. MECE Principle: Ensure steps are Mutually Exclusive and Collectively Exhaustive (MECE) and in a logical order of precedence and dependence.

5. Formatting: Format each step as follows:
   1. **Step Name** - The ability to [explanation].
   2. Use the exact same output format if the user inputs an updated variable. Every response should be the same output format unless otherwise instructed

6. Scoping:
   1. Begin the job map at {{start_point}}, if included. Otherwise default to the universal phases
   2. Conclude the job map at {{end_point}}, if included. Otherwise default to the Conclude phase of the universal phases
   3. Don't include steps before the {{start_point}} or after the {{end_point}}.
   4. Consider the focus specified (B2B versus B2C - this is especially important in journey mapping)

7. Execution Phase: Always include at least one step in the Execute phase that reflects the core objective of the job.

8. Final Check: Ensure the job map makes sense when placed in this structure: "As a(n) {{end_user}} who is {{job}} {{context}} you need to [generated output]"

**Process:**

Think step by step, but only keep a minimum draft for each thinking step, with 5 words at most.

1. Analyze the job and context
2. For each of the 9 JTBD phases:
   a. Consider potential steps for the phase
   b. Brainstorm at least 3 potential steps
   c. Evaluate the MECE principle for the steps in this phase
3. Check fidelity requirements and adjust the number of steps if necessary
4. Verify scoping constraints
5. Generate the job map

**Output Structure:**

1. **Step Name** - The ability to [explanation].
2. **Another Step Name** - The ability to [explanation]. [Additional steps as needed]

**Output Path:**
• Save your analysis as a markdown file to: docs/domain/jtbd/job_map.md