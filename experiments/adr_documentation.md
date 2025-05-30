Create or update Architecture Decision Record (ADR) documentation based on a given Git repository. Analyze the repository thoroughly and generate comprehensive ADR documentation, following common ADR best practices and conventions.

Analyze the repository content and identify significant architectural decisions made in the project. Consider:

- Key files and directories in the repository
- Technologies, frameworks, and libraries used
- Architectural patterns or design decisions  
- Project structure and organization
- Dependencies and third-party libraries
- Configuration files and environment settings
- Database schemas and data models (if applicable)
- API designs and communication protocols
- Security measures and authentication mechanisms
- Scalability and performance considerations
- Testing strategies and tools
- Project evolution over time through Git history
- Any existing .adr-dir file or ADR documentation

Create or update a series of Architecture Decision Records (ADRs) that capture the key architectural decisions made in the project. For each ADR, use the standard ADR structure:

- Title
- Status  
- Context
- Decision
- Consequences

Ensure each ADR adheres to these guidelines:

- Focus on significant architectural decisions with lasting impact
- Write as if the decision was made at the time, using present tense
- Provide clear rationales, including alternatives considered and trade-offs
- Number ADRs sequentially, starting from 0001
- Use a consistent naming convention: "NNNN-title-with-hyphens.md"
- Include references to specific parts of the codebase or configuration files
- Consider relationships between ADRs, referencing related decisions when appropriate
- If updating existing ADRs, respect their content and append or update as necessary

Present each ADR in Markdown format, enclosed in <adr> tags with the filename as an attribute. For example:

<adr filename="0001-use-postgresql-as-primary-database.md">
# 1. Use PostgreSQL as Primary Database

## Status

Accepted

## Context

[Context description]

## Decision

[Decision description]

## Consequences

[Consequences description]
</adr>

After creating or updating all the ADRs, provide a summary of the architectural decisions in the following format:

<summary>
1. [ADR title 1]
2. [ADR title 2]
3. [ADR title 3]
...
</summary>

Your final output should consist of only the ADRs and the summary.

$ARGUMENTS
