# Product Requirements

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


## Mobility MVP
Passenger:
- registration/login and profile
- route search and designated stops
- scheduled trips
- next-day booking
- same-day live booking
- segment-aware seat availability
- booking, payment and confirmation
- live vehicle tracking and ETA
- notifications, trip history, cancellation and support

Driver:
- registration and verification workflow
- assigned vehicle
- scheduled trips and passenger manifest
- start trip, GPS, upcoming stops and pickups
- trip completion

Operator:
- organization, vehicles, drivers, routes and schedules
- bookings, revenue and basic analytics

Admin:
- users, operators, drivers, vehicles, routes, stops, trips, bookings, payments, verification and support

## Non-MVP
Nationwide rollout, Marketplace, Delivery, Energy/Gas, full wallet, social auth and other future verticals.

## Success metrics
Active vehicles/drivers/operators, daily bookings, advance bookings, live bookings, conversion, payment success, utilization, occupancy, wait time, on-time departure, cancellations, no-shows, trip completion, repeat passengers, complaints, driver adoption and operator retention.
