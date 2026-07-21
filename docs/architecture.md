# Architecture and cloud-native

You do not need to read this page to get value from Asset Insights Portal. It is here for the technical and security teams who want to understand what runs underneath, and to show that the platform is built on solid, modern foundations.

## Built cloud-native from the ground up

Asset Insights Portal follows cloud-native fundamentals as defined by the Cloud Native Computing Foundation. In practice that means the platform is designed to run reliably in the cloud, scale with demand, and evolve safely over time.

- **Containers.** Every service is packaged in a container, so it runs the same way in every environment, from a developer laptop to production.
- **Orchestration.** Containers run on Kubernetes, which handles scaling, healing, and rolling updates without downtime.
- **Microservices.** The platform is composed of focused services that can be developed, deployed, and scaled independently, so one part can grow or change without disrupting the rest.
- **Declarative APIs.** Services talk to each other through clear, versioned APIs, which keeps the system predictable and easy to integrate with.
- **Immutable infrastructure.** Environments are defined as code and rebuilt rather than patched in place, which makes deployments repeatable and reduces configuration drift.

## How the pieces fit together

The platform is organized in layers, each with a clear job.

| Layer | What it does |
|-------|--------------|
| **Ingestion** | Connects to source systems, databases, files, and streaming feeds, and brings data in through connectors and open APIs. |
| **Data and asset model** | Maps incoming data onto a common asset model, runs quality checks, and maintains one trusted record per asset. |
| **Insight and analytics** | Powers dashboards, search, reporting, and AI-assisted insight, with lineage back to source. |
| **Action** | Runs alerts, notifications, and workflows, and integrates results back into operational systems. |
| **Experience** | The portal interface and APIs that people and applications use to work with everything above. |

Cutting across every layer are the platform foundations: identity and access, security, observability, and audit.

## Event-driven and API-first

The portal is API-first, so every capability is available through a documented interface, and event-driven, so changes in your data flow through the system as they happen rather than waiting for a batch cycle. Together this keeps the view current and makes the platform straightforward to integrate with the tools you already run.

## Security and trust by design

- **Access control.** Role-based access and single sign-on through your existing identity provider.
- **Encryption.** Data is encrypted in transit and at rest.
- **Isolation.** Workspaces and multi-tenancy keep each team's or business unit's data separated.
- **Auditability.** Actions are logged and data lineage is maintained, so the platform supports review and compliance.

## Reliable to operate

- **Elastic scaling.** Capacity grows and shrinks with demand, so performance holds up as your asset base and user count increase.
- **Observability.** Metrics, logs, and tracing give operators clear visibility into the health of the platform.
- **Automated delivery.** Continuous integration and delivery, with infrastructure as code, mean updates ship safely and often.
- **Resilience.** Services are designed to recover automatically, and the platform is built to keep running through the failure of any single component.

## Runs where you need it

Because the platform is container-based and defined as code, it can run on the major public clouds and in the environments your organization already trusts. The architecture stays the same wherever it runs.

Next: [get in touch](get-in-touch.md).
