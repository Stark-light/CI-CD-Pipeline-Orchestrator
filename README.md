# CI/CD Pipeline Orchestrator (Java)

A lightweight Java-based CI/CD orchestration platform designed to automate build and deployment workflows using DAG-based execution, concurrent job scheduling, rollback hooks, and real-time execution monitoring.

## Features

* YAML-based pipeline configuration
* DAG-driven stage execution
* Concurrent job scheduling
* Build and deployment orchestration
* Real-time log streaming
* Rollback hook support
* Execution monitoring
* Failure handling and retry support

## Tech Stack

* Java
* Multithreading
* Maven
* JUnit
* YAML Parsing
* REST APIs
* Linux

---

## Architecture Overview

The orchestrator models deployment pipelines as Directed Acyclic Graphs (DAGs), where:

* Nodes represent pipeline stages
* Edges represent stage dependencies
* Independent stages execute concurrently
* Failures trigger rollback hooks

The execution engine dynamically schedules runnable stages based on dependency resolution.

---

## Sample Pipeline Configuration

```yaml
pipeline:
  stages:
    - build
    - test
    - deploy

build:
  command: mvn clean install

test:
  command: mvn test
  depends_on: build

deploy:
  command: ./deploy.sh
  depends_on: test
```

---

## Core Modules

```bash
src/
 ├── parser/
 ├── scheduler/
 ├── executor/
 ├── monitoring/
 ├── rollback/
 └── logging/
```

---

## Execution Flow

1. Parse YAML pipeline definition
2. Build DAG representation
3. Resolve dependency graph
4. Execute independent jobs concurrently
5. Stream logs in real time
6. Trigger rollback hooks on failure
7. Generate execution report

---

## Key Engineering Concepts

* CI/CD Fundamentals
* DAG-based Scheduling
* Concurrent Execution
* Pipeline Orchestration
* Fault Tolerance
* Deployment Automation
* Dependency Resolution
* Thread-safe Job Scheduling

---

## Future Improvements

* Docker container execution
* Kubernetes deployment integration
* Web dashboard for monitoring
* Distributed worker nodes
* Artifact versioning
* Notification system

---

## Learning Outcomes

This project helped in understanding:

* CI/CD workflow orchestration
* Parallel execution strategies
* Deployment pipeline architecture
* Dependency graph scheduling
* Fault recovery mechanisms
* Enterprise DevOps infrastructure concepts
