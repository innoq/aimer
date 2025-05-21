You are an AI agent tasked with generating proto-personas for a digital product based on a Product Requirements Document (PRD) and Jobs to Be Done (JTBD) analysis. Follow the recommendations of the Nielsen Norman Group for proto-personas. Create personas that are concise, precise, sufficiently diverse, and easy to understand.

The documentation of the digital product you are creating proto-personas for will be provided in the following input sources:

- Product Vision: docs/product/product-vision.md
- Product Requirements Document (PRD): docs/product/product-requirements-document.md
- Jobs to Be Done analysis: docs/domain/jtbd/

Create multiple proto-personas to cover different target groups, contexts, or use cases for the product. Each proto-persona should follow this structure:

1. Name and Brief Info
   - A short, memorable name
   - A concise description of the persona

2. Background and Demographic Characteristics
   - Age, profession, background
   - Relevant traits or circumstances
   - Focus on characteristics that directly impact how they might use the product

3. Goals and Needs
   - What are their primary objectives when using the product? 
   - Which specific jobs from the JTBD analysis are they trying to accomplish?
   - What functional, emotional, and social needs motivate their product usage?

4. Behavior and Usage Context
   - How do they currently approach similar tasks or problems?
   - When, where, and how would they interact with the product?
   - What existing tools or workarounds do they employ?

5. Challenges and Pain Points
   - What specific frustrations do they experience with current solutions?
   - What barriers might prevent them from adopting a new product?
   - What concerns or hesitations might they have?

6. Hypotheses and Assumptions
   - What assumptions are we making about this persona that need validation?
   - What questions remain about their behaviors or preferences?
   - What aspects of their experience require additional research?

7. Short Quote or Motto
   - A memorable statement that captures their perspective and priorities

Important guidelines:
- Formulate the results clearly and comprehensibly, without unnecessary details.
- Emphasize where assumptions are made that need to be validated through research at a later point.
- Directly connects to specific requirements and features in the PRD
- Aligns with the jobs identified in the JTBD analysis
- Represents realistic user behaviors and needs, not stereotypes
- Could be used immediately to inform design and prioritization decisions
- Balances specificity with flexibility for product evolution
- Could be presented on a single page for easy reference

Your output should be a list of such proto-personas in the described format, presented in Markdown. Do not explain why you chose these personas; present them compactly and clearly according to the guidelines.

Begin your response with "# Proto-Personas for [product]" and then list each persona, using appropriate Markdown formatting for headings, lists, and emphasis. Save the output to docs/product/proto-personas/