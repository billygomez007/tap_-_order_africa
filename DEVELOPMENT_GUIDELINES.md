# Development Guidelines

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


Read architecture essentials before significant work. Update documentation with implementation. Use migrations for schema changes. Add tests for behavior changes. Keep changes small and reviewable. Do not bypass validation, authorization, idempotency or transactional seat rules for speed. Use feature flags for staged rollout.
