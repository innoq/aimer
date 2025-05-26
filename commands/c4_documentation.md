You are a senior software architect tasked with creating comprehensive C4 architecture documentation based on this Git repository. Your goal is to thoroughly analyze this repository and generate complete C4 architecture documentation.

You will be provided with the following input variables:

1. {{LANGUAGE}}: The language in which the documentation should be written (e.g., "deutsch", "english", "français").
2. {{TARGET_DIR}}: The target directory for the documentation files (e.g., "docs/architecture/c4", "documentation/c4").

$ARGUMENTS

First, analyze the repository data thoroughly:

1. Perform a static code analysis:
   - Examine the folder structure and files in the repository
   - Identify technologies, frameworks, and programming languages used
   - Recognize architectural patterns and principles
   - Extract external dependencies from relevant files
   - Analyze configuration files (Docker, Kubernetes, CI/CD, etc.)

2. Analyze the Git history:
   - Examine commit patterns and frequency to identify development focus areas
   - Investigate contributor activities to identify system experts
   - Analyze file change patterns to identify coupled components
   - Identify frequently changed files (potential hotspots)
   - Detect architectural changes over time through commit analysis

3. Review existing documentation:
   - Search the repository for existing architecture documentation
   - Analyze README files, wiki contents, and doc folders
   - Extract information from comments and inline documentation
   - Identify existing diagrams or architecture sketches

4. Analyze deployment and infrastructure:
   - Examine Dockerfiles, Kubernetes manifests, and cloud configurations
   - Identify deployment environments and strategies
   - Recognize infrastructure-as-code definitions
   - Analyze monitoring and logging configurations

Next, generate the C4 model documentation:

1. Create the following directory structure in the project:

```
{{TARGET_DIR}}/
├── README.md (Overview and navigation)
├── context.md (System Context Diagram)
├── containers.md (Container Diagram)
├── components.md (Component Diagram)
├── deployment.md (Deployment Diagram)
├── decisions.md (Architecture decisions based on Git history)
└── evolution.md (Architecture evolution based on Git analysis)
```

2. For each file, create the content as follows:

   a. README.md:
      - Introduction to the C4 model and its purpose
      - Brief description of the product/system
      - Overview of the architecture artifacts
      - Navigation to individual diagram files
      - Information about documentation currency
      - Guidelines for maintaining the documentation

   b. context.md:
      - Explanation of the System Context Diagram
      - Mermaid diagram of the system context
      - Description of main users and external systems
      - System boundaries and responsibilities
      - Business context and goals

   c. containers.md:
      - Explanation of the Container Diagram
      - Mermaid diagram of main containers (applications, databases, etc.)
      - Detailed description of each container
      - Technology stack and deployment properties
      - Inter-container communication and protocols

   d. components.md:
      - Explanation of the Component Diagram
      - Mermaid diagram of main components (focused on the most important container)
      - Description of each component and its responsibilities
      - Internal communication paths and data flows
      - Architectural patterns and principles

   e. deployment.md:
      - Explanation of the Deployment Diagram
      - Mermaid diagram of the deployment architecture
      - Infrastructure elements and their relationships
      - Deployment environments (Development, Staging, Production)
      - Scaling strategies and load balancing

   f. decisions.md:
      - Architecture decisions based on Git history analysis
      - Identified architectural changes over time
      - Rationale for important technical decisions
      - Lessons learned from development history

   g. evolution.md:
      - Architecture evolution based on Git analysis
      - Temporal development of the architecture
      - Identified trends and patterns in development
      - Predictions and recommendations for future development

3. Use the following Mermaid diagram types:
   - Context & Container: `flowchart TD` or `graph TD`
   - Components: `flowchart TD` with subgraphs
   - Deployment: `flowchart TD` with deployment-specific notations

4. Ensure your documentation meets the following quality criteria:
   - Completeness: All identified system elements are documented
   - Currency: Documentation reflects the current state of the codebase
   - Comprehensibility: Diagrams are self-explanatory, descriptions are clear and precise
   - Maintainability: Documentation is integrated into version control

Generate all files in Markdown format with embedded Mermaid diagrams. Use the language specified in {{LANGUAGE}} for all texts and label all diagrams accordingly.

Important notes:

- Base your analysis solely on the available repository data
- Do not make assumptions about unavailable information
- Explicitly mark uncertainties and assumptions
- Prioritize clarity and comprehensibility over completeness
- Use Git history as a valuable source of information for architectural decisions

Your final output should consist of the content for each of the files mentioned above (README.md, context.md, containers.md, components.md, deployment.md, decisions.md, and evolution.md), written in the specified language and formatted in Markdown with embedded Mermaid diagrams. Do not include any additional commentary or explanations outside of the file contents themselves.
