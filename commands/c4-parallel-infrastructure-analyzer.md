# Infrastructure Analysis for C4 Deployment View

## Purpose
Analyze infrastructure configurations and deployment artifacts to generate accurate C4 deployment diagrams and documentation.

## Context
Infrastructure analysis reveals how the system is deployed, scaled, and operated, which is essential for the C4 deployment view and operational understanding.

## Instructions

1. Analyze containerization:
   - Dockerfile configurations
   - Docker Compose files
   - Container orchestration configs

2. Examine cloud configurations:
   - Infrastructure as Code files
   - Cloud provider configurations
   - Serverless definitions

3. Identify deployment environments:
   - Development setup
   - Staging configuration
   - Production architecture

4. Extract operational configs:
   - CI/CD pipelines
   - Monitoring setup
   - Logging configuration
   - Security policies

5. Map infrastructure components:
   - Load balancers
   - Databases
   - Message queues
   - Caching layers

## Output Format

```json
{
  "containerization": {
    "docker_images": [],
    "orchestration": "kubernetes|docker-compose|ecs|none",
    "registries": []
  },
  "cloud_infrastructure": {
    "provider": "",
    "services": [],
    "regions": []
  },
  "environments": {
    "development": {},
    "staging": {},
    "production": {}
  },
  "operational": {
    "ci_cd": {},
    "monitoring": [],
    "logging": []
  },
  "infrastructure_components": {
    "compute": [],
    "storage": [],
    "networking": [],
    "services": []
  }
}
```

## Success Criteria

- All deployment configurations identified
- Environment differences documented
- Infrastructure dependencies mapped
- Scaling strategies identified

$ARGUMENTS