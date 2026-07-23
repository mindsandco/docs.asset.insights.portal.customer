# Product tour

A look at the management portal in daily use. Every screen below is the live product, not a mockup.

## Dashboard

An at-a-glance overview of the whole installation: assets, gateways, users, and scheduled jobs, alongside platform health and asset status. Operators land here and immediately see whether anything needs attention.

![Management portal dashboard showing asset, gateway, user and job counts with platform health and status widgets](assets/screenshots/dashboard.png)

## Fields

Assets are grouped into fields. Each field rolls up its gateways and assets with online, offline, and disabled counts, so you can spot a struggling site before it becomes a problem.

![Fields list showing fields with gateway and asset online, offline and disabled counts](assets/screenshots/fields.png)

## Uptime and health

The platform continuously monitors the health of its own services. A 90-day history per service makes it easy to confirm the system is running and to see any past incidents at a glance.

![Uptime page showing per-service health with 90-day uptime history bars](assets/screenshots/uptime.png)

## Marketplace

Extend the platform with integrations and add-ons from a built-in marketplace, so new capabilities are added without rebuilding the core.

![Marketplace showing an installed application card](assets/screenshots/marketplace.png)

## Properties

Assets, fields, and gateways carry dynamic properties, so you can capture the details that matter to your operation without waiting for a code change. Add the fields your teams need and the platform stores them alongside the standard data.

![Dynamic properties page showing custom properties on assets, fields and gateways](assets/screenshots/properties.png)

## Branding

Make the portal your own. Set the company name, logo, favicon, background, and theme colors, and the look carries through the portal and the sign-in screen, so your teams work in a familiar environment from the first click.

![Branding page showing company name, logo, favicon and theme color settings](assets/screenshots/branding.png)

## Tours

Guided tours walk new users through the portal in context, so teams get productive faster without a separate training session.

## Jobs

Scheduled jobs run recurring work on a set cadence, so routine tasks happen on time without anyone remembering to trigger them.

![Jobs page showing scheduled jobs with their cadence and status](assets/screenshots/jobs.png)

## User administration

Manage the people who use the platform from one place: invite users, assign their roles, and control access as teams change. Sign-in and identity are handled through Keycloak.

![User administration page showing users with their assigned roles](assets/screenshots/users.png)

## Role administration

Named roles and fine-grained permissions decide who can see and change what, from portfolio-wide administrators to technicians and data consumers. Grant only the access each person needs, all enforced through Keycloak.

Next: [architecture and cloud-native](architecture.md).
