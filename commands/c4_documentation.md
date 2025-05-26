Create comprehensive C4 architecture documentation based on this Git repository. Thoroughly analyze this repository and generate complete C4 architecture documentation.

Analyze the repository data thoroughly:

**Static Code Analysis:**
- Examine the folder structure and files in the repository
- Identify technologies, frameworks, and programming languages used
- Recognize architectural patterns and principles
- Extract external dependencies from relevant files
- Analyze configuration files (Docker, Kubernetes, CI/CD, etc.)

**Git History Analysis:**
- Examine commit patterns and frequency to identify development focus areas
- Investigate contributor activities to identify system experts
- Analyze file change patterns to identify coupled components
- Identify frequently changed files (potential hotspots)
- Detect architectural changes over time through commit analysis

**Documentation Review:**
- Search the repository for existing architecture documentation
- Analyze README files, wiki contents, and doc folders
- Extract information from comments and inline documentation
- Identify existing diagrams or architecture sketches

**Deployment and Infrastructure:**
- Examine Dockerfiles, Kubernetes manifests, and cloud configurations
- Identify deployment environments and strategies
- Recognize infrastructure-as-code definitions
- Analyze monitoring and logging configurations

Generate the C4 model documentation as a complete set of files:

**README.md**: Introduction to the C4 model and its purpose, brief description of the product/system, overview of the architecture artifacts, navigation to individual diagram files, information about documentation currency, and guidelines for maintaining the documentation.

**context.md**: Explanation of the System Context Diagram, Mermaid diagram of the system context, description of main users and external systems, system boundaries and responsibilities, and business context and goals.

**containers.md**: Explanation of the Container Diagram, Mermaid diagram of main containers (applications, databases, etc.), detailed description of each container, technology stack and deployment properties, and inter-container communication and protocols.

**components.md**: Explanation of the Component Diagram, Mermaid diagram of main components (focused on the most important container), description of each component and its responsibilities, internal communication paths and data flows, and architectural patterns and principles.

**deployment.md**: Explanation of the Deployment Diagram, Mermaid diagram of the deployment architecture, infrastructure elements and their relationships, deployment environments (Development, Staging, Production), and scaling strategies and load balancing.

**decisions.md**: Architecture decisions based on Git history analysis, identified architectural changes over time, rationale for important technical decisions, and lessons learned from development history.

**evolution.md**: Architecture evolution based on Git analysis, temporal development of the architecture, identified trends and patterns in development, and predictions and recommendations for future development.

Use the following Mermaid diagram types:
- Context & Container: `flowchart TD` or `graph TD`
- Components: `flowchart TD` with subgraphs
- Deployment: `flowchart TD` with deployment-specific notations

Ensure your documentation meets these quality criteria:
- Completeness: All identified system elements are documented
- Currency: Documentation reflects the current state of the codebase
- Comprehensibility: Diagrams are self-explanatory, descriptions are clear and precise
- Maintainability: Documentation is integrated into version control

Important notes:
- Base your analysis solely on the available repository data
- Do not make assumptions about unavailable information
- Explicitly mark uncertainties and assumptions
- Prioritize clarity and comprehensibility over completeness
- Use Git history as a valuable source of information for architectural decisions

Your final output should consist of the content for each of the files mentioned above (README.md, context.md, containers.md, components.md, deployment.md, decisions.md, and evolution.md), formatted in Markdown with embedded Mermaid diagrams. Do not include any additional commentary or explanations outside of the file contents themselves.

$ARGUMENTS
