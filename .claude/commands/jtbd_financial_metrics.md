You are an AI assistant tasked with generating financial outcome statements for a specific end-user evaluating products or services. These statements will help companies understand their customers' financial considerations when making purchasing decisions.

**End User:** {{end_user}}
**Job:** {{job}}
**Focus:** {{focus}}
**Context:** {{context}}
**n:** {{n}}

Please follow these instructions to generate the financial outcome statements:

1. Assume the role of the specified end-user who is evaluating products or services used in the given job context.
2. Process:
   - Analyze the job, context, and focus
   - Brainstorm at least 10 potential themes. The final themes should be 30% of the number of statements to generate.
   - Evaluate the MECE principle for the financial metrics in this job and context
   - Generate the financial metrics
3. Understand that financial desired outcomes are structured as follows: [Direction of improvement] + [metric] + [object of control] + [contextual clarifier]
4. Keep in mind that for financial outcomes:
   
   - The most common metric is "cost"
   - When using "minimize the cost", the object of control should always be a noun
   - Consider the end-user's perspective and potential financial concerns across all customer journeys:
       - Product Selection
       - Product Purchase
       - Produce Receipt
       - Product Installation
       - Product Disposal
       - Product Upgrade
       - Learning to Use Product
       - Product Maintenance
       - Product Customization
       - Product Storage
       - Product Transport
       - Product Replacement
       - Product Configuration
       - Product Integration
       - Product Use
       - Product Repair
       - Product Cleaning
   
   1. Remember to include performance metrics (KPIs) that may indirectly affect financial outcomes.
   2. Generate the specified number of unique financial outcome statements, ensuring they are relevant to the end-user role and job context.
   3. Format your output as a numbered list, following this example structure: **[Direction] the [metric] of** [object of control] _[contextual clarifier]_

Before generating the final list, conduct your analysis inside <financial_analysis> tags. In this analysis:

- Identify relevant KPIs for the given job context.
- Brainstorm potential objects of control and contextual clarifiers.
- Briefly analyze how each consideration relates to the job context.

Once you've completed your analysis, present the final list of financial outcome statements.

**Output Path:**
• Save your analysis as a markdown file to: docs/domain/jtbd/financial_metrics.md