<div align="center">

# DevOps to Platform Engineering
### A Community-Driven Guide

[![Community Data](https://img.shields.io/badge/community_reports-90-blue)]()
[![Data Points](https://img.shields.io/badge/data_points-30-green)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

</div>

## Table of Contents

- [About This Guide](#about-this-guide)
- [Where You Are Now: Self-Assessment for the Transition](#where-you-are-now-selfassessment-for-the-transition)
- [Phase 1: Foundations – Shifting Mindset & Core Principles (Week 1-2)](#phase-1-foundations--shifting-mindset--core-principles-week-12)
- [Phase 2: Core Skills – Building Robust Systems (Week 3-4)](#phase-2-core-skills--building-robust-systems-week-34)
- [Phase 3: Applied Projects – Building Real-World Platforms (Week 5-8)](#phase-3-applied-projects--building-realworld-platforms-week-58)
- [Recommended Resources](#recommended-resources)
- [Practice Exercises for Each Phase](#practice-exercises-for-each-phase)
- [Contributing](#contributing)

---


## About This Guide

The landscape of infrastructure engineering is rapidly evolving. Traditional DevOps roles are shifting, and the demand signal from the community is clear: "How are we *actually* upskilling to survive the transition from traditional DevOps to Platform Engineering / MLOps?" This guide is your answer.

Forget generic advice. This resource aggregates **real career paths, learning roadmaps, and critical insights** directly from experienced DevOps engineers navigating this exact transition on r/devops. We've distilled the collective wisdom, the "gotchas," and the high-value focus areas into a clear, actionable 8-week roadmap.

You'll discover:
*   Where AI truly impacts your daily tasks (and where it absolutely doesn't).
*   The crucial skills the community emphasizes for architecting robust, cost-effective systems.
*   Specific technologies and project ideas that resonate with current industry needs, including deep dives into specialized areas like AI Infrastructure's reliance on the Nvidia stack (RoCE, Infiniband, Bluefield DPU).
*   How to leverage tools, not just for automation, but for building genuine *platforms*.

This isn't just a list of topics; it's a strategic playbook designed to help you become an indispensable Platform or MLOps Engineer, grounded in the hard-won experiences of your peers.

---

## Where You Are Now: Self-Assessment for the Transition

Before you embark on this journey, it's vital to honestly assess your current skillset and identify areas of vulnerability and strength. The community consensus highlights a critical trend: **AI is automating boilerplate.** As one user with 2 upvotes notes, the work getting automated includes "writing basic YAML, generating Terraform modules."

**Reflect on your current role:**

1.  **Boilerplate Reliance:** Do a significant portion of your daily tasks involve writing repetitive YAML, generating basic IaC modules (Terraform, CloudFormation), or scripting simple automation routines?
    *   *If yes:* This is a red flag. These are the tasks AI is already excelling at, as noted by the community. Your focus needs to shift to higher-level problems.
2.  **System-Level Understanding:** How often do you make decisions about production architecture trade-offs (e.g., choosing between messaging queues, database types, deployment strategies)?
    *   *Community Insight (2 upvotes):* "What AI can't do: understand production architecture trade-offs, debug complex distributed systems, make cost vs reliability decisions." If you're not regularly engaged in these, this roadmap will push you there.
3.  **Debugging Prowess:** Are you confident debugging complex, distributed systems across multiple services and components?
    *   *Community Insight (2 upvotes):* This is another area AI struggles with. Your ability to diagnose and fix non-obvious issues in a distributed environment is a high-value skill.
4.  **Cost vs. Reliability:** Do you actively participate in decisions balancing operational costs with system reliability and performance?
    *   *Community Insight (2 upvotes):* This is a critical business-level skill that differentiates a Platform Engineer from an automation specialist.
5.  **Software Engineering Fundamentals:** How strong are your programming skills (Go, Python, Java, etc.) beyond scripting? Can you design and implement robust APIs?
6.  **Developer Experience (DX):** Do you actively consider how your tools and platforms impact developer productivity and satisfaction?

**Your Goal:** Identify where your skills primarily align with the *automatable* versus the *irreplaceable* categories identified by the community. This assessment will help you prioritize your learning in the subsequent phases.

---

## Phase 1: Foundations – Shifting Mindset & Core Principles (Week 1-2)

This phase is about changing your perspective from "managing infrastructure" to "building a product (a platform) for developers." It's about understanding the "why" before the "how."

### Key Concepts & Focus Areas:

1.  **The Platform Engineering Philosophy:**
    *   **From Tools to Product:** Understand that an Internal Developer Platform (IDP) is a product. Your developers are your customers. Focus on their pain points, self-service, and cognitive load reduction.
    *   **Team Topologies:** Grasp the concepts of Stream-Aligned Teams, Platform Teams, Enabling Teams, and Complicated Subsystem Teams. This helps define the scope and interaction model for your platform.
    *   **Developer Experience (DX):** Prioritize making developers' lives easier. This means intuitive tooling, clear documentation, and fast feedback loops.

2.  **Core Software Engineering Principles:**
    *   **API Design:** Learn RESTful principles, gRPC, and how to design clean, consistent, and versioned APIs. Your platform will be consumed programmatically.
    *   **Observability Fundamentals:** Introduction to metrics, logging, and tracing. Understand *why* these are crucial for a platform, not just for debugging applications.
    *   **Security by Design:** Shift left on security. Understand common vulnerabilities (OWASP Top 10) and how to build secure-by-default components.

3.  **Basic FinOps:**
    *   Understand cloud cost models (compute, storage, network).
    *   Learn basic cost monitoring and optimization strategies. *Community Insight:* "Making cost vs reliability decisions" is a non-AI task (2 upvotes), so start building this muscle early.

### Leveraging AI in Phase 1:

A significant community observation (11 upvotes) highlights that "AI is also very good at documenting everything... complete docs for every script, module and workflow, including diagrams." **Don't waste time on manual documentation.** Use AI tools to generate:
*   Initial drafts of API documentation.
*   Diagrams for your planned platform architecture.
*   Comments and explanations for any boilerplate code you *do* write during learning.
This frees up your cognitive energy to focus on the higher-level design and trade-offs.

### Practice Exercises (Week 1-2):

1.  **Design a "Hello World" API Platform:** Outline the APIs a developer would use to deploy a simple microservice. Focus on the user journey and self-service.
2.  **Backstage Exploration:** Set up a local instance of Backstage (an open-source IDP) and explore its core features (Service Catalog, Scaffolder). Imagine how you'd use it to onboard a new service.
3.  **API Contract First:** For a simple service (e.g., a user management API), define its OpenAPI (Swagger) specification before writing any code.
4.  **Cost Analysis:** Pick a simple cloud service (e.g., S3 bucket, EC2 instance) and research its pricing model. Calculate potential costs for a hypothetical workload.

---

## Phase 2: Core Skills – Building Robust Systems (Week 3-4)

This phase delves into the technical depth required to build and operate reliable, scalable platforms. This is where you develop the skills AI *cannot* replicate.

### Key Concepts & Focus Areas:

1.  **Advanced Kubernetes & Cloud-Native Ecosystem:**
    *   **Operators & Custom Resources (CRDs):** Understand how to extend Kubernetes with custom logic. This is fundamental to building self-service platform capabilities.
    *   **Service Mesh (e.g., Istio, Linkerd):** Dive deep into traffic management, security, and observability at the network layer.
    *   **Container Security:** Image scanning, runtime security, network policies.
    *   **Advanced Networking:** Understand CNI plugins, ingress controllers, Egress gateways, and how they contribute to a secure and performant platform.

2.  **Distributed Systems Engineering:**
    *   **Concurrency & Parallelism:** Go beyond basic scripting; understand design patterns for concurrent systems.
    *   **Fault Tolerance & Resilience:** Circuit breakers, retries, exponential backoffs, idempotency. Design systems that expect failure.
    *   **Consistency Models:** Eventual vs. Strong consistency in distributed databases.
    *   **Message Queues & Event Streaming (Kafka, RabbitMQ, SQS/SNS):** Deep dive into their use cases, guarantees, and operational aspects.

3.  **Comprehensive Observability & Reliability:**
    *   **Metrics (Prometheus, Grafana):** Advanced PromQL, dashboard design, alert configuration.
    *   **Logging (ELK Stack, Loki, Splunk):** Centralized logging, structured logging, effective querying for troubleshooting.
    *   **Tracing (Jaeger, OpenTelemetry):** Distributed tracing for understanding request flows across microservices.
    *   **Site Reliability Engineering (SRE) Principles:** SLOs, SLIs, error budgets. Understand how to define and measure platform reliability.
    *   *Community Insight (2 upvotes):* Remember, AI can't "debug complex distributed systems." This section directly addresses that gap by arming you with the tools and methodologies for effective troubleshooting and system design.

4.  **Security for Platforms:**
    *   **Identity & Access Management (IAM):** Advanced concepts in cloud IAM, OIDC, OAuth2, and integrating with enterprise directories.
    *   **Secrets Management (Vault, AWS Secrets Manager, Azure Key Vault):** Secure storage, retrieval, and rotation of sensitive data.
    *   **Supply Chain Security:** Protecting your CI/CD pipelines and artifact repositories (e.g., SLSA, Notary).

5.  **Specialization Track: MLOps / AI Infrastructure Fundamentals:**
    *   **Introduction to HPC:** For those looking specifically at AI/ML infrastructure, community consensus points to a specialized area. A user notes, "A lot of AI infrastructure has to do with HPC and mostly around Nvidia stack. They are the market leaders."
    *   **Key Technologies:** Start exploring concepts like:
        *   **RoCE (RDMA over Converged Ethernet):** High-speed, low-latency networking for data-intensive workloads.
        *   **Infiniband:** Another high-performance networking technology common in HPC and AI clusters.
        *   **Nvidia Cumulus Linux:** A network operating system for building high-performance data center networks.
        *   **Bluefield DPU (Data Processing Unit):** Understand the role of DPUs in offloading network and security tasks to accelerate AI/ML workloads.
    *   This track is crucial if you want to heed the community advice to "change your role on linkedin from 'Senior DevOps' to 'AI infrastructure'."

### Practice Exercises (Week 3-4):

1.  **Build a Kubernetes Operator (Simple):** Create a basic Operator that manages a custom resource (e.g., deploying an Nginx instance for a `Website` CRD).
2.  **Service Mesh Implementation:** Deploy Istio or Linkerd into a Kubernetes cluster and experiment with traffic routing, mTLS, and basic observability features.
3.  **Distributed Tracing:** Instrument a simple microservices application with OpenTelemetry and deploy it. Visualize traces in Jaeger.
4.  **Fault Injection:** Implement a simple chaos engineering experiment (e.g., randomly killing a pod) and observe its impact on your system's SLOs.
5.  **MLOps Simulation (Optional for AI Infra track):** Research and simulate a distributed training job's networking requirements. How would RoCE or Infiniband improve performance?

---

## Phase 3: Applied Projects – Building Real-World Platforms (Week 5-8)

This is where you synthesize your knowledge and build tangible artifacts. The goal is to create portfolio-worthy projects that demonstrate your ability to design, build, and operate robust platforms. This phase also directly addresses community concerns about "semi-vibecoded garbage" by emphasizing robust engineering practices.

### Project Themes & Ideas:

1.  **Self-Service Deployment Portal (Core Platform Engineering):**
    *   **Goal:** Build a user-friendly web interface or CLI tool that allows developers to deploy their applications to Kubernetes with predefined templates and guardrails.
    *   **Components:** Backstage (scaffolder, service catalog), Argo CD/Flux (GitOps), Kubernetes (deployment, service, ingress), a simple API backend (Go/Python) for orchestrating actions.
    *   **Focus:** Developer experience, security (RBAC, secrets), automated testing of your platform components.
    *   *Community Insight:* This directly addresses the need to shift from manual ops to platform building, enabling developers to "self-serve" deployments securely.

2.  **Feature Flag Management System (Advanced Platform Feature):**
    *   **Goal:** Implement a system that allows developers to manage feature flags dynamically, enabling A/B testing, gradual rollouts, and kill switches.
    *   **Components:** API for flag management, a persistent store (Redis, DynamoDB), a client-side SDK (example in a language like Go/Python), Prometheus/Grafana for monitoring flag usage and impact.
    *   **Focus:** API design, real-time data propagation, observability of feature flag impact, operational safety (kill switches).

3.  **Automated Environment Provisioning (IaC & GitOps for Platforms):**
    *   **Goal:** Develop a GitOps-driven pipeline to provision complete development, staging, or even production environments on demand.
    *   **Components:** Terraform/Pulumi (for cloud resources), Argo CD/Flux (for Kubernetes resources), Atlantis/Terraform Cloud (for IaC workflow), a basic CI pipeline (GitHub Actions/GitLab CI) for PR validation.
    *   **Focus:** Immutability, drift detection, security (least privilege for service accounts), cost awareness.
    *   *Community Insight:* While AI can generate basic Terraform, *designing* a robust, self-service environment provisioning system that handles trade-offs and security is where your value lies (2 upvotes).

4.  **MLOps Pipeline Platform (Specialized AI/ML Infra):**
    *   **Goal:** Build a platform that enables data scientists to deploy, monitor, and manage machine learning models through a CI/CD-like pipeline.
    *   **Components:** Kubeflow/MLflow/Sagemaker, Argo Workflows (for orchestration), Prometheus/Grafana (for model monitoring), a model registry (e.g., MLflow Model Registry).
    *   **Specific for HPC/Nvidia Track:** Integrate concepts related to optimizing for GPU workloads. Consider how you would provision and manage GPU resources using tools like `nvidia-container-toolkit` or Kubernetes device plugins. Explore how a system might leverage **RoCE, Infiniband, or Bluefield DPU** for high-throughput model training or inference, even if you're just designing the architecture or using simulations for proof of concept.
    *   *Community Insight:* "Change your role on linkedin from 'Senior DevOps' to 'AI infrastructure'" means diving into these specific areas. This project directly utilizes the community's advice on targeting the Nvidia stack.

### Addressing "Vibe Coded Garbage" Concerns:

Throughout all projects, actively integrate:
*   **Comprehensive Testing:** Unit, integration, and end-to-end tests for all platform components.
*   **Robust Error Handling:** Design for failure, with clear error messages and graceful degradation.
*   **Security Audits:** Regularly review code and configurations for security vulnerabilities.
*   **Performance Benchmarking:** Test the performance of your platform components under load.
*   **Clear Documentation:** Even if AI assists, ensure it's accurate and easily understandable by developers.

---

## Recommended Resources

These resources are highly regarded within the community for deep understanding, not just surface-level knowledge.

### Books:

*   **Team Topologies: Organizing Business and Technology Teams for Fast Flow** by Matthew Skelton & Manuel Pais (Essential for understanding platform organization)
*   **Site Reliability Engineering (SRE) & The Site Reliability Workbook** (Google) (For reliability principles and practices)
*   **Accelerate: The Science of Lean Software and DevOps** by Nicole Forsgren, Jez Humble, Gene Kim (Understanding high-performing teams)
*   **Designing Data-Intensive Applications** by Martin Kleppmann (Deep dive into distributed systems concepts)
*   **Kubernetes Patterns** by Roland Huß and Bilgin Ibryam (Advanced Kubernetes design)
*   **Building Internal Developer Platforms** by Kevin Hoffman (For practical IDP construction)

### Online Courses & Certifications:

*   **Certified Kubernetes Application Developer (CKAD) / Certified Kubernetes Administrator (CKA):** Foundational for any platform role.
*   **HashiCorp Certified Terraform Associate:** For advanced IaC strategies.
*   **Cloud Provider Certifications (AWS Solutions Architect, Azure DevOps Engineer, GCP Professional Cloud Architect):** Choose based on your target cloud. Focus on architecture and services, not just basic usage.
*   **"Platform Engineering on Kubernetes" courses (e.g., from CNCF, Cloud Native Associates):** Look for specialized courses that focus on the *platform* aspect.
*   **Nvidia DLI (Deep Learning Institute) courses:** For the MLOps/AI Infrastructure track, explore courses on GPU programming, CUDA, and HPC networking.

### Open Source Projects & Repositories:

*   **Backstage (Spotify):** The leading open-source Internal Developer Portal. Get hands-on.
    *   *GitHub:* `https://github.com/backstage/backstage`
*   **Argo Project (CD, Workflows, Events, Rollouts):** Critical for GitOps and workflow orchestration.
    *   *GitHub:* `https://github.com/argoproj`
*   **Prometheus & Grafana:** Essential for monitoring.
    *   *GitHub:* `https://github.com/prometheus/prometheus`, `https://github.com/grafana/grafana`
*   **OpenTelemetry:** Standard for instrumentation.
    *   *GitHub:* `https://github.com/open-telemetry`
*   **Istio / Linkerd:** Service mesh implementations.
    *   *GitHub:* `https://github.com/istio/istio`, `https://github.com/linkerd/linkerd2`
*   **Kubeflow:** The Machine Learning Toolkit for Kubernetes.
    *   *GitHub:* `https://github.com/kubeflow/kubeflow`
*   **MLflow:** Open-source platform for the machine learning lifecycle.
    *   *GitHub:* `https://github.com/mlflow/mlflow`
*   **Nvidia-Container-Toolkit:** Essential for running GPU-accelerated containers.
    *   *GitHub:* `https://github.com/NVIDIA/nvidia-container-toolkit`
*   **Learn Kubernetes the Hard Way:** A classic for deep understanding.
    *   *GitHub:* `https://github.com/kelseyhightower/kubernetes-the-hard-way`

---

## Practice Exercises for Each Phase

These exercises are designed to be hands-on and build upon each other, integrating the community-driven insights.

### Phase 1: Foundations (Week 1-2)

1.  **Platform Vision Document:** Draft a short (1-2 page) vision document for an internal platform. Define your "customers" (developers), their top 3 pain points, and how your platform would solve them. Use AI to help generate initial ideas for feature descriptions, then refine them yourself.
2.  **Basic API Definition:** Define an OpenAPI (Swagger) spec for a `project` service that allows developers to create, read, update, and delete project entries in your hypothetical platform catalog. Focus on clear endpoints, request/response schemas, and error codes.
3.  **Local Backstage Setup:** Successfully deploy Backstage locally using Docker or `yarn start`. Explore its service catalog, add a few dummy services, and try scaffolding a new project using its default templates. Document your observations on DX.
4.  **FinOps Exploration:** Use your cloud provider's cost explorer to identify the top 3 most expensive services in a sample account. Research 2-3 strategies to reduce costs for each, considering reliability trade-offs.

### Phase 2: Core Skills (Week 3-4)

1.  **Kubernetes Operator for a Simple App:** Choose a basic application (e.g., a Redis instance or a simple web server). Write a Kubernetes Operator (using Operator SDK or Kubebuilder) that manages its lifecycle via a Custom Resource Definition (CRD).
2.  **Service Mesh Traffic Management:** Deploy two simple microservices (e.g., a `frontend` and a `backend`) into a Kubernetes cluster with Istio or Linkerd. Implement traffic splitting (e.g., 90/10) to a canary version of your `backend` service. Observe metrics and logs in Grafana.
3.  **Distributed Tracing Implementation:** Take a simple existing microservices application (or build one with 2-3 services). Instrument it with OpenTelemetry for distributed tracing. Deploy it and verify that traces correctly flow across all services in Jaeger.
4.  **SLO/SLI Definition:** For a hypothetical critical platform component (e.g., your internal deployment API), define at least two Service Level Indicators (SLIs) and a corresponding Service Level Objective (SLO). Explain how you would measure these.
5.  **MLOps/HPC Research (AI Infra Track):** Research a specific use case where RoCE or Infiniband would provide significant performance benefits over standard Ethernet for an ML workload (e.g., distributed model training). Write a short summary (1 page) explaining the technology and its benefits in that context.

### Phase 3: Applied Projects (Week 5-8)

1.  **Minimum Viable Platform (MVP):**
    *   **Objective:** Build a simplified self-service portal (could be CLI-based) that takes a service name and a Git repository URL, then deploys a basic containerized application to Kubernetes.
    *   **Components:** Python/Go CLI or web frontend, Kubernetes `Deployment` and `Service` YAML generation, `kubectl apply` (or simple `client-go` logic), basic GitOps integration with Argo CD/Flux for synchronization.
    *   **Focus:** Developer experience, automation, basic error handling.
2.  **GitOps-Driven Environment Provisioning:**
    *   **Objective:** Create a Terraform module to provision a new namespace in Kubernetes and a dedicated database (e.g., Postgres on AWS RDS) for a "staging" environment. Set up a GitOps repository (e.g., on GitHub) with Argo CD/Flux to automatically deploy the base Kubernetes resources (service accounts, RBAC, network policies) into that namespace once Terraform applies.
    *   **Focus:** Infrastructure as Code best practices, GitOps principles, security (least privilege for cloud roles), automated testing of your Terraform code.
3.  **AI Model Deployment Pipeline (AI Infra Track):**
    *   **Objective:** Design and implement a simple MLOps pipeline using Argo Workflows or Kubeflow Pipelines.
    *   **Pipeline Stages:** Data preprocessing, model training (using a dummy model), model versioning (e.g., saving to S3 with a version tag), and deploying the model as a REST API endpoint (e.g., with Seldon Core or KServe).
    *   **Focus:** Automation of ML lifecycle, reproducibility, basic model monitoring concepts. If possible, integrate a GPU-enabled base image and confirm GPU access.
4.  **Security Audit & Hardening:**
    *   **Objective:** Take one of your deployed projects (from any phase) and perform a basic security audit.
    *   **Tasks:** Scan container images for vulnerabilities (e.g., Trivy, Clair). Configure Kubernetes Network Policies to restrict traffic. Implement secrets management for sensitive application data (e.g., using `external-secrets` with Vault/cloud secrets manager).
    *   **Focus:** Proactive security, "shift-left" practices.

---


---

## Contributing

Found an error or have better benchmarks? PRs welcome! This guide improves with community input.

Originally inspired by [this discussion](https://reddit.com/r/devops/comments/1thv5r4/).


---

## Related Guides

- [48GB VRAM LLM Playbook](https://github.com/essentialols/48gb-vram-llm-guide) - Model selection, configs, and benchmarks for 48GB setups
- [DevOps to Platform Engineering Guide](https://github.com/essentialols/devops-platform-engineering-guide) - Career transition paths and upskilling roadmaps  
- [Go Modular Monolith Guide](https://github.com/essentialols/go-modular-monolith-guide) - Architecture patterns for large Go codebases

