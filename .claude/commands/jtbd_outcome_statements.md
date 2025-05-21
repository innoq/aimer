You are an expert in Jobs-to-be-Done (JTBD) theory tasked with creating comprehensive outcome statements for a specific job. These outcome statements will help product teams understand the metrics customers use to evaluate how successfully they can execute a job.

**End User:** {{end_user}}
**Job:** {{job}} 
**Context:** {{context}}
**Focus:** {{focus}}
**Number of statements to generate:** {{n}}

**Instructions:**

1. Analyze the job, context, and focus from the perspective of the specified end user. Consider both functional and emotional aspects of job execution.

2. Identify relevant themes for outcome statements (approximately 1 theme per 4-5 statements). Themes should reflect key customer concerns, such as efficiency, reliability, etc.

3. For each theme, generate outcome statements following the format:
   - **Direction of change** (minimize, maximize, increase, decrease, etc.)
   - **Metric** (time, likelihood, frequency, number, etc.)
   - **Object of control** (the thing being improved, reduced, etc.)
   - **Contextual clarifier** (when, where, or under what conditions)

4. Ensure outcome statements are:
   - Measurable (can be evaluated on a scale)
   - Solution-agnostic (not tied to specific features)
   - Focused on outcomes, not activities
   - Free from vague adjectives and adverbs
   - Comprehensive (covering the entire job execution process)
   - MECE (Mutually Exclusive, Collectively Exhaustive)

5. Organize statements by theme, with theme names as headers.

6. Approximately 80% of statements should focus on desired improvements, while 20% should focus on preventing negative outcomes.

**Output Format:**

# Outcome Statements: [Job]

## [Theme 1]
1. [Direction] the [metric] of [object of control] [contextual clarifier].
2. [Direction] the [metric] of [object of control] [contextual clarifier].
3. [Direction] the [metric] of [object of control] [contextual clarifier].
...

## [Theme 2]
1. [Direction] the [metric] of [object of control] [contextual clarifier].
2. [Direction] the [metric] of [object of control] [contextual clarifier].
...

[Continue for all themes]

**Output Path:**
• Save your analysis as a markdown file to: docs/domain/jobs-to-be-done/outcome_statements.md