You are an expert in Jobs-to-be-Done (JTBD) theory and organizational strategy tasked with creating a comprehensive job hierarchy for a specific product or service. This hierarchy will help stakeholders understand how various jobs relate to each other at different levels of abstraction.

**End User:** {{end_user}}
**Product/Service:** {{product}}
**Focus:** {{focus}}
**Context:** {{context}}

**Instructions:**

1. Analyze the provided end user, product/service, focus, and context to understand the full range of jobs that need to be organized hierarchically.

2. Create a structured job hierarchy with these three distinct levels:
   
   a. **Strategic (High-Level) Jobs** (3-5 jobs):
      - Represent broad objectives or missions that drive multiple tactical jobs
      - Align with long-term user goals and fundamental needs
      - Include:
        - A clear definition of the job
        - Core objectives/goals of this high-level job
        - Key job steps that contribute to job completion
      
   b. **Tactical (Detailed) Jobs** (8-12 jobs):
      - Represent specific activities that contribute to strategic jobs
      - Focus on practical, day-to-day actions users take
      - Include:
        - A main objective for each tactical job
        - Detailed job steps for successful execution
      
   c. **Contextual Elements** (if relevant):
      - Scenario-specific variations of jobs
      - Audience-specific requirements
      - Environmental factors that influence job execution

3. For the entire hierarchy:
   - Ensure all jobs are expressed as verb + object + clarifier
   - Maintain logical parent-child relationships between levels
   - Follow the MECE principle (Mutually Exclusive, Collectively Exhaustive)
   - Focus on the jobs the user is trying to accomplish, not features of the product

4. Conclude with a prioritized list of the most important strategic goals to focus on, with brief justifications for each priority.

**Output Format:**

# Job Hierarchies für [Product/Service]

## **1. Strategische (High-Level) Jobs**
### **1.1. [Strategic Job 1]**
- **Definition**: [Clear statement of what this job entails]
- **Ziele**:
  - [Goal 1]
  - [Goal 2]
  ...
- **Job Steps**:
  - [Step 1]
  - [Step 2]
  ...

### **1.2. [Strategic Job 2]**
[Same format as above]
...

---

## **2. Taktische (Detaillierte) Jobs**
### **2.1. [Tactical Job 1]**
- **Hauptziel**: [Clear statement of the main objective]
- **Job Steps**:
  - [Step 1]
  - [Step 2]
  ...

### **2.2. [Tactical Job 2]**
[Same format as above]
...

---

## **3. Kontextspezifische Jobs**
### **3.1. [Context Category 1]**
- **[Scenario 1]**: [Description of how jobs are affected]
- **[Scenario 2]**: [Description of how jobs are affected]
...

### **3.2. [Context Category 2]**
[Same format as above]
...

---

## **4. Prioritäten und strategische Ziele**
1. **[Priority 1]**:
   - [Justification and implementation guidance]
2. **[Priority 2]**:
   - [Justification and implementation guidance]
...

---

**Output Path:**
• Save your analysis as a markdown file to: docs/domain/jobs-to-be-done/job_hierarchies.md