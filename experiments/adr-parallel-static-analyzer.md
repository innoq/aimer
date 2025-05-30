# ADR Parallel Static Code Analyzer

## Purpose

Analyze project structure, architectural patterns, and technology choices to identify architectural decisions for ADR documentation.

## Context

This sub-agent performs static analysis of the codebase to extract architectural insights without executing the code. It focuses on structural patterns, technology stacks, and design decisions evident in the code organization.

## Instructions

1. **Optional: Use Static Analysis Tools**
   Consider using language-specific static analysis tools for deeper insights:
   - **JavaScript/TypeScript**: ESLint, TSLint, dependency-cruiser, madge
   - **Python**: pylint, flake8, bandit, vulture, pyreverse
   - **Java**: SpotBugs, PMD, Checkstyle, jdepend, SonarQube
   - **C#/.NET**: Roslyn analyzers, StyleCop, FxCop, NDepend
   - **Go**: go vet, staticcheck, golangci-lint, go-critic
   - **Ruby**: RuboCop, Reek, Brakeman, rails_best_practices
   - **PHP**: PHPStan, Psalm, PHPMD, phpcs
   - **Rust**: clippy, cargo-audit, cargo-outdated
   - **General**: tokei (lines of code), scc (code complexity), cloc
   
   Run appropriate tools based on detected languages and extract architectural insights from their output.

2. **Project Structure Analysis**
   - Map directory hierarchy and module organization
   - Identify architectural layers (presentation, business, data)
   - Detect monolithic vs microservices patterns
   - Analyze package/module dependencies
   - Use dependency analysis tools to visualize module relationships

3. **Technology Stack Detection**
   - Identify programming languages and versions
   - List frameworks and major libraries
   - Detect build tools and dependency managers
   - Note any technology migrations or deprecated components
   - Use package manager files (package.json, pom.xml, go.mod, Gemfile, etc.) for accurate dependency analysis

4. **Architectural Pattern Recognition**
   - Identify design patterns (MVC, MVVM, Clean Architecture, etc.)
   - Detect architectural styles (REST, GraphQL, event-driven, etc.)
   - Analyze separation of concerns
   - Identify cross-cutting concerns handling

5. **Code Organization Decisions**
   - Module boundaries and interfaces
   - Naming conventions and standards
   - Code generation or scaffolding patterns
   - Shared libraries and utilities structure

6. **Quality and Standards**
   - Coding standards and linting rules
   - Static analysis configurations
   - Code complexity thresholds
   - Documentation standards

## Output Format

```json
{
  "project_structure": {
    "type": "monolith|microservices|modular_monolith|library",
    "main_components": [
      {
        "name": "<component_name>",
        "path": "<relative_path>",
        "purpose": "<description>",
        "dependencies": ["<dep1>", "<dep2>"]
      }
    ],
    "architectural_layers": ["<layer1>", "<layer2>"],
    "module_count": <number>
  },
  "technology_stack": {
    "languages": [
      {
        "name": "<language>",
        "version": "<version>",
        "usage": "primary|secondary"
      }
    ],
    "frameworks": [
      {
        "name": "<framework>",
        "version": "<version>",
        "purpose": "<usage_description>"
      }
    ],
    "build_tools": ["<tool1>", "<tool2>"],
    "package_managers": ["<manager1>", "<manager2>"]
  },
  "architectural_patterns": [
    {
      "pattern": "<pattern_name>",
      "evidence": ["<file_or_structure>"],
      "implementation_details": "<description>",
      "confidence": "high|medium|low"
    }
  ],
  "design_decisions": [
    {
      "area": "<decision_area>",
      "choice": "<what_was_chosen>",
      "alternatives_considered": ["<alt1>", "<alt2>"],
      "rationale": "<why_this_choice>",
      "trade_offs": ["<trade_off1>", "<trade_off2>"]
    }
  ],
  "code_standards": {
    "style_guide": "<detected_style>",
    "linting_tools": ["<tool1>", "<tool2>"],
    "naming_conventions": "<description>",
    "documentation_format": "<format>"
  }
}
```

## Success Criteria

- Complete project structure mapped with all major components identified
- Technology stack accurately detected with versions where available
- At least 3 architectural patterns or design decisions identified
- Clear rationale provided for each identified decision
- Output is valid JSON that can be processed by consolidator

## $ARGUMENTS