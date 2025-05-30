# Hotspot Analysis - Complexity Analyzer

## Purpose
Analyze codebase to measure structural complexity, coupling metrics, and code quality indicators. Generate comprehensive complexity data for hotspot risk scoring.

## Context
Code complexity is a key factor in identifying maintenance hotspots. This agent specializes in static code analysis, measuring various complexity dimensions that contribute to technical debt and maintenance burden. The analysis focuses on quantifiable metrics that correlate with bug density and change difficulty.

## Instructions

### Tool Selection

Consider using appropriate CLI-based static analysis tools if available in the environment:

**Language-Specific CLI Tools:**
- **Java**: `pmd`, `checkstyle`, `spotbugs`
- **JavaScript/TypeScript**: `eslint`, `jshint`, `complexity-report`
- **Python**: `radon cc`, `pylint`, `flake8`, `mccabe`
- **Go**: `go vet`, `golint`, `gocyclo`, `staticcheck`
- **Ruby**: `rubocop`, `reek`, `flay`, `flog`
- **C/C++**: `cppcheck`, `clang-tidy`, `complexity`
- **PHP**: `phpmd`, `phpcs`, `psalm`, `phpstan`

**Multi-Language CLI Tools:**
- `lizard` - Cyclomatic complexity analyzer (Python, Java, C/C++, JS, Ruby, PHP, etc.)
- `semgrep` - Pattern-based static analysis
- `scc` - Code complexity calculator with SLOC
- `tokei` - Fast code statistics

Example usage:
```bash
# Python complexity
radon cc --show-complexity --average src/

# JavaScript complexity  
eslint --format json src/ | jq '.[] | .messages'

# Multi-language complexity
lizard --CCN 10 --length 50 src/
```

Use these tools where available to augment manual analysis and provide accurate metrics.

### 1. Structural Complexity Analysis

For each file and function in the codebase:

#### Cyclomatic Complexity
- Count decision points (if, while, for, case, catch, &&, ||, ?:)
- Calculate: Number of decision points + 1
- Flag functions with complexity > 10 as high risk

#### Cognitive Complexity
- Measure mental effort to understand code:
  - Basic: +1 for each break in linear flow
  - Nesting: +1 for each level of nesting
  - Complexity: Additional penalties for nested conditions

#### Depth Metrics
- Maximum nesting depth of control structures
- Call stack depth for recursive functions
- Inheritance depth for classes

#### Size Metrics
- Lines of code per function (exclude comments/blanks)
- Number of methods per class
- Number of parameters per function
- Number of return statements per function

### 2. Coupling Analysis

#### Afferent Coupling (Ca)
For each module, count:
- How many other modules depend on this one
- Track import/include statements referencing this module
- Note circular dependencies

#### Efferent Coupling (Ce)
For each module, count:
- How many other modules this one depends on
- Track all external dependencies
- Identify unstable dependencies

#### Instability Index
Calculate: Ce / (Ca + Ce)
- 0 = maximally stable
- 1 = maximally unstable

### 3. Code Quality Indicators

#### Documentation Quality
- Comment-to-code ratio
- Presence of function/class documentation
- TODO/FIXME/HACK comment density

#### Code Smells
Detect and count:
- Long parameter lists (> 5 parameters)
- Multiple return points (> 3)
- Deep nesting (> 4 levels)
- God classes (> 20 methods)
- Long methods (> 50 lines)

#### Naming Quality
- Average identifier length
- Consistency in naming conventions
- Meaningful vs cryptic names

### 4. Aggregate Metrics

For each file/component:
- Calculate weighted complexity score (0-10 scale)
- Identify complexity hotspots within files
- Track complexity trends if historical data available

### 5. Special Considerations

#### Language-Specific Analysis
Adapt metrics for:
- Object-oriented languages (inheritance complexity)
- Functional languages (composition complexity)
- Dynamic languages (runtime complexity)

#### Framework Complexity
Account for:
- Framework-imposed complexity
- Generated code
- Configuration complexity

## Output Format

```json
{
  "analysis_timestamp": "ISO-8601 timestamp",
  "files_analyzed": 0,
  "complexity_metrics": [
    {
      "file_path": "src/example/file.ext",
      "metrics": {
        "cyclomatic_complexity": {
          "average": 0.0,
          "max": 0,
          "high_risk_functions": ["function_name"]
        },
        "cognitive_complexity": {
          "average": 0.0,
          "max": 0
        },
        "nesting_depth": {
          "average": 0.0,
          "max": 0
        },
        "size_metrics": {
          "total_lines": 0,
          "average_function_length": 0.0,
          "max_function_length": 0,
          "class_count": 0,
          "method_count": 0
        },
        "coupling": {
          "afferent": 0,
          "efferent": 0,
          "instability": 0.0,
          "circular_dependencies": []
        },
        "quality_indicators": {
          "comment_ratio": 0.0,
          "long_parameter_lists": 0,
          "multiple_returns": 0,
          "code_smells": []
        },
        "complexity_score": 0.0
      },
      "functions": [
        {
          "name": "function_name",
          "line_start": 0,
          "cyclomatic_complexity": 0,
          "cognitive_complexity": 0,
          "parameters": 0,
          "lines": 0
        }
      ]
    }
  ],
  "summary": {
    "high_complexity_files": 0,
    "average_complexity": 0.0,
    "coupling_issues": 0,
    "code_smell_count": 0
  }
}
```

## Success Criteria

- All source files analyzed for complexity metrics
- Accurate calculation of standard complexity measures
- Identification of all high-risk functions and classes
- Complete coupling analysis with dependency graphs
- Code quality indicators mapped to specific locations
- Output suitable for risk score calculation

$ARGUMENTS