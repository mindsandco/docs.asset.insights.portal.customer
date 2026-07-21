# Features

Every feature below exists to serve one goal: getting trusted, standardized asset data from the field into the hands of the people and systems that need it. They are grouped by the job they do.

## Connect your assets

### Field gateway and edge connectors
Connect assets over the industrial and IoT protocols they already speak, including OPC UA, MQTT, and Bluetooth, as well as file-based sources. Connectors are built on a shared software development kit, so bringing a new source online means writing the protocol-specific part and letting the platform handle the rest.

### Reliable delivery from the edge
Gateways buffer data locally and only mark it as sent once the central platform confirms receipt, with automatic retry and backoff. If a site loses connectivity, no data is lost. It is delivered when the link returns.

### Egress-only by design
Field gateways open outbound connections only. They run no inbound network ports and expose no remote control channel, which keeps industrial sites protected. This approach aligns with IEC 62443 and NIST SP 800-82 guidance for industrial control system security.

### Signed data integrity
Every payload is cryptographically signed at the gateway and verified centrally, and each gateway authenticates with its own short-lived credentials. You can trust that the data arriving at the center is genuine and unaltered.

## Turn raw data into trusted data

### Automatic harmonization
Telemetry from different vendors, sites, and generations of equipment is normalized into one versioned canonical model. Data that used to arrive in many incompatible formats lines up in a consistent shape that every consumer can rely on.

### Rule-based transformation and validation
A rule engine applies transformations and quality checks as data flows through: unit conversions, range validation, derived metrics, and event detection. The result is clean, consistent, trustworthy data rather than raw readings someone has to interpret by hand.

### Event-driven pipeline
Data moves through the platform as events, so information flows through as it arrives rather than waiting for a batch cycle. The pipeline scales with volume and keeps services decoupled and resilient.

## Access and administer

### Management portal
A single administrative surface for the whole installation: clients and applications, users, roles, assets, fields, gateways, dynamic properties, certificates and secrets, scheduled jobs, and extensions. Built as a modern web application that operators and administrators can use directly.

### GraphQL and REST APIs
Harmonized data and administration are exposed through a documented GraphQL API, with REST where it fits. Consuming systems such as analytics platforms, ERP, and SCADA query the data they need, and a published API kit makes integration straightforward.

### Role-based access and single sign-on
Access is controlled through your identity provider using named roles and fine-grained permissions, so people see and do only what their role allows. Invited users are onboarded through a simple secure sign-in link.

### White-label branding
Each tenant can apply its own company name, logo, favicon, background, and theme, applied to both the portal and the sign-in experience, so the platform can carry your brand or your customer's.

### Extensions marketplace
Extend the platform with integrations and add-ons through a built-in marketplace, so new capabilities can be added without rebuilding the core.

## Operate with confidence

### Notifications
Templated notifications are dispatched automatically when something needs attention, such as an alarm from the field, so the right people are informed through the right channel.

### Uptime and health monitoring
The platform tracks the health of its own services continuously, so operators know the system is running and can act quickly if something needs attention.

### Observability built in
Every service emits traces, metrics, and structured logs through OpenTelemetry to a standard monitoring stack, so operators have clear visibility into how the platform is behaving.

## Deploy anywhere

### Vendor-agnostic, Kubernetes-first
The platform is container-based and runs on Kubernetes, on Azure, AWS, or on-premise. Delivery is automated through GitOps, so the same platform runs wherever your data needs to live, including environments with data residency requirements.

Next: [architecture and cloud-native](architecture.md).
