# Architecture

## Product context
Tap & Order Africa is a Ghana-focused multi-vertical super-app. Platform Core is the reusable foundation; Mobility is the first production domain. The first controlled pilot is Kasoa -> Accra. Future verticals are documented as extension points only and are not implemented in the Mobility MVP.

## Non-negotiable rules
- Mobile and web clients use versioned APIs and never access the database directly.
- Payment status, booking confirmation, seat availability, driver verification and trip state are server-authoritative.
- External providers are accessed through adapters.
- Users may hold multiple roles.
- Organization-scoped operational data is tenant-isolated.
- Critical booking and payment commands are idempotent.
- Important state transitions are explicit and auditable.
- Location exposure is minimized to journey-relevant data.
- Offline clients may queue safe operational updates, but never create financial truth.


## System shape
Start as a modular monolith with strict boundaries:
- Platform Core: identity, auth, profiles, organizations, payments, wallet-ready primitives, notifications, messaging, location/maps, search, reviews/support, permissions, feature flags, analytics and audit.
- Mobility: routes, stops, operators, vehicles, drivers, schedules, trips, seats, bookings, live tracking and manifests.
- Future domains: Marketplace, Delivery, Energy/Gas, Services, Property, Tickets and others.

Passenger and driver apps plus operator/admin web clients call the API/application layer. Application services orchestrate domain logic and repositories. PostgreSQL is the transactional system of record. Asynchronous jobs/events handle side effects such as notifications and analytics.
