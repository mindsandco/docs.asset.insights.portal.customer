# Architecture and cloud-native

You do not need to read this page to get value from Asset Insights Portal. It is here for the technical and security teams who want to understand what runs underneath, and to show that the platform is built on solid, modern foundations.

## Three tiers, from the field to the user

Asset Insights Portal is organized as three tiers, following the path data takes from an asset to the people and systems that use it.

| Tier | What it does |
|------|--------------|
| **Field gateway (edge)** | Connects to assets on site over industrial and IoT protocols, harmonizes their data at the edge, and pushes signed packages to the central platform over outbound HTTPS only. |
| **Central data management** | Receives data, harmonizes it into a versioned canonical model, applies transformation and validation rules, and distributes it through an event-driven pipeline to downstream services and consumers. |
| **Management portal** | The web application and APIs where people and systems administer the installation and access harmonized data. |

The data path in practice: a field gateway sends signed data to the ingest service, which publishes it onto the event bus. A worker harmonizes it into the canonical model and republishes it, and downstream services for notifications, uptime, and the management portal consume it from there.

![Asset Insights Portal data flow: edge assets push signed telemetry through the field gateway to ingest, onto the event bus, through the harmonizing worker, and out to downstream services, while management provisions the credentials and certificates the edge relies on](assets/architecture-flow.svg ':size=100%')

*Data flows left to right: assets to gateway to ingest to the event bus, harmonized by the worker, then out to notifications, uptime, and the management portal. Management runs the control plane in the other direction, provisioning the client credentials, certificates, and registry the edge signs and pushes with.*

## Built cloud-native from the ground up

The platform follows cloud-native fundamentals as defined by the Cloud Native Computing Foundation. In practice that means it is designed to run reliably in the cloud, scale with demand, and evolve safely over time.

- **Containers.** Every service is packaged in a container, so it runs the same way in every environment.
- **Orchestration.** Services run on Kubernetes, which handles scaling, healing, and rolling updates without downtime.
- **Microservices.** The platform is composed of focused, independently deployable services, so one part can grow or change without disrupting the rest.
- **Declarative APIs.** Services communicate through clear, versioned APIs and an event bus, which keeps the system predictable and easy to integrate with.
- **GitOps delivery.** Deployments are defined as code and applied automatically, so releases are repeatable and configuration stays in sync with what is running.

## The technology underneath

The platform is built on a modern, well-supported stack.

- **Services.** .NET services, each with a single responsibility, communicating through Dapr for pub/sub, state, secrets, and scheduled jobs.
- **Event bus.** Publish and subscribe messaging over a pluggable broker, so services stay decoupled and the pipeline scales.
- **Management portal.** A React web application backed by an API that serves GraphQL as its primary interface and REST where it fits.
- **Data.** A relational database for the management model, with an event-sourced write model so every change is captured as a recorded event.
- **Identity.** Keycloak for authentication and authorization, supporting single sign-on, named roles, fine-grained permissions, and invited-user onboarding.

## Bridging operational and information technology

The platform is built to connect the operational technology on the plant floor with the information technology of the enterprise. Field gateways speak the protocols that industrial equipment uses, and the central platform presents that data through the standard APIs that enterprise systems expect. This lowers integration cost and avoids locking you into any single vendor.

## Security and trust by design

- **Egress-only edge.** Field gateways open outbound connections only, with no inbound ports, in line with IEC 62443 and NIST SP 800-82 guidance.
- **Signed data.** Every payload is cryptographically signed at the gateway and verified centrally.
- **Strong identity.** User access uses single sign-on and role-based permissions, and services authenticate to each other separately from user identity.
- **Encryption.** Data is encrypted in transit.
- **Secrets management.** Credentials and certificates are managed centrally and can be rotated and revoked.

## Reliable to operate

- **Elastic scaling.** Capacity grows and shrinks with demand, so performance holds up as your data volume and user count increase.
- **Observability.** Every service emits traces, metrics, and structured logs through OpenTelemetry to a standard monitoring stack, giving operators clear visibility.
- **Resilience.** Edge buffering means no data is lost when a site loses connectivity, and services are designed to recover automatically.
- **Health tracking.** The platform monitors the health of its own services so operators know it is running.

## Runs where you need it

Because the platform is container-based and defined as code, it runs on the major public clouds and on-premise, including environments with data residency requirements. The architecture stays the same wherever it runs.

Next: [get in touch](get-in-touch.md).
