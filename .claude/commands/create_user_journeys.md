# Custom Prompt: Create Multiple User Journeys

Generate comprehensive user journey maps based on product documentation (PRD, JTBD analysis) and existing personas. These journeys should document the end-to-end experiences of different users accomplishing specific goals with the product.

## Input Sources
- Product Vision: docs/product/product-vision.md
- Product Requirements Document (PRD): docs/product/product-requirements-document.md
- Jobs to Be Done analysis: docs/domain/jtbd/
- Proto Personas: docs/product/proto-personas/

## Instructions

Create multiple user journeys that map how different personas navigate through the product to accomplish key goals. Each journey should connect to existing product requirements, identified jobs-to-be-done, and reflect realistic user behavior patterns.

For each journey, follow this structure:

1. **Persona Selection**
   - Choose an appropriate persona from the existing documentation
   - Briefly summarize key characteristics relevant to this journey
   - Explain why this persona is well-suited for this specific journey

2. **Goal Definition**
   - Clearly state what the user is trying to accomplish
   - Connect this goal to specific jobs from the JTBD analysis
   - Explain the motivation and context for this goal

3. **Starting Situation**
   - Describe the user's situation before beginning the journey
   - Note any existing tools, workarounds, or pain points
   - Establish the trigger that initiates this journey

4. **Journey Mapping**
   - Divide the journey into logical phases (5-8 phases recommended)
   - For each phase:
     - Identify specific touchpoints (interactions with the product)
     - Describe user actions, thoughts, and system responses
     - Note emotional responses at each touchpoint (positive, negative, neutral)
     - Identify potential pain points, moments of delight, or confusion
     - Connect to specific features mentioned in the PRD

5. **Outcome**
   - Describe the end result of the journey
   - Explain how the user's goal was met (or not met)
   - Note any follow-up actions or next steps

6. **Optimization Potential**
   - Identify 2-4 areas where the experience could be improved
   - Connect improvement suggestions to specific pain points in the journey
   - Consider both short-term fixes and longer-term enhancements

7. **JTBD Alignment**
   - Explicitly connect the journey to specific steps in relevant job maps
   - Show how the journey addresses functional, emotional, and social dimensions of jobs

## Number and Selection of Journeys

Create 3-5 distinct user journeys that:
- Cover different personas (at least 2-3 different personas)
- Address different primary goals or use cases
- Represent varying levels of user expertise (novice to advanced)
- Showcase different aspects of the product functionality
- Potentially illustrate how different users might interact with each other through the product

## Example Format

Each journey should be saved as a separate markdown file using the naming convention: `user-journey-[persona-name]-[goal-keyword].md`

For example:

```markdown
# User Journey: [Journey Name/Goal]

## Persona
**[Persona Name]**
[Brief description of the persona, focusing on characteristics relevant to this journey]

## Goal
[Clear statement of what the user wants to accomplish]

## Starting Situation
[Description of the user's context before starting the journey]

## Journey

### Phase 1: [Phase Name]
**Touchpoint 1: [Interface Element/Screen Name]**
- [Description of what the user does]
- [Description of system response]
- **Emotion**: [User's emotional state]

[Continue with additional phases and touchpoints]

## Outcome
[Description of the end result and whether the goal was achieved]

## Optimization Potential
- [Specific suggestion for improvement]
- [Specific suggestion for improvement]

## Alignment with JTBD
[Explicit connections to specific steps in the job map or JTBD framework]
```

Additionally, create a summary file named `README.md` inside the user-journeys folder that provides a comparative analysis of all journeys:

```markdown
# User Journeys Overview

## Summary of Journeys
- Journey 1: [Brief description]
- Journey 2: [Brief description]
- Journey 3: [Brief description]

## Comparative Analysis
[Brief analysis of how these journeys relate to each other, overlap, or highlight different aspects of the product]

## Key Insights
[Overall insights gained from analyzing the complete set of user journeys]
```

## Important Considerations

1. Make each journey realistic by including:
   - Alternative paths where appropriate
   - Potential errors or misunderstandings
   - Varying emotional states throughout the journey
   - Both digital and non-digital touchpoints if relevant

2. Consider the implementation status:
   - For already implemented features, be specific about actual interfaces
   - For planned features, base interactions on the PRD specifications
   - Note any gaps or assumptions about future implementations

3. Ensure the journeys reflect:
   - Each persona's specific characteristics, preferences, and pain points
   - Contextual factors that influence the experience
   - Realistic emotional responses throughout the process
   - The sequential and iterative nature of real user interactions

4. Highlight connections between journeys:
   - Show where different users' paths might intersect
   - Identify shared pain points across different personas
   - Note any conflicting needs between different user types

The final output should be a set of separate markdown files (one for each journey), plus an overview file (README.md), all saved to the docs/product/user-journeys/ directory. Each file should provide a cohesive narrative that helps stakeholders understand diverse user experiences, identify potential improvements, and align development priorities with various user needs.