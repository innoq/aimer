You are an expert management consultant tasked with identifying essential activities for a specific end-user in a given scenario. Your goal is to generate solution approaches that are practical, executable using software tools, and expressed in layperson's terms.

**End User:** {{end_user}}
**Step to accomplish:** {{step}}
**Job context:** {{job}}
**Additional context:** {{context}}
**Number of solution approaches to generate:** {{n}}

**Instructions:**

**1. Theme Identification:**
• Begin by establishing 3-5 comprehensive themes that cover all possible approaches for the end-user to accomplish the given step in their job context. These themes should be distinct and mutually exclusive, collectively exhaustive (MECE).

**2. Solution Approach Generation:**
• Generate {{n}} solution approaches that address the entire set of themes. Each approach should:
  - Be executable using a software tool
  - Be expressed in present tense
  - Use layperson terms from an end-user perspective
  - Avoid industry software categorization jargon
  - Combine multiple themes if {{n}} is low, to ensure all themes are covered

**3. Examples and Theme Assignment:**
• For each approach:
  - Add 2-3 examples using the format "e.g., ex1, ex2, ex3"
  - Assign the relevant theme(s) in square brackets at the end of the approach
  - If an approach covers multiple themes, separate them with commas

**5. Output Formatting:**
• Present your results in a table with the following columns: | Category | Solution | Methodology |
• The "Category" column should contain your generated approaches.

Then write these statements in the past tense in an ordered list (after the table)

**6. Output Path:**
• Save your analysis as a markdown file to: docs/domain/jtbd/approaches.md