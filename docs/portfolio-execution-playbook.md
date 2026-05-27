# Portfolio Execution Playbook

This playbook defines how to use Hermes Agent to build the four portfolio projects.

## Operating Model

Hermes should act as the portfolio orchestrator.

- Hermes owns planning, documentation, review, and verification.
- Coding agents such as Codex can be used as implementation workers.
- Research Agent gathers references and comparable examples.
- Project Onboarding Agent should be added later for new repositories.
- Cron jobs can monitor papers, tools, and benchmark updates.

## Default Workflow Per Project

### 1. Research

Use the Research Agent to collect:

- comparable case studies
- reference architectures
- relevant open-source projects
- security/MLOps best practices
- datasets if needed

Output:

```text
research/reports/YYYY-MM-DD-project-name-background.md
```

### 2. Design

Create:

- README draft
- architecture diagram
- milestone plan
- threat model or MLOps notes

Output:

```text
docs/plans/project-name-implementation-plan.md
```

### 3. Scaffold

Create repository skeleton:

- backend
- frontend if needed
- docker-compose
- tests
- docs
- README
- GitHub Actions

### 4. Implement MVP

Use small milestones. Each milestone should end with:

- working demo
- tests or verification command
- README update
- commit

### 5. Review

Review for:

- correctness
- security
- reproducibility
- README quality
- architecture clarity
- portfolio signal strength

### 6. Polish

Add:

- screenshots
- sample outputs
- limitations
- roadmap
- deployment notes

## Project 1: Closed Local LLM Platform

Recommended first milestone:

```text
Create a Docker Compose app with Next.js UI, FastAPI gateway, and Ollama-backed chat endpoint. Include README architecture diagram and health checks.
```

Verification:

- `docker compose up` works.
- UI can send prompt to backend.
- backend can call Ollama.
- README explains closed-network rationale.

## Project 2: Retail Intelligence Platform

Recommended first milestone:

```text
Create sample retail dataset, dbt-style transformation structure, baseline forecast, and MLflow experiment tracking.
```

Verification:

- training command runs.
- MLflow logs params/metrics/artifacts.
- baseline forecast is saved.

## Project 3: Industrial Vision AI

Recommended first milestone:

```text
Train a small U-Net or segmentation baseline on a public/synthetic dataset and log metrics to W&B.
```

Verification:

- training command runs.
- W&B logs metrics and prediction images.
- inference script produces mask overlay.

## Project 4: Physical AI Lab

Recommended first milestone:

```text
Create FastAPI service that accepts text instruction + image and returns structured action JSON for a simulated ROS2 node.
```

Verification:

- sample command returns valid action JSON.
- ROS2-compatible interface or mock node receives the command.
- README explains limitations clearly.

## Hermes Prompts to Use

### Research prompt

Use:

```text
prompts/research-agent.md
```

### Report template

Use:

```text
prompts/report-template.md
```

### README template

Use:

```text
prompts/portfolio-project-readme-template.md
```

## Quality Bar Before Publishing

Before calling a project portfolio-ready, verify:

- README quick start works.
- Architecture diagram is accurate.
- Security/MLOps sections are specific, not generic.
- Main demo can be run by another person.
- There is at least one test or verification command.
- Limitations are honest.
- Commits are clean.
