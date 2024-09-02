# OSS Interview Assignment: Observability Pipeline

## Project Overview

Build a comprehensive observability pipeline that collects telemetry data from a Python application via SDKs, processes and transforms them via OpenTelemetry collectors, and stores logs, traces, and metrics in ClickHouse for efficient retrieval and analysis.

## Key Components

### 1. Python SDK for Telemetry Collection

Develop a Python SDK that wraps the OpenTelemetry SDK to simplify telemetry data collection.

#### Requirements:
- Create a PyPI package for easy installation: `pip install your_sdk_name`
- Provide simple APIs for instrumenting Python applications
- Support automatic instrumentation for common frameworks (e.g., Flask, FastAPI)
- Include options for manual instrumentation
- Support all three telemetry signals: logs, traces, and metrics

#### Example usage:
```python
from your_sdk_name import instrument_app

app = Flask(__name__)
instrument_app(app, service_name="my-service")
```

### 2. OpenTelemetry Collector Setup

Set up OpenTelemetry collectors to process and transform telemetry data.

#### Requirements:
- Use Docker Compose for local development setup
- Configure collectors to receive data from your Python SDK
- Implement data processing pipelines (e.g., filtering, sampling)
- Set up exporters to send data to ClickHouse

#### Bonus:
- Create a Helm chart for deploying collectors in Kubernetes
- Implement horizontal scaling for collectors

### 3. ClickHouse Backend

Set up a ClickHouse instance as the backend for storing telemetry data.

#### Requirements:
- Design efficient schema for storing logs, traces, and metrics
- Implement data retention and archiving policies
- Ensure proper indexing for fast query performance

#### Bonus:
- Create a Helm chart for deploying ClickHouse in Kubernetes
- Implement a multi-node ClickHouse cluster for high availability

### 4. Web Application for Data Retrieval

Create a basic web application to fetch and display telemetry data from the ClickHouse backend.

#### Requirements:
- Implement endpoints for retrieving logs, traces, and metrics
- Optimize queries for ordered trace and log retrieval
- Develop efficient aggregation queries for metrics
- Create a simple frontend to visualize the data
- Implement pagination and time-range selection

#### Performance Optimization:
- Use materialized views in ClickHouse for pre-aggregated metrics
- Implement caching strategies for frequently accessed data
- Use efficient ClickHouse-specific query patterns (e.g., prewhere, final)

### 5. Documentation and Deployment

Provide comprehensive documentation for your solution:
- Detailed README with setup instructions
- Architecture diagram explaining the data flow
- API documentation for your Python SDK
- Query optimization strategies used in the web application

#### Deployment:
- Include Docker Compose file for local deployment of the entire stack
- Provide Kubernetes manifests or Helm charts (if implemented)

## Evaluation Criteria

- Code quality and organization
- Performance and scalability considerations
- Effective use of OpenTelemetry, ClickHouse, and Kubernetes (if implemented)
- Completeness of the solution
- Quality of documentation
- Creativity in solving observability challenges

## Submission Guidelines

1. Provide a GitHub repository with your complete project.
2. Ensure frequent, meaningful commits throughout the development process.
3. Include all necessary documentation in the repository.
4. Create a Loom video (10-15 minutes) explaining:
   - Your solution architecture
   - Key design decisions and trade-offs
   - A walkthrough of the main functionalities
   - Performance optimization strategies
   - Challenges faced and how you overcame them

## Bonus Points

- Implement distributed tracing across multiple services
- Add alerting based on collected metrics
- Create a custom processor for the OpenTelemetry collector
- Implement advanced ClickHouse features (e.g., materialized views, dictionaries)
- Develop a CLI tool for querying the observability data

Good luck! :)
