You are an expert in Jobs-to-be-Done (JTBD) theory and user story creation tasked with developing comprehensive job stories for a specific product or service. These job stories will help product teams understand the situational context in which users are trying to accomplish jobs and the motivations behind them.

**End User:** {{end_user}}
**Job:** {{job}}
**Context:** {{context}}
**Product/Service:** {{product}}
**Number of story categories:** {{categories}}
**Stories per category:** {{stories_per_category}}
**Focus:** {{focus}}

**Instructions:**

1. Analyze the job, context, and end user to identify distinct categories of situations in which the job might be performed. These categories should represent different contexts, motivations, or job aspects.

2. For each category, create the specified number of job stories using the format:
   - **When [situational context]**
   - **I want to [motivation/goal]**
   - **So that [expected outcome]**

3. Ensure each job story:
   - Begins with a specific, realistic situational trigger that prompts the job
   - Clearly articulates the user's motivation or goal in that specific context
   - Ends with a concrete, valuable outcome the user expects to achieve
   - Is written from the first-person perspective of the end user
   - Avoids specifying implementation details or solutions
   - Contains sufficient specificity to inform design decisions
   - Focuses on the job and its context, not on features or UI elements

4. Make sure the complete set of job stories:
   - Covers the full range of important situations in which the job might be performed
   - Represents varying levels of user expertise or familiarity
   - Includes both common scenarios and critical edge cases
   - Follows the MECE principle (Mutually Exclusive, Collectively Exhaustive)
   - Is prioritized with most important stories first within each category

5. After completing all job stories, add a brief section highlighting the key qualities of the job stories and how they should be used for product development.

**Output Format:**

# Job Stories für [Product/Service]

## **1. [Category Name 1]**
- **Wenn [situational context],**  
  **möchte ich [motivation/goal],**  
  **damit [expected outcome].**

- **Wenn [situational context],**  
  **möchte ich [motivation/goal],**  
  **damit [expected outcome].**

## **2. [Category Name 2]**
- **Wenn [situational context],**  
  **möchte ich [motivation/goal],**  
  **damit [expected outcome].**

- **Wenn [situational context],**  
  **möchte ich [motivation/goal],**  
  **damit [expected outcome].**

[Continue for all categories]

---

### **Qualitäten der Job Stories**
- **[Quality 1]**: [Brief explanation]
- **[Quality 2]**: [Brief explanation]
- **[Quality 3]**: [Brief explanation]
- **[Quality 4]**: [Brief explanation]

**Output Path:**
• Save your analysis as a markdown file to: docs/domain/jobs-to-be-done/job_stories.md