# Static Code Analysis for C4 Documentation

## Purpose
Analyze repository structure, technologies, and architectural patterns to provide foundational data for C4 architecture documentation.

## Context
Static code analysis reveals the technical implementation details necessary for accurate Container and Component diagrams in the C4 model.

## Instructions

1. Examine repository structure:
   - Map directory hierarchy
   - Identify project boundaries
   - Detect monorepo patterns

2. Identify technologies and frameworks:
   - Programming languages by file extension
   - Framework indicators in configuration files
   - Build tool configurations

3. Extract architectural patterns:
   - Layered architecture indicators
   - Microservices boundaries
   - Event-driven patterns

4. Analyze dependencies:
   - Package manager files (package.json, pom.xml, etc.)
   - Import statements patterns
   - External service configurations

5. Process configuration files:
   - Environment configurations
   - Database connections
   - API endpoints

## Output Format

```json
{
  "repository_structure": {
    "type": "monorepo|polyrepo|hybrid",
    "main_directories": [],
    "service_boundaries": []
  },
  "technologies": {
    "languages": {},
    "frameworks": [],
    "databases": [],
    "message_queues": []
  },
  "architectural_patterns": [],
  "dependencies": {
    "internal": [],
    "external": []
  },
  "configurations": {
    "environments": [],
    "external_services": []
  }
}
```

## Success Criteria

- All source code directories analyzed
- Technology stack completely identified
- Clear service/component boundaries detected
- Dependencies mapped with versions

$ARGUMENTS