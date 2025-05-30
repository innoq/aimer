# Hotspot Analysis - Business Logic Analyzer

## Purpose
Identify and analyze business-critical components with high domain complexity. Focus on code that implements core business rules, workflows, and decision logic that represents inherent complexity beyond technical metrics.

## Context
Business logic complexity differs from structural complexity - it represents the inherent difficulty of the problem domain. This agent identifies components that handle critical business processes, complex calculations, state management, and integration orchestration. Such components often become hotspots due to frequent business rule changes.

## Instructions

### Tool Support

Leverage CLI-based analysis tools to identify business logic patterns:

**Pattern Detection CLI Tools:**
- `semgrep` - Custom pattern matching for business logic
- `grep`/`ripgrep` - Fast pattern search across codebases
- `ast-grep` - Structural pattern matching using AST
- `comby` - Structural code search and manipulation

**Dependency Analysis CLI Tools:**
- `jdeps` (Java) - Analyze package dependencies
- `dependency-cruiser` (JS/TS) - Validate and visualize dependencies
- `pipdeptree` (Python) - Package dependency tree
- `go mod graph` (Go) - Module dependency graph

**Code Analysis CLI Tools:**
- `ctags`/`universal-ctags` - Generate tags for code navigation
- `cscope` - Code browsing tool
- `doxygen` - Extract code structure and documentation
- `cloc` - Count lines of code by language

Example usage:
```bash
# Find payment-related business logic
semgrep --pattern 'payment|invoice|billing' --lang java

# Extract class hierarchies
ctags -R --fields=+i --extras=+q src/

# Analyze dependencies
dependency-cruiser --validate .dependency-cruiser.js src
```

These tools can help identify business-critical components and complex decision patterns.

### 1. Business Component Identification

#### Domain Keyword Analysis
Search for business domain indicators:
- Payment processing patterns
- User authentication/authorization
- Order/transaction management  
- Inventory/resource calculations
- Pricing/discount rules
- Compliance/regulatory logic
- Reporting/analytics engines

#### Critical Path Detection
Identify components in critical business flows:
- Revenue-generating processes
- Customer-facing features
- Data integrity guardians
- Integration orchestrators
- Security enforcement points

### 2. Decision Complexity Analysis

#### Business Rule Detection
Identify complex decision logic:
- Multi-condition business rules (> 5 conditions)
- Nested decision trees
- Rule engines and evaluators
- Policy enforcement code
- Validation frameworks

#### State Machine Analysis
Detect state management complexity:
- Number of states
- Transition complexity
- State persistence logic
- Concurrent state handling
- State validation rules

### 3. Calculation Complexity

#### Algorithm Identification
Find computationally complex business logic:
- Financial calculations (interest, tax, fees)
- Scheduling algorithms
- Optimization routines
- Statistical computations
- Resource allocation logic

#### Data Transformation
Analyze ETL and data processing:
- Complex data mappings
- Multi-source aggregations
- Business metric calculations
- Report generation logic

### 4. Integration Complexity

#### External System Integration
Identify integration points:
- API orchestration logic
- Data synchronization code
- Error handling and retry logic
- Message transformation
- Protocol adapters

#### Cross-Domain Coordination
Find components that coordinate across domains:
- Workflow orchestrators
- Saga pattern implementations
- Distributed transaction management
- Event coordination logic

### 5. Business Configuration

#### Configurability Analysis
Assess configuration complexity:
- Number of configuration parameters
- Business rule configurability
- Feature flags and toggles
- Multi-tenant variations
- Environment-specific logic

#### Customization Points
Identify extensibility complexity:
- Plugin/extension interfaces
- Custom business logic hooks
- Override mechanisms
- Template/strategy patterns

### 6. Domain Model Complexity

#### Entity Relationship Complexity
Analyze domain model:
- Number of related entities
- Relationship cardinality
- Aggregate boundaries
- Invariant enforcement

#### Business Constraint Enforcement
Find complex validation:
- Cross-entity validations
- Temporal constraints
- Business invariants
- Consistency rules

## Output Format

```json
{
  "analysis_timestamp": "ISO-8601 timestamp",
  "business_components": [
    {
      "file_path": "src/example/file.ext",
      "component_type": "payment_processor|rule_engine|workflow|calculator|integrator",
      "business_metrics": {
        "criticality_score": 0.0,
        "domain_complexity": {
          "decision_points": 0,
          "business_rules": 0,
          "state_complexity": 0,
          "calculation_complexity": 0
        },
        "integration_complexity": {
          "external_systems": 0,
          "coordination_points": 0,
          "data_transformations": 0
        },
        "configuration_complexity": {
          "config_parameters": 0,
          "feature_flags": 0,
          "customization_points": 0
        }
      },
      "business_features": [
        {
          "name": "feature_name",
          "type": "rule|calculation|workflow|integration",
          "complexity": "low|medium|high",
          "change_frequency_indicator": "stable|volatile"
        }
      ],
      "domain_entities": ["Order", "Payment", "User"],
      "external_dependencies": ["PaymentGateway", "TaxService"],
      "business_risk_factors": [
        "Revenue impact",
        "Compliance requirement",
        "Customer facing"
      ]
    }
  ],
  "critical_paths": [
    {
      "path_name": "checkout_flow",
      "components": ["file1.ext", "file2.ext"],
      "business_impact": "high",
      "complexity_score": 0.0
    }
  ],
  "summary": {
    "total_business_components": 0,
    "high_criticality_components": 0,
    "complex_workflows": 0,
    "integration_points": 0,
    "configuration_hotspots": 0
  }
}
```

## Success Criteria

- All business-critical components identified
- Domain complexity accurately assessed
- Business rules and workflows mapped
- Integration points documented
- Configuration complexity measured
- Critical paths identified with impact assessment
- Output provides business context for risk scoring

$ARGUMENTS