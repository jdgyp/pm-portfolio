# Product Requirements Document
## Integration Build Kits

| Field | Detail |
|---|---|
| **Product Name** | Integration Build Kits |
| **Product Group** | Integration Factory |
| **Product Manager** | [Redacted] |
| **Target Users** | Domain Engineering Teams, Integration Engineers |
| **Status** | Live — iterating |
| **Last Updated** | April 2026 |

---

## 1. Executive Summary

Integration Build Kits provide a standardised, production-ready foundation for building integrations across the enterprise. By abstracting away common platform concerns — service scaffolding, CI/CD, observability, security, and deployment — domain teams can focus on business-specific integration logic rather than rebuilding shared plumbing.

**Core value proposition:** Speed-to-value with guardrails. Integrations are delivered faster and more safely, with lower long-term support and maintenance cost.

---

## 2. Problem Statement

### Current Pain Points

- Integration teams repeatedly solve the same non-differentiating problems: deployment, logging, monitoring, secrets management.
- Inconsistent build patterns and pipelines increase operational risk and support burden.
- Slow onboarding and unclear ownership models delay delivery and create a poor developer experience.
- Legacy and bespoke integration frameworks make modernisation, migration, and support unnecessarily difficult.

### Why Now

- Demand for data movement, eventing, and API-to-pipeline integrations is accelerating across domains.
- There is a strategic need to reduce the legacy integration estate and converge on repeatable, governed patterns.
- Integration Build Kits have reached sufficient maturity to move from "startup mode" to a scalable platform model.

---

## 3. Goals & Success Metrics

### Product Goals

1. Reduce time to first production-ready integration.
2. Improve consistency, security, and operability across all integrations.
3. Enable self-service onboarding with clear ownership boundaries.
4. Eliminate repeated boilerplate and custom infrastructure work.

### Success Metrics

| Dimension | Metric |
|---|---|
| **Adoption** | Number of teams and integrations actively using Build Kits |
| **Efficiency** | Reduced time-to-build vs legacy or bespoke approaches |
| **Operational Quality** | Reduction in P1/P2 incidents caused by non-standard pipelines |
| **Satisfaction** | Qualitative feedback scores via platform feedback channels |

---

## 4. Non-Goals

Integration Build Kits explicitly do **not**:

- Own or define business logic, transformation rules, or domain data models.
- Replace engineering judgement or architectural decision-making.
- Define enterprise standards or policies (these sit with central Architecture and InfoSec).
- Support every framework or runtime by default.

---

## 5. Target Users & Personas

### Primary Personas

**Integration Engineer (Domain Team)**
Needs to build, test, and deploy integrations quickly and safely, without worrying about platform infrastructure.

**Platform / Support Engineer**
Needs consistent observability, well-defined alerting, and a predictable support model across all integrations.

### Secondary Personas

**Technical Lead / Architect**
Needs confidence that integrations meet platform and security expectations without reviewing every implementation detail.

**Domain Product Manager**
Cares about delivery speed and reliability; integration internals are not their concern.

---

## 6. User Needs & Key Use Cases

| # | Use Case |
|---|---|
| 1 | Create a new integration service from a standard scaffold |
| 2 | Deploy to managed runtime environments via a pre-configured CI/CD pipeline |
| 3 | Observe and support integrations using standard dashboards and alerts |
| 4 | Extend integrations with reusable components (e.g. messaging, data stores, storage) |
| 5 | Onboard a new team with minimal manual platform intervention |

---

## 7. Functional Requirements

### 7.1 Service Scaffolding

- Pre-built integration microservice templates.
- Standard project structure and configuration with opinionated defaults.
- Clear extension points for domain-specific customisation.

### 7.2 CI/CD Pipelines

- Built-in pipelines covering build, test, and deploy stages.
- Integrated code quality, security, and policy checks.
- Consistent release and upgrade management across all integrations.

### 7.3 Observability

- Standard logging, metrics, and distributed tracing out of the box.
- Pre-built dashboards and baseline alert configurations.
- GitOps-managed observability assets with domain-level layering support.

### 7.4 Security & Compliance

- Centralised secrets management by default.
- Standard identity and access patterns.
- Security requirements handled at the platform layer, not per team.

### 7.5 Reusable Components

- Common, pre-built integration components available to all teams.
- Continuous pattern harvesting from real integration implementations.
- Clear ownership model: the platform provides components; teams own usage and business logic.

---

## 8. Non-Functional Requirements

| Category | Requirement |
|---|---|
| **Reliability** | Suitable for Tier-1 production workloads |
| **Performance** | Must support high-volume batch and streaming use cases |
| **Scalability** | Horizontal scaling managed by the runtime platform |
| **Support** | 24/7 Tier-1 support model for production integrations |
| **Compatibility** | Deployed within approved enterprise runtime environments |

---

## 9. Ownership & Operating Model

### Platform Team Owns
- Build Kit templates, pipelines, and reusable components.
- Platform documentation and onboarding experience.
- Standard observability tooling, support processes, and runbooks.

### Domain Teams Own
- Business logic and data transformation.
- Runtime configuration and integration-specific alerting.
- Ongoing evolution and maintenance of their integrations.

---

## 10. Out of Scope

The following have been explicitly descoped:

- Exactly-once or two-phase commit delivery guarantees.
- Wholesale support for alternative runtimes without a demonstrated platform need.
- Full no-code integration authoring.

---

## 11. Risks & Mitigations

| Risk | Mitigation |
|---|---|
| Teams misinterpret platform vs domain responsibilities | Clear "what Build Kits are / are not" messaging embedded in onboarding |
| Over-customisation requests dilute the standard | Apply an 80/20 rule and pattern-led decision model |
| Poor first-time developer experience reduces adoption | Invest in onboarding automation and high-quality documentation |
| Platform expectation creep broadens scope unsustainably | Roadmap discipline and explicit, maintained non-goals |

---

## 12. Open Questions

- [ ] Which reusable components should be prioritised in the next iteration?
- [ ] How far should onboarding be automated vs guided/assisted?
- [ ] Which metrics most effectively demonstrate ROI to senior leadership?
