# Context Analysis Prompt

## Purpose
Map the system's ecosystem by analyzing all external touchpoints, dependencies, and interfaces. Identify integration risks and understand how the system fits into the broader technical and business landscape.

## Context
Context analysis reveals how external factors impact system quality. Many performance, reliability, and security issues stem from problematic interfaces or misunderstood dependencies. This analysis helps avoid the "microscope trap" by ensuring we understand the full system context.

## Instructions

### 1. System Boundary Definition
First, clearly establish what is "inside" vs "outside" the system:
- Core components owned and maintained by the team
- Shared components with partial ownership
- External systems and services
- Third-party dependencies and libraries

### 2. Interface Inventory and Classification

#### A. Identify All External Interfaces
Create a comprehensive catalog:

**Inbound Interfaces** (others → system):
- User interfaces (Web UI, Mobile apps, CLI)
- API endpoints (REST, GraphQL, SOAP, RPC)
- Message queues/topics (consumed)
- File imports (batch, uploads)
- Database connections (shared databases)
- Webhooks and callbacks

**Outbound Interfaces** (system → others):
- External API calls
- Message publishing
- File exports
- Database writes to external schemas
- Notifications (email, SMS, push)
- Reporting feeds

**Bidirectional Interfaces**:
- Synchronous request-response APIs
- Shared databases
- File system mounts
- WebSocket connections

#### B. For Each Interface, Document:

**Technical Specification**:
- Protocol and format (HTTP/REST, AMQP, FTP, etc.)
- Data format (JSON, XML, CSV, Binary)
- Schema/contract definition (OpenAPI, XSD, Protobuf)
- Version information
- Typical payload sizes
- Expected transaction volumes

**Quality Characteristics**:
- Availability requirements/SLAs
- Performance expectations (latency, throughput)
- Error rates and handling
- Security requirements (auth, encryption)
- Monitoring and observability

**Operational Aspects**:
- Who owns/maintains the external system?
- How are changes communicated?
- What's the update/deployment frequency?
- Support availability and escalation paths
- Historical stability

### 3. Dependency Analysis

#### A. Runtime Dependencies
Map critical dependencies and their impact:

| Dependency | Type | Criticality | Fallback Strategy | Failure Impact |
|------------|------|-------------|-------------------|----------------|
| Payment Gateway | API | Critical | Queue + Retry | No revenue |
| User Service | API | High | Cache | Degraded UX |
| Analytics | API | Low | Fire-and-forget | No impact |

#### B. Build/Deploy Dependencies
- Package repositories (npm, Maven, etc.)
- Container registries
- CI/CD services
- Infrastructure providers
- Certificate authorities

#### C. Data Dependencies
- Master data sources
- Reference data providers
- Real-time data feeds
- Batch data imports/exports

### 4. Risk Assessment

#### A. Interface Risk Scoring
For each interface, assess:
1. **Change Risk**: How often does the interface change?
2. **Stability Risk**: How reliable is the external system?
3. **Control Risk**: Do we control the interface specification?
4. **Business Risk**: What's the impact of interface failure?
5. **Technical Risk**: How complex is the integration?

Score each 1-5 and calculate: `Risk Score = (Change + Stability + Control + Business + Technical) / 5`

#### B. High-Risk Interface Patterns
Flag interfaces with:
- No formal specification or documentation
- Manual/human-operated processes
- Multiple incompatible versions in use
- No error handling or monitoring
- Single points of failure
- Synchronous chains of dependencies
- Circular dependencies

### 5. Integration Quality Assessment

#### A. Contract Testing
- Are interface contracts formally defined?
- Do contract tests exist?
- How are breaking changes detected?
- Is versioning strategy clear?

#### B. Error Handling
- Timeout configurations
- Retry strategies with backoff
- Circuit breaker implementations
- Fallback mechanisms
- Error propagation and reporting

#### C. Monitoring and Observability
- Interface-specific metrics and dashboards
- SLA tracking
- Error rate monitoring
- Distributed tracing implementation
- Alert configurations

### 6. Special Considerations

#### A. External Party Interfaces
For third-party integrations:
- Commercial relationship status
- SLA agreements
- Support channels
- Change notification processes
- Vendor lock-in assessment

#### B. Legacy System Interfaces
- Technical debt assessment
- Migration/modernization plans
- Workaround documentation
- Knowledge transfer risks

#### C. Regulatory/Compliance Interfaces
- Data protection requirements
- Audit trail needs
- Compliance certifications
- Data residency constraints

## Output Format

### 1. Context Diagram
Visual system context showing:
- System boundary
- All external actors/systems
- Interface types and directions
- Risk levels (color-coded)

### 2. Interface Risk Matrix

| Interface | Type | Owner | Risk Score | Critical Issues | Recommendations |
|-----------|------|-------|------------|-----------------|-----------------|
| Payment API | REST/Sync | FinanceOrg | 4.2 | No circuit breaker, version drift | Implement resilience patterns |

### 3. Dependency Impact Analysis

#### Critical Path Dependencies
Systems/services that can bring down core functionality:
1. **[Service Name]**: Impact description, current mitigations

#### Data Flow Dependencies
How data moves through external systems:
1. **[Flow Name]**: Source → Transformations → Destination, risks identified

### 4. Key Findings

#### High-Risk Interfaces (Risk Score > 4.0)
1. **[Interface]**: Specific risks and business impact

#### Missing Resilience Patterns
1. **[Pattern]**: Where needed and why

#### Integration Anti-Patterns Found
1. **[Anti-pattern]**: Locations and recommended fixes

### 5. Prioritized Recommendations

#### Immediate Actions (< 1 week)
- Add timeout configurations to [services]
- Implement basic retry logic for [interfaces]
- Set up monitoring for [critical interfaces]

#### Short-term Improvements (1-4 weeks)
- Implement circuit breakers for [services]
- Add contract tests for [APIs]
- Document [undocumented interfaces]

#### Strategic Changes (1-3 months)
- Redesign [problematic integration]
- Migrate from [legacy interface] to [modern alternative]
- Implement proper event-driven architecture for [use case]

### 6. Interface Governance Recommendations
- Proposed interface standards
- Change management process
- Monitoring and alerting strategy
- Documentation requirements

## Success Criteria
- Complete inventory of all external interfaces
- Risk assessment for each interface with business impact
- Identified all single points of failure
- Found interfaces lacking resilience patterns
- Clear remediation roadmap with priorities
- Improved understanding of system's external dependencies

$ARGUMENTS