# Security Analysis Prompt

## Purpose
Systematically identify security vulnerabilities, risks, and compliance gaps within the system. Focus on both technical security measures and organizational security practices that could impact system security posture.

## Context
Security is a cross-cutting quality attribute that must be evaluated at multiple levels: code, architecture, infrastructure, and processes. This analysis helps identify not just obvious vulnerabilities but also systemic security weaknesses that could be exploited.

## Instructions

### 1. Security Landscape Assessment

#### A. Threat Modeling
Identify potential attackers and their capabilities:

**External Threats**:
- Script kiddies (automated tools, known exploits)
- Organized cybercriminals (financial motivation)
- Nation-state actors (sophisticated, persistent)
- Competitors (industrial espionage)

**Internal Threats**:
- Malicious insiders (employees, contractors)
- Negligent insiders (accidental exposure)
- Compromised accounts (credential theft)

**For each threat, assess**:
- Motivation and capabilities
- Likely attack vectors
- Potential impact if successful
- Current defensive measures

#### B. Asset Classification
Categorize system assets by sensitivity:

| Asset Type | Examples | Sensitivity Level | Protection Requirements |
|------------|----------|------------------|----------------------|
| Personal Data | User profiles, emails | High | Encryption, access controls, audit logs |
| Financial Data | Payment info, transactions | Critical | Strong encryption, tokenization, PCI DSS |
| Business Data | Analytics, strategies | Medium | Access controls, backup encryption |
| Public Data | Marketing content | Low | Integrity protection |

### 2. Technical Security Assessment

#### A. Authentication and Authorization Analysis

**Authentication Mechanisms**:
- Password policies and enforcement
- Multi-factor authentication implementation
- Session management security
- Account lockout and brute-force protection
- Password storage mechanisms (hashing, salting)

**Authorization Controls**:
- Role-based access control (RBAC) implementation
- Principle of least privilege adherence
- Permission boundaries and enforcement
- Privilege escalation prevention
- API authentication and authorization

**Security Questions to Answer**:
- Can users access data they shouldn't?
- Are admin privileges properly protected?
- How are service-to-service calls authenticated?
- What happens when credentials are compromised?

#### B. Data Protection Assessment

**Encryption Analysis**:
```
Data at Rest:
- Database encryption status
- File system encryption
- Backup encryption
- Key management practices

Data in Transit:
- TLS implementation and configuration
- Certificate management
- Internal communication encryption
- Third-party API security
```

**Data Handling Practices**:
- Data classification and labeling
- Data retention and deletion policies
- Data minimization principles
- Cross-border data transfer compliance
- Anonymization and pseudonymization

#### C. Input Validation and Output Encoding

**Common Vulnerability Patterns**:
- SQL injection vectors
- Cross-site scripting (XSS) opportunities
- Command injection possibilities
- Path traversal vulnerabilities
- Deserialization attacks
- XML/JSON parsing vulnerabilities

**Validation Strategy Assessment**:
- Input validation completeness
- Sanitization effectiveness
- Output encoding consistency
- File upload security
- API parameter validation

### 3. Infrastructure Security Analysis

#### A. Network Security Assessment

**Network Architecture**:
- Network segmentation effectiveness
- Firewall rules and configurations
- DMZ implementation
- VPN security
- Load balancer security configurations

**Access Controls**:
- SSH key management
- VPN access controls
- Jump box/bastion host security
- Network monitoring and intrusion detection

#### B. Cloud Security Configuration

**Cloud-Specific Concerns**:
- IAM policy configurations
- Security group configurations
- Storage bucket permissions
- Resource access logging
- Compliance with cloud security best practices

**Configuration Management**:
- Infrastructure as code security
- Secret management practices
- Environment isolation
- Patch management processes

### 4. Application Security Deep Dive

#### A. Code-Level Security Issues

**Static Analysis Focus Areas**:
- Hard-coded credentials or secrets
- Insecure cryptographic implementations
- Race conditions and concurrency issues
- Buffer overflows or memory issues
- Insecure random number generation

**Dynamic Analysis Opportunities**:
- Runtime security testing
- Penetration testing results
- Vulnerability scanning findings
- Security monitoring alerts

#### B. Third-Party Dependencies

**Dependency Security Assessment**:
- Known vulnerabilities in dependencies
- Dependency update practices
- License compliance
- Supply chain security
- Vendor security assessments

### 5. Compliance and Governance

#### A. Regulatory Compliance Assessment

**Relevant Standards**:
- GDPR (data protection)
- PCI DSS (payment processing)
- HIPAA (healthcare data)
- SOX (financial reporting)
- Industry-specific regulations

**Compliance Gap Analysis**:
- Current compliance status
- Missing controls or documentation
- Audit trail adequacy
- Data subject rights implementation
- Breach notification procedures

#### B. Security Governance

**Policy and Process Assessment**:
- Security policy completeness and currency
- Incident response procedures
- Security training and awareness
- Vendor security requirements
- Security review processes

### 6. Security Monitoring and Response

#### A. Observability Assessment

**Security Monitoring Coverage**:
- Authentication and authorization events
- Data access patterns
- System configuration changes
- Network traffic analysis
- Application error monitoring

**Incident Detection Capabilities**:
- SIEM/SOAR implementation
- Alerting rules and thresholds
- False positive rates
- Response time metrics
- Forensic data retention

#### B. Incident Response Readiness

**Response Capability Assessment**:
- Incident response plan completeness
- Team roles and responsibilities
- Communication procedures
- Containment and eradication processes
- Recovery and lessons learned processes

## Output Format

### 1. Executive Security Summary

**Risk Assessment Overview**:
- Overall security posture rating (1-5)
- Critical vulnerabilities requiring immediate attention
- Compliance status summary
- Business risk assessment

**Top Security Priorities**:
1. [Critical Issue]: Business impact and recommended timeline
2. [High Priority Issue]: Risk level and mitigation approach
3. [Medium Priority Issue]: Monitoring and improvement strategy

### 2. Detailed Vulnerability Assessment

#### Critical Vulnerabilities (Fix Immediately)
For each critical finding:

**Vulnerability: [Name]**
- **CVSS Score**: X.X (Critical/High/Medium/Low)
- **Description**: Technical details of the vulnerability
- **Location**: Specific systems/components affected
- **Attack Vector**: How this could be exploited
- **Business Impact**: Potential consequences
- **Proof of Concept**: Evidence or reproduction steps
- **Remediation**: Specific steps to fix
- **Timeline**: Recommended fix deadline

#### Security Weaknesses (Address Soon)
- Authentication/authorization gaps
- Data protection issues
- Infrastructure misconfigurations
- Process/policy gaps

### 3. Compliance Status Report

| Requirement | Current Status | Gap Analysis | Remediation Plan |
|-------------|----------------|--------------|------------------|
| GDPR Art. 32 | Partial | Missing data encryption | Implement field-level encryption |
| PCI DSS 3.2.1 | Non-compliant | No cardholder data tokenization | Implement tokenization service |

### 4. Security Architecture Assessment

#### Threat Model Results
- High-priority threats identified
- Attack surface analysis
- Trust boundaries evaluation
- Security control effectiveness

#### Defense in Depth Analysis
- Perimeter security effectiveness
- Internal segmentation quality
- Application-level protections
- Data-level protections

### 5. Risk Register

| Risk ID | Description | Likelihood | Impact | Risk Score | Mitigation Strategy | Owner |
|---------|-------------|------------|--------|------------|-------------------|-------|
| SEC-001 | SQL injection in payment module | High | Critical | 9.0 | Input validation, parameterized queries | Dev Team |

### 6. Security Improvement Roadmap

#### Immediate Actions (< 1 week)
- Patch critical vulnerabilities
- Disable unnecessary services
- Implement emergency monitoring

#### Short-term Improvements (1-4 weeks)
- Implement missing security controls
- Enhance monitoring and alerting
- Update security policies

#### Strategic Security Initiatives (1-6 months)
- Comprehensive security architecture review
- Security training program implementation
- Advanced threat detection capabilities

### 7. Security Metrics and Monitoring

#### Proposed Security KPIs
- Mean time to detect security incidents
- Mean time to respond to incidents
- Vulnerability remediation times
- Security training completion rates
- Compliance audit results

#### Continuous Security Monitoring
- Real-time security dashboard requirements
- Automated vulnerability scanning
- Security event correlation rules
- Regular penetration testing schedule

## Success Criteria
- Comprehensive inventory of security vulnerabilities and risks
- Clear prioritization based on business impact and exploitability
- Actionable remediation plans with timelines
- Compliance gap analysis with specific improvement steps
- Security monitoring and governance recommendations
- Team awareness of security responsibilities and procedures

$ARGUMENTS