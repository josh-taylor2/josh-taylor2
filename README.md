# Hi, I'm Josh

Software developer focused on **full-stack web applications, cloud infrastructure, and DevOps automation**.

I'm a fourth year student at **McGill University** (expected graduation in Winter 2028). Most of the work
below comes from my software development internship on a **DevOps team**, where I
shipped internal tools used by developers, administrators, and the UX team.

📫 **Reach me:** [joshua.taylor2@mail.mcgill.ca](mailto:joshua.taylor2@mail.mcgill.ca) · [LinkedIn](https://www.linkedin.com/in/joshua-taylor-809013291/)

---

## 🧭 How I Work

My strength is in communicating requirements and turning them into a clear architecture and spec — having spent 8 months on a DevOps team across 2 internships, I've learned to work across a broad distribution of languages and technologies, too many to be an expert in every one. In practice that means I lean heavily on **spec-driven, AI-assisted development with [Kiro](https://kiro.dev)**: I'm meticulous about requirements, design docs, and acceptance criteria, then drive implementation from those specs rather than free-handing every line. It's the same skill behind the [DORA Catch-All Workflow](https://github.com/josh-taylor2/dora-catch-all-workflow) below, where I wrote the full spec before implementing a line of it.

The technologies listed below are some of the notable ones I've interacted with during my time as a DevOps intern.

---

## 🛠️ Technologies I've Worked Across

| Area | Technologies |
|------|--------------|
| **Languages** | Java 21 · TypeScript · Python · JavaScript · Bash · SQL |
| **Frontend** | Vue 3 (Composition API) · Vite · Vanilla JS SPAs · HTML/CSS |
| **Backend** | Spring Boot · Node.js / Express · REST API design |
| **Databases** | PostgreSQL · MongoDB |
| **Cloud (AWS)** | ECS Fargate · EKS · S3 · ALB · Route53 · IAM · RDS · EC2 · ACM · SSM |
| **Infrastructure** | Terraform · Docker · Kubernetes · Helm |
| **CI/CD** | GitLab CI/CD (multi-stage pipelines, scheduled jobs, manual triggers) |
| **Auth & Security** | OAuth2 / OIDC · Keycloak · Okta · JWT · AES-256-GCM encryption at rest |
| **AI / Spec-Driven Dev** | Kiro · LLM integration · Model Context Protocol (MCP) · Jira REST API |

---

## 📂 Projects

All projects below are from my internship. Because the original code is proprietary, each repo
contains **architecture documentation and sanitized code snippets** rather than a runnable
application — no credentials, internal hostnames, or account identifiers are included.

### Full-Stack Applications

**[License Generator Web App](https://github.com/josh-taylor2/license-generator)**
A Spring Boot + MongoDB application for creating, searching, and managing software license keys,
replacing a manual and error-prone process. I built the REST API with ETag-based HTTP caching, a
vanilla-JS single-page frontend with client-side routing and dynamic form generation, the OAuth2/OIDC
security layer, and the full Terraform + GitLab CI deployment onto ECS Fargate.
`Java 21` `Spring Boot` `MongoDB` `Terraform` `AWS` `GitLab CI/CD` `OAuth2`

**[Admin Portal](https://github.com/josh-taylor2/admin-portal)**
A Vue 3 + Express + PostgreSQL portal that gave CloudOps administrators self-service control over
customer configurations — work that previously required a developer for every change. Designed and
built from scratch, including the database schema, an AES-256-GCM encrypted messaging system, a
safe-by-default capability toggle service, and Kubernetes-native deployment with idempotent migrations.
`TypeScript` `Vue 3` `Express` `PostgreSQL` `Kubernetes` `Helm` `Keycloak`

### Cloud Infrastructure

**[Design Prototypes Platform](https://github.com/josh-taylor2/design-prototypes-platform)**
Terraform-managed internal hosting that let the UX team publish and share coded prototypes with
stakeholders without pulling in DevOps for every deploy. S3 static hosting behind an internal
HTTPS load balancer with Route53 DNS and automatic deployment on push.
`Terraform` `AWS (S3, ALB, Route53, ACM)` `GitLab CI/CD`

**[GitLab Nightly Shutdown](https://github.com/josh-taylor2/dev-gitlab-scheduler)**
A scheduled pipeline that cut AWS spending by shutting down a development GitLab instance (EC2 + RDS)
outside business hours. Uses cross-account IAM role assumption and idempotent state checks so it's
safe to run repeatedly.
`Bash` `AWS CLI` `IAM / STS` `GitLab CI Schedules`

### DevOps Automation & AI

**[DORA Catch-All Workflow](https://github.com/josh-taylor2/dora-catch-all-workflow)**
DORA is a multi-agent DevOps system built by one of my teammates; it dispatches Jira tickets to dedicated workflows for known problem types. I built the catch-all workflow that runs when no dedicated workflow matches — it searches a nightly-updated knowledge base of past incidents (built by my [ticket-hunter](https://github.com/josh-taylor2/ticket-hunter-agent) pipeline) and posts a proposed solution or triage recommendation, so every ticket gets a response instead of hitting a dead end. Spec-driven: I wrote EARS-style requirements and a design doc before implementation.
`AI / LLM` `MCP` `Jira REST API` `Bash` `systemd`

**[Automated Image Promotion Pipeline](https://github.com/josh-taylor2/images-promotion)**
Replaced the weekly manual creation of Jira Change Request tickets for promoting patched container
images to staging and production. Parses a patch report, builds Jira wiki-markup tables, and files
fully-populated tickets through the Jira Service Management API.
`Bash` `Jira REST API` `GitLab CI/CD` `yq` `jq`

**[AI Pipeline Error Resolution Agent](https://github.com/josh-taylor2/ticket-hunter-agent)**
Mines closed Jira incident tickets for root-cause comments and generates an AI-summarized knowledge
base, which an agent then uses to match new pipeline failures against known patterns and suggest fixes.
`Python` `Jira REST API` `LLM Integration` `GitLab CI/CD`

---

## 📌 A Note on These Repositories

These projects were built during an internship on proprietary internal systems, so the complete
source cannot be published. Each repository instead contains:

- **A written case study** — the problem, the solution, the architecture, and the key technical decisions
- **Sanitized code snippets** demonstrating the actual patterns I implemented
- **A clear statement of my specific contribution** to each project

Every snippet has been reviewed to remove credentials, internal hostnames, account identifiers, and
proprietary business logic.
