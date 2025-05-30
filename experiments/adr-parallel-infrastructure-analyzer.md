# ADR Parallel Infrastructure Analyzer

## Purpose

Analyze configuration, deployment, and infrastructure decisions to identify architectural choices related to system operation and deployment.

## Context

This sub-agent examines infrastructure-as-code, configuration files, deployment scripts, and environment setup to understand operational architectural decisions.

## Instructions

1. **Optional: Use Infrastructure Analysis Tools**
   Consider using infrastructure and configuration analysis tools:
   - **Container Analysis**: dive, docker-slim, hadolint (Dockerfile linting)
   - **Kubernetes**: kubectl, kube-score, polaris, kubesec
   - **Terraform**: tflint, terraform-compliance, checkov
   - **CloudFormation**: cfn-lint, cfn-nag
   - **Ansible**: ansible-lint, molecule
   - **Security Scanning**: trivy, grype, syft (SBOM)
   - **CI/CD**: pipeline linters for GitHub Actions, GitLab CI, Jenkins
   - **General Config**: yamllint, jsonlint, config-lint
   
   Run appropriate tools based on detected infrastructure technologies.

2. **Deployment Architecture**
   - Identify deployment targets (cloud providers, on-premise, hybrid)
   - Analyze containerization strategies (Docker, Kubernetes)
   - Detect CI/CD pipeline configurations
   - Review infrastructure-as-code files (Terraform, CloudFormation, etc.)
   - Use IaC scanning tools to identify best practices and potential issues

3. **Configuration Management**
   - Analyze configuration file structures
   - Identify environment-specific configurations
   - Detect configuration management patterns
   - Review secrets management approach

4. **Scalability and Performance**
   - Identify caching strategies (Redis, Memcached, CDN)
   - Analyze load balancing configurations
   - Detect auto-scaling policies
   - Review resource allocation decisions

5. **Monitoring and Observability**
   - Identify logging frameworks and destinations
   - Detect monitoring and alerting tools
   - Analyze metrics collection strategies
   - Review distributed tracing setup

6. **Networking and Security**
   - Analyze network topology and segmentation
   - Identify firewall and security group rules
   - Detect SSL/TLS configurations
   - Review authentication and authorization infrastructure

## Output Format

```json
{
  "deployment_architecture": {
    "platforms": [
      {
        "type": "aws|azure|gcp|kubernetes|docker|traditional",
        "services_used": ["<service1>", "<service2>"],
        "configuration_files": ["<file1>", "<file2>"]
      }
    ],
    "deployment_strategy": "blue_green|rolling|canary|direct",
    "environment_count": <number>,
    "environments": ["development", "staging", "production"]
  },
  "configuration_management": {
    "approach": "env_files|config_server|kubernetes_configmaps|vault",
    "config_files": [
      {
        "path": "<file_path>",
        "purpose": "<description>",
        "environment_specific": true|false
      }
    ],
    "secrets_management": "environment_variables|vault|aws_secrets|kubernetes_secrets",
    "feature_flags": "present|absent"
  },
  "scalability_decisions": {
    "horizontal_scaling": {
      "enabled": true|false,
      "auto_scaling": true|false,
      "min_instances": <number>,
      "max_instances": <number>
    },
    "caching_layers": [
      {
        "type": "redis|memcached|cdn|application",
        "purpose": "<usage_description>",
        "configuration": "<config_details>"
      }
    ],
    "load_balancing": "application|network|none"
  },
  "observability": {
    "logging": {
      "framework": "<logging_framework>",
      "centralized": true|false,
      "log_aggregation": "<tool_name>"
    },
    "monitoring": {
      "tools": ["<tool1>", "<tool2>"],
      "metrics_collected": ["<metric1>", "<metric2>"],
      "alerting_configured": true|false
    },
    "tracing": {
      "enabled": true|false,
      "tool": "<tracing_tool>"
    }
  },
  "infrastructure_decisions": [
    {
      "area": "<decision_area>",
      "choice": "<what_was_chosen>",
      "rationale": "<why_this_choice>",
      "impact": "<operational_impact>",
      "alternatives": ["<alt1>", "<alt2>"]
    }
  ]
}
```

## Success Criteria

- All deployment and infrastructure configurations identified
- At least 3 infrastructure-related architectural decisions documented
- Clear mapping between configuration files and their purposes
- Scalability and performance strategies clearly outlined
- Output is valid JSON that can be processed by consolidator

## $ARGUMENTS