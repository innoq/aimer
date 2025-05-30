# Architecture Decision Record (ADR)

You are tasked with generating a single Architecture Decision Record (ADR) based on the analysis of the current feature branch. Your goal is to document a relevant architectural or design decision in Markdown format.

Please follow these steps to complete your task:

1. Analyze the repository information:
   - Review the commit history, focusing on changes that indicate architectural or design decisions.
   - Look for patterns, significant changes, or comments that suggest important decisions were made.
2. Identify one relevant architectural decision from the analysis.
3. Create an ADR Markdown file with the following structure:
   - Title: "# ADR {ADR_NUMBER}: Brief title of the decision"
   - Context: Explain the background, requirements, and conflicts that led to this decision.
   - Decision: Describe what was decided, using the phrase "We will..."
   - Status: Indicate the current status (e.g., "Proposed", "Accepted", "Deprecated", "Superseded")
   - Consequences: Discuss how this decision impacts the project, both positively and negatively.
4. Follow these style guidelines:
   - Use complete sentences and paragraphs.
   - Keep entries concise, precise, and easily readable.
   - If the decision changes or supersedes a previous one, reference the relevant ADR (e.g., "superseded by ADR X").
5. Output:
   - Generate a single Markdown file representing the ADR.
   - Ensure the content is structured correctly and follows the guidelines provided.

Please provide your output in the following format:

<adr>
# ADR {ADR_NUMBER}: [Insert brief title of the decision]

## Context

[Explain the background, requirements, and conflicts that led to this decision]

## Decision

[Describe what was decided, using the phrase "We will..."]

## Status

[Indicate the current status]

## Consequences

[Discuss how this decision impacts the project, both positively and negatively]
</adr>

Remember to base your ADR solely on the information provided in the repository analysis. Do not invent or assume information that is not present in the given analysis.

$ARGUMENTS
