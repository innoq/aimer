# Code Walkthrough Prompt

## Purpose
Trace execution paths through code to evaluate business logic implementation, cross-cutting concerns, and architectural consistency. Focus on understanding how business requirements are implemented and where the implementation deviates from intended design.

## Context
Code walkthroughs reveal how theory meets practice by following actual execution paths. This analysis helps identify gaps between intended architecture and implementation, uncovers hidden complexity, and validates that business logic is correctly implemented across system boundaries.

## Instructions

### 1. Use Case Selection and Preparation

#### A. Strategic Use Case Selection
Choose use cases that provide maximum insight:

**High-Value Scenarios**:
- Core business workflows (e.g., payment processing, user registration)
- Complex business logic (e.g., pricing calculations, approval workflows)
- Cross-system integrations (e.g., data synchronization, external API calls)
- Error-prone areas (based on bug reports or stakeholder feedback)
- Recently changed functionality

**Selection Criteria**:
- Business criticality (high impact on users/revenue)
- Technical complexity (multiple components involved)
- Risk level (areas with frequent issues)
- Representative patterns (common architectural approaches)

#### B. Walkthrough Scope Definition
For each selected use case:
- **Entry Points**: API endpoints, UI interactions, scheduled jobs
- **Expected Flow**: Business process steps
- **Success Criteria**: What defines successful completion
- **Error Scenarios**: Known failure modes
- **Performance Expectations**: Response time, throughput requirements

### 2. Execution Path Tracing

#### A. Static Analysis Approach
Map the code execution flow without running the system:

**Flow Documentation**:
```
1. Entry Point: POST /api/orders
   ├── Controller: OrderController.createOrder()
   ├── Validation: OrderValidator.validate()
   ├── Business Logic: OrderService.processOrder()
   │   ├── Inventory: InventoryService.checkAvailability()
   │   ├── Pricing: PricingEngine.calculateTotal()
   │   └── Payment: PaymentGateway.processPayment()
   ├── Persistence: OrderRepository.save()
   └── Response: OrderDTO.toJson()
```

**Call Hierarchy Analysis**:
- Method-to-method call chains
- Cross-component interactions
- External service invocations
- Database operations
- Event/message publishing

#### B. Data Flow Tracing
Track how data transforms through the system:

**Data Transformation Chain**:
```
Input Data → Validation → Business Rules → Persistence → Output
   ↓            ↓             ↓              ↓           ↓
HTTP JSON → Order DTO → Order Entity → Database → Response JSON
```

**Key Questions**:
- How is input data validated and sanitized?
- Where are business rules applied?
- How is data mapped between layers?
- What transformations occur at boundaries?
- Where might data be lost or corrupted?

### 3. Implementation Quality Assessment

#### A. Business Logic Correctness
Evaluate how well code implements business requirements:

**Business Rule Implementation**:
- Are all business rules correctly implemented?
- Is business logic scattered across layers?
- Are calculations accurate and complete?
- How are business exceptions handled?
- Are edge cases properly addressed?

**Domain Model Alignment**:
- Does code structure reflect business concepts?
- Are domain entities properly encapsulated?
- Is business terminology used consistently?
- Are invariants and constraints enforced?

#### B. Error Handling and Edge Cases

**Error Handling Patterns**:
- **Input Validation**: How are invalid inputs handled?
- **Business Exceptions**: How are business rule violations communicated?
- **Technical Errors**: How are system failures managed?
- **Recovery Mechanisms**: Can the system recover from failures?
- **User Communication**: Are errors properly communicated to users?

**Edge Case Coverage**:
- Boundary conditions (min/max values, empty collections)
- Concurrent access scenarios
- Network failures and timeouts
- Resource exhaustion conditions
- Data inconsistency situations

### 4. Cross-Cutting Concerns Analysis

#### A. Systematic Cross-Cutting Assessment

**Security Implementation**:
- **Authentication**: How is user identity verified?
- **Authorization**: How are permissions checked?
- **Input Sanitization**: How is malicious input prevented?
- **Data Protection**: How is sensitive data handled?
- **Audit Logging**: What security events are logged?

**Performance Considerations**:
- **Database Access**: Query efficiency and N+1 problems
- **Caching Strategy**: What is cached and when?
- **Resource Usage**: Memory and CPU utilization
- **Blocking Operations**: Synchronous vs asynchronous processing
- **Scalability Bottlenecks**: Single points of resource contention

**Observability and Monitoring**:
- **Logging Coverage**: What events are logged?
- **Metrics Collection**: What is measured?
- **Tracing**: Can requests be traced end-to-end?
- **Error Reporting**: How are failures captured?
- **Business Metrics**: Are business KPIs tracked?

#### B. Consistency Assessment
Evaluate cross-cutting concern implementation consistency:
- Are patterns applied uniformly across components?
- Are there gaps in coverage?
- Do different teams use different approaches?
- Are there conflicting implementations?

### 5. Architectural Adherence Evaluation

#### A. Architecture Pattern Compliance

**Layered Architecture Assessment**:
- Does code respect layer boundaries?
- Are there inappropriate layer bypasses?
- Is separation of concerns maintained?
- Are dependencies pointing in the right direction?

**Design Pattern Usage**:
- Are appropriate design patterns used?
- Are patterns implemented correctly?
- Is pattern usage consistent across similar scenarios?
- Are anti-patterns present?

#### B. Technology and Framework Usage

**Framework Adherence**:
- Are framework conventions followed?
- Is the framework used idiomatically?
- Are framework features leveraged appropriately?
- Are there framework-specific anti-patterns?

**Library and Dependency Usage**:
- Are external libraries used correctly?
- Is functionality duplicated that libraries provide?
- Are dependencies up-to-date and secure?
- Is vendor lock-in managed appropriately?

### 6. Performance and Scalability Analysis

#### A. Performance Bottleneck Identification

**Database Operations**:
- Query efficiency and indexing strategy
- Transaction boundary optimization
- Connection pool usage
- Data loading patterns (lazy vs eager)

**External Service Calls**:
- Timeout and retry configurations
- Circuit breaker implementations
- Async vs sync communication choices
- Error handling for external failures

#### B. Scalability Assessment
- **State Management**: How is state handled across instances?
- **Resource Sharing**: Are shared resources properly managed?
- **Concurrency Handling**: How are race conditions prevented?
- **Load Distribution**: Can processing be distributed?

## Output Format

### 1. Use Case Execution Summary

#### Selected Use Cases
| Use Case | Business Criticality | Technical Complexity | Risk Level | Analysis Priority |
|----------|---------------------|---------------------|------------|-------------------|
| Order Processing | High | Medium | High | P1 |
| User Registration | Medium | Low | Low | P3 |

### 2. Detailed Walkthrough Analysis

For each analyzed use case:

#### Use Case: [Name]
**Business Context**:
- Purpose and business value
- Key stakeholders and users
- Success criteria and KPIs

**Execution Flow Analysis**:
```
Entry Point: [Description]
├── Step 1: [Component.method()] - [Purpose]
│   ├── Validation: [Details]
│   ├── Business Logic: [Key decisions]
│   └── Side Effects: [Database writes, events, etc.]
├── Step 2: [Component.method()] - [Purpose]
└── Exit Point: [Response/Result]
```

**Data Flow Assessment**:
- Input data structure and validation
- Key transformations and mappings
- Output format and content
- Data integrity checkpoints

### 3. Implementation Quality Report

#### Business Logic Implementation
**Strengths**:
- Correctly implemented business rules
- Clear domain model representation
- Appropriate abstraction levels

**Concerns**:
- Business logic scattered across layers
- Missing validation for edge cases
- Inconsistent error handling

#### Cross-Cutting Concerns Assessment

| Concern | Implementation Quality | Coverage | Consistency | Issues Found |
|---------|----------------------|----------|-------------|--------------|
| Security | Good | 90% | High | Missing auth check in admin flow |
| Logging | Poor | 40% | Low | Inconsistent log levels, missing correlation IDs |
| Performance | Medium | 70% | Medium | No caching in calculation service |

### 4. Architectural Conformity Analysis

#### Pattern Adherence Assessment
- **MVC Pattern**: Controllers have business logic (violation)
- **Repository Pattern**: Correctly implemented
- **Service Layer**: Inconsistent transaction boundaries

#### Technology Usage Review
- **Framework Usage**: Spring Boot used idiomatically
- **Library Usage**: Outdated Jackson version, manual JSON parsing where unnecessary
- **Custom Code**: Reimplemented functionality available in standard libraries

### 5. Performance and Scalability Findings

#### Performance Issues Identified
1. **[Issue]**: N+1 query problem in order item loading
   - Location: OrderService.getOrderDetails()
   - Impact: Linear performance degradation with order size
   - Recommendation: Implement batch loading

#### Scalability Concerns
1. **[Concern]**: Synchronous payment processing blocks threads
   - Impact: Limited concurrent order processing
   - Recommendation: Implement async payment handling

### 6. Error Handling and Edge Case Analysis

#### Error Handling Effectiveness
**Strengths**:
- Consistent exception hierarchy
- Proper error propagation to UI
- Comprehensive input validation

**Gaps**:
- Missing retry logic for transient failures
- Inadequate error logging context
- No graceful degradation for external service failures

#### Edge Case Coverage
- **Boundary Conditions**: Well handled
- **Concurrency**: Race condition in inventory check
- **Failure Scenarios**: Missing rollback for partial failures

### 7. Improvement Recommendations

#### Immediate Fixes (< 1 week)
- Add missing authentication check in admin workflow
- Fix N+1 query in order processing
- Implement missing error handling for payment timeouts

#### Short-term Improvements (1-4 weeks)
- Refactor business logic out of controllers
- Implement consistent logging strategy
- Add circuit breakers for external service calls

#### Strategic Changes (1-3 months)
- Redesign for async processing where appropriate
- Implement comprehensive monitoring and metrics
- Establish architectural fitness functions

## Success Criteria
- Complete understanding of business logic implementation
- Identified gaps between intended and actual architecture
- Assessment of cross-cutting concern implementation quality
- Clear picture of error handling and edge case coverage
- Performance and scalability bottleneck identification
- Actionable recommendations for code and architecture improvements

$ARGUMENTS