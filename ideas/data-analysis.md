# Data Analysis

## Purpose
Evaluate data storage, data models, data flow patterns, and data governance to identify issues with data quality, access, management, and architectural alignment. Focus on understanding how data design impacts system performance, maintainability, and business capabilities.

## Context
Data is often the most valuable and longest-lived asset in a system. Poor data architecture creates technical debt that compounds over time and limits business agility. This analysis examines both technical data implementation and organizational data practices.

## Instructions

### 1. Data Landscape Assessment

#### A. Data Storage System Inventory
Create a comprehensive catalog of all data storage systems:

**Primary Storage Systems**:
- Relational databases (PostgreSQL, MySQL, SQL Server)
- NoSQL databases (MongoDB, Cassandra, DynamoDB)
- In-memory stores (Redis, Memcached)
- File systems (Local, NFS, Object storage)
- Data warehouses (Snowflake, BigQuery, Redshift)
- Search engines (Elasticsearch, Solr)

**For Each Storage System**:
- **Purpose and Usage**: What data is stored and why
- **Technology Choice Rationale**: Why this technology was selected
- **Data Volume and Growth**: Current size and growth patterns
- **Access Patterns**: Read/write frequency and patterns
- **Performance Characteristics**: Latency, throughput, bottlenecks
- **Backup and Recovery**: Strategy and testing frequency

#### B. Data Classification and Sensitivity
Categorize data by business importance and sensitivity:

| Data Category | Examples | Sensitivity | Retention | Access Controls |
|---------------|----------|-------------|-----------|----------------|
| Personal Data | User profiles, preferences | High | 7 years | Role-based, audit logged |
| Financial Data | Transactions, payments | Critical | 10 years | Strict RBAC, encryption |
| Operational Data | Logs, metrics | Medium | 1 year | Team-based access |
| Public Data | Product catalog | Low | Indefinite | Public read access |

### 2. Data Model Evaluation

#### A. Relational Database Schema Analysis

**Schema Design Assessment**:
- **Normalization Level**: Appropriate for use case?
- **Referential Integrity**: Foreign key constraints implemented?
- **Data Types**: Appropriate choices, avoiding anti-patterns
- **Indexing Strategy**: Performance vs. storage trade-offs
- **Constraint Implementation**: Business rules enforced at DB level

**Schema Evolution Analysis**:
- **Migration History**: How schema changes are managed
- **Version Control**: Schema versioning and documentation
- **Backward Compatibility**: How breaking changes are handled
- **Rollback Capability**: Can schema changes be undone?

**Common Anti-Patterns to Check**:
- **God Tables**: Tables with too many columns
- **Missing Indexes**: Poor query performance
- **Over-Indexing**: Unnecessary storage and update overhead
- **EAV (Entity-Attribute-Value)**: Flexibility at the cost of integrity
- **Polymorphic Associations**: Complex relationship modeling

#### B. NoSQL Data Model Assessment

**Document Store Analysis**:
- **Schema Flexibility**: How is schema evolution handled?
- **Document Structure**: Consistent vs. varied document shapes
- **Embedding vs. Referencing**: Data relationship strategies
- **Query Patterns**: How data is accessed and aggregated

**Key-Value Store Analysis**:
- **Key Design**: Naming conventions and collision avoidance
- **Value Structure**: Simple values vs. complex objects
- **Expiration Policies**: Data lifecycle management
- **Partitioning Strategy**: Distribution and scalability

### 3. Data Flow and Integration Analysis

#### A. Data Movement Mapping

**Data Sources and Destinations**:
```
External APIs → Ingestion Service → Raw Data Store → Processing Pipeline → Clean Data Store → Application Database → Reporting System
```

**Integration Patterns Assessment**:
- **ETL vs. ELT**: Extract-Transform-Load patterns
- **Real-time vs. Batch**: Data freshness requirements
- **Event-Driven Updates**: Change data capture mechanisms
- **API Integration**: REST, GraphQL, messaging patterns
- **File-Based Integration**: CSV, JSON, XML processing

#### B. Data Synchronization Analysis

**Multi-System Data Consistency**:
- **Master Data Management**: Single source of truth identification
- **Data Duplication**: Where and why data is duplicated
- **Synchronization Mechanisms**: How data stays consistent
- **Conflict Resolution**: Handling concurrent updates
- **Eventual Consistency**: Where and how implemented

**Data Latency Assessment**:
- **Real-time Requirements**: Which data needs immediate consistency
- **Acceptable Lag**: Business tolerance for data staleness
- **Monitoring**: How data freshness is tracked
- **SLA Compliance**: Meeting data availability commitments

### 4. Data Quality Assessment

#### A. Data Integrity Analysis

**Data Quality Dimensions**:
- **Completeness**: Missing or null values analysis
- **Accuracy**: Data correctness verification
- **Consistency**: Cross-system data alignment
- **Validity**: Format and constraint compliance
- **Uniqueness**: Duplicate data identification
- **Timeliness**: Data currency and freshness

**Data Quality Metrics**:
- **Error Rates**: Percentage of invalid/incorrect data
- **Completeness Scores**: Percentage of required fields populated
- **Duplication Rates**: Percentage of duplicate records
- **Freshness Metrics**: Age of data vs. requirements

#### B. Data Validation and Cleansing

**Input Validation Strategy**:
- **Schema Validation**: Enforcing data structure requirements
- **Business Rule Validation**: Domain-specific constraints
- **Format Validation**: Pattern matching and type checking
- **Cross-Field Validation**: Relationship constraint checking

**Data Cleansing Processes**:
- **Automated Cleansing**: Rules-based data correction
- **Manual Review Processes**: Human validation workflows
- **Exception Handling**: How invalid data is managed
- **Data Recovery**: Restoring corrupted or lost data

### 5. Data Access and Performance Analysis

#### A. Query Performance Assessment

**Database Performance Analysis**:
- **Slow Query Identification**: Queries exceeding performance thresholds
- **Index Usage**: Which indexes are used/unused
- **Query Plan Analysis**: Execution strategy optimization
- **Connection Pooling**: Resource management efficiency
- **Lock Contention**: Concurrent access conflicts

**Access Pattern Analysis**:
```
Query Patterns:
├── Read-Heavy: 80% SELECT operations
├── Write-Heavy: 15% INSERT/UPDATE operations
└── Analytical: 5% complex aggregations

Access Distribution:
├── User Data: 60% of queries
├── Product Catalog: 25% of queries
└── Reporting: 15% of queries
```

#### B. Caching Strategy Evaluation

**Caching Layer Assessment**:
- **Cache Hierarchy**: L1 (application), L2 (distributed), L3 (database)
- **Cache Coherence**: How cache invalidation is managed
- **Hit Rates**: Cache effectiveness measurement
- **Eviction Policies**: LRU, LFU, TTL strategies
- **Cache Warming**: Preloading strategies

### 6. Data Governance and Compliance

#### A. Data Governance Framework

**Data Ownership and Stewardship**:
- **Data Owners**: Who is responsible for each data domain
- **Data Stewards**: Who manages day-to-day data quality
- **Governance Policies**: Rules and procedures for data management
- **Change Management**: How data structure changes are approved

**Data Lineage and Documentation**:
- **Source Documentation**: Where data originates
- **Transformation Documentation**: How data is processed
- **Usage Documentation**: How data is consumed
- **Impact Analysis**: Understanding downstream effects of changes

#### B. Compliance and Privacy Assessment

**Regulatory Compliance**:
- **GDPR Compliance**: Right to erasure, data portability
- **Data Retention Policies**: Legal and business requirements
- **Audit Trails**: Change tracking and accountability
- **Cross-Border Data Transfer**: Legal and technical constraints

**Privacy Protection**:
- **Data Anonymization**: PII removal and masking
- **Encryption at Rest**: Sensitive data protection
- **Access Logging**: Who accessed what data when
- **Consent Management**: User permission tracking

### 7. Data Architecture and Scalability

#### A. Data Architecture Patterns

**Current Architecture Assessment**:
- **Data Lake vs. Data Warehouse**: Structured vs. unstructured approaches
- **Microservice Data Patterns**: Database per service, shared databases
- **CQRS Implementation**: Command-query responsibility segregation
- **Event Sourcing**: Event-driven data modeling

#### B. Scalability and Performance Planning

**Scaling Strategies**:
- **Vertical Scaling**: Hardware upgrade limitations
- **Horizontal Scaling**: Sharding and partitioning strategies
- **Read Replicas**: Load distribution mechanisms
- **Data Archiving**: Historical data management

## Output Format

### 1. Data Landscape Overview

#### Data System Inventory
| System | Technology | Purpose | Data Volume | Growth Rate | Performance Status |
|--------|------------|---------|-------------|-------------|-------------------|
| Primary DB | PostgreSQL | Transactional data | 500GB | 10GB/month | Good |
| Cache | Redis | Session data | 50GB | 5GB/month | Excellent |
| Analytics | BigQuery | Reporting | 2TB | 100GB/month | Needs optimization |

#### Data Classification Summary
- **Critical Data**: 15% (payment, personal data)
- **Sensitive Data**: 30% (user behavior, business metrics)
- **Internal Data**: 40% (logs, configurations)
- **Public Data**: 15% (product information)

### 2. Data Model Assessment

#### Schema Quality Analysis
**Strengths**:
- Well-normalized core entities
- Appropriate indexing for common queries
- Good referential integrity enforcement

**Issues Identified**:
- **God Table**: User table with 47 columns
- **Missing Indexes**: Product search queries slow
- **Over-Normalized**: Excessive joins for simple operations

#### Data Model Evolution
- **Schema Changes**: 23 migrations in last 6 months
- **Breaking Changes**: 2 backward-incompatible changes
- **Documentation**: 60% of tables documented

### 3. Data Quality Report

#### Data Quality Metrics
| Quality Dimension | Score | Issues Found | Impact |
|------------------|-------|--------------|--------|
| Completeness | 85% | Missing user emails | Registration workflow failures |
| Accuracy | 92% | Outdated product prices | Customer complaints |
| Consistency | 78% | Address format variations | Shipping delays |
| Timeliness | 90% | Stale inventory data | Overselling incidents |

#### Critical Data Quality Issues
1. **[Issue]**: 15% of user records missing email addresses
   - Impact: Cannot send notifications
   - Root Cause: Optional field in registration form
   - Recommendation: Make email mandatory, backfill existing records

### 4. Data Flow and Integration Analysis

#### Data Integration Map
```
External APIs (3) → Message Queue → Data Pipeline → Data Lake → Analytics DB
                                        ↓
                  Application DB ← ETL Process ← Data Warehouse
```

#### Integration Quality Assessment
- **Real-time Integrations**: 85% success rate
- **Batch Processes**: 95% success rate
- **Data Latency**: Average 15 minutes for critical data
- **Error Handling**: Manual intervention required for 5% of failures

### 5. Performance and Access Analysis

#### Database Performance Summary
- **Slow Queries**: 12 queries exceeding 2-second threshold
- **Index Usage**: 78% of indexes actively used
- **Connection Pool**: 60% average utilization
- **Lock Contention**: 3 incidents per week

#### Top Performance Issues
1. **Product Search**: Full table scan on 2M records
   - Solution: Add composite index on (category, status, created_date)
   - Expected Improvement: 10x faster queries

### 6. Data Governance Assessment

#### Governance Maturity
| Area | Maturity Level | Status |
|------|---------------|--------|
| Data Ownership | Basic | Some data domains have owners |
| Documentation | Ad-hoc | 40% of data sources documented |
| Quality Monitoring | Basic | Manual quality checks |
| Compliance | Developing | GDPR partially implemented |

#### Compliance Gaps
- **Data Retention**: No automated deletion of expired data
- **Access Controls**: Overly broad database permissions
- **Audit Logging**: Insufficient detail for compliance requirements

### 7. Strategic Recommendations

#### Immediate Actions (< 1 month)
- Fix critical slow queries with proper indexing
- Implement automated data quality monitoring
- Establish data retention policies and automation

#### Short-term Improvements (1-3 months)
- Redesign problematic data models (god tables)
- Implement comprehensive data lineage tracking
- Enhance data validation and cleansing processes

#### Long-term Strategy (3-12 months)
- Implement data governance framework
- Design scalable data architecture for growth
- Establish data quality culture and practices

### 8. Data Monitoring Strategy

#### Key Data Metrics
- Data quality scores by domain
- Query performance trends
- Storage growth patterns
- Integration success rates
- Compliance audit results

#### Alerting and Monitoring
- Real-time data quality alerts
- Performance threshold monitoring
- Integration failure notifications
- Compliance violation detection

## Success Criteria
- Comprehensive understanding of data landscape and architecture
- Identified data quality issues with business impact assessment
- Clear performance bottlenecks and optimization opportunities
- Data governance gaps and compliance risks documented
- Actionable roadmap for data architecture improvements
- Monitoring strategy for ongoing data health assessment

$ARGUMENTS