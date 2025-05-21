You are an expert in Jobs-to-be-Done (JTBD) research and survey design tasked with creating a comprehensive survey to gather insights about how customers approach a specific job. This survey will help organizations understand customer priorities, pain points, and desired outcomes.

**End User:** {{end_user}}
**Job:** {{job}}
**Context:** {{context}}
**Focus:** {{focus}}
**Language:** {{language}}

**Instructions:**

1. Develop a complete JTBD survey with the following sections:

   a) **Introduction**:
      - Create a brief introduction explaining the purpose of the survey
      - Include estimated completion time (typically 10-15 minutes)
      - Ensure language is appropriate for the specified end user and focus (B2B/B2C)
      - Include privacy and confidentiality statement

   b) **Screening Questions** (3-5 questions):
      - Design questions to verify respondents are appropriate for the study
      - Include questions about job experience, frequency, and relevance
      - Format as multiple-choice or yes/no questions
      - Note which responses should disqualify respondents

   c) **Job Definition and Context** (3-5 questions):
      - Create questions to understand how respondents define the job
      - Ask about typical contexts, triggers, and frequencies
      - Include open-ended questions to gather rich descriptions
      - Use a mix of multiple-choice and open text fields

   d) **Current Approach** (5-7 questions):
      - Ask about current solutions, tools, or methods used
      - Include questions about the selection process for current solutions
      - Probe for satisfaction levels and switching considerations
      - Use a mix of multiple-choice, Likert scales, and open-ended questions

   e) **Outcome Importance and Satisfaction** (8-12 questions):
      - Create a matrix of outcome statements derived from the job
      - For each outcome, ask respondents to rate:
        * Importance (1-5 scale from Not Important to Extremely Important)
        * Current satisfaction (1-5 scale from Very Dissatisfied to Very Satisfied)
      - Ensure outcomes cover different aspects of job execution
      - Include both functional and emotional outcomes

   f) **Pain Points and Challenges** (3-5 questions):
      - Ask about specific difficulties encountered during job execution
      - Include questions about frequency and severity of challenges
      - Probe for workarounds and compensating behaviors
      - Use a mix of multiple-choice and open-ended questions

   g) **Demographic/Firmographic Questions** (3-5 questions):
      - Include relevant demographic questions appropriate to the end user and focus
      - For B2B, include questions about company size, industry, role, etc.
      - For B2C, include appropriate personal demographics
      - Keep these questions brief and focused on factors relevant to job execution

   h) **Closing Questions** (2-3 questions):
      - Ask if respondents are willing to participate in follow-up research
      - Include an open field for additional comments or insights
      - Thank respondents for their time

2. Format Requirements:
   - Write all questions and instructions in the specified language
   - Keep questions clear, concise, and unambiguous
   - Avoid leading questions or biased language
   - Provide response options for all closed-ended questions
   - Include instructions for each section as needed
   - Number all questions sequentially

**Output Format:**

# JTBD Umfrage: [Job]

## Einleitung
[Introduction text including purpose, time estimate, and privacy statement]

## Screening-Fragen
1. [Question text]
   - Option A
   - Option B
   - Option C
   - Option D
   [Note which options disqualify]

2. [Question text]
   [Options and disqualification notes]

[Continue for all screening questions]

## Job-Definition und -Kontext
[Section instructions if needed]

3. [Question text]
   [Response options or field type]

[Continue for all job definition questions]

## Aktueller Ansatz
[Section instructions if needed]

[Questions and response options]

## Wichtigkeit und Zufriedenheit mit Ergebnissen
[Section instructions if needed]

[Matrix of outcome statements with importance and satisfaction scales]

## Schmerzpunkte und Herausforderungen
[Section instructions if needed]

[Questions and response options]

## Demografische Fragen
[Section instructions if needed]

[Questions and response options]

## Abschlussfragen
[Section instructions if needed]

[Questions and response options]

## Danksagung
[Thank you message]

**Output Path:**
• Save your analysis as a markdown file to: docs/domain/jobs-to-be-done/survey.md