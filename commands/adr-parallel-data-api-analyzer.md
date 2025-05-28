# ADR Parallel Data and API Analyzer

## Purpose

Analyze data models, APIs, and communication protocols to identify architectural decisions related to data management and system integration.

## Context

This sub-agent examines database schemas, API definitions, data flow patterns, and integration points to understand data and communication architectural decisions.

## Instructions

1. **Data Architecture**
   - Identify database types (relational, NoSQL, graph, time-series)
   - Analyze data models and schemas
   - Detect data partitioning and sharding strategies
   - Review data migration patterns

2. **API Design**
   - Identify API styles (REST, GraphQL, gRPC, SOAP)
   - Analyze API versioning strategies
   - Review API documentation formats (OpenAPI, GraphQL schema)
   - Detect API gateway usage

3. **Communication Patterns**
   - Identify synchronous vs asynchronous communication
   - Analyze message queue usage (RabbitMQ, Kafka, SQS)
   - Detect event-driven architecture patterns
   - Review service discovery mechanisms

4. **Data Flow and Integration**
   - Map data flow between components
   - Identify ETL/ELT processes
   - Analyze data transformation patterns
   - Review external service integrations

5. **Data Governance**
   - Identify data validation strategies
   - Analyze data privacy and compliance measures
   - Detect data retention policies
   - Review backup and recovery strategies

## Output Format

```json
{
  "data_architecture": {
    "databases": [
      {
        "type": "postgresql|mysql|mongodb|redis|elasticsearch",
        "purpose": "<usage_description>",
        "schema_files": ["<file1>", "<file2>"],
        "scaling_strategy": "vertical|horizontal|sharded"
      }
    ],
    "data_patterns": {
      "consistency_model": "strong|eventual|causal",
      "transaction_support": "acid|base|none",
      "caching_strategy": "<description>"
    },
    "data_modeling": {
      "approach": "normalized|denormalized|document|graph",
      "orm_usage": "active_record|data_mapper|none",
      "migration_tool": "<tool_name>"
    }
  },
  "api_architecture": {
    "apis": [
      {
        "name": "<api_name>",
        "style": "rest|graphql|grpc|soap",
        "version_strategy": "uri|header|query_param",
        "documentation": "openapi|graphql_schema|none",
        "authentication": "jwt|oauth|api_key|basic"
      }
    ],
    "api_gateway": {
      "present": true|false,
      "type": "<gateway_type>",
      "features": ["rate_limiting", "authentication", "routing"]
    }
  },
  "communication_patterns": {
    "sync_communication": {
      "protocols": ["http", "grpc", "websocket"],
      "service_discovery": "dns|consul|eureka|kubernetes|none"
    },
    "async_communication": {
      "message_brokers": ["rabbitmq", "kafka", "sqs", "redis"],
      "patterns": ["pub_sub", "work_queue", "event_streaming"],
      "event_schema": "avro|protobuf|json_schema|none"
    }
  },
  "integration_points": [
    {
      "service": "<external_service>",
      "type": "payment|email|storage|analytics",
      "integration_method": "sdk|api|webhook",
      "data_exchange_format": "json|xml|protobuf"
    }
  ],
  "data_decisions": [
    {
      "area": "<decision_area>",
      "choice": "<what_was_chosen>",
      "rationale": "<why_this_choice>",
      "trade_offs": ["<trade_off1>", "<trade_off2>"],
      "alternatives": ["<alt1>", "<alt2>"]
    }
  ]
}
```

## Success Criteria

- All data stores and their purposes identified
- API architecture and design patterns documented
- Communication patterns between services mapped
- At least 3 data or API-related architectural decisions identified
- Output is valid JSON that can be processed by consolidator

## $ARGUMENTS