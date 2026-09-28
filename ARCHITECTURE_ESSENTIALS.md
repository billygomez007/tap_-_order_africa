# Architecture Essentials

1. Platform Core remains independent of Mobility.
2. Mobility is a domain module, not the foundation.
3. Future verticals reuse Platform Core.
4. Clients never access the database directly.
5. Payment state is server-authoritative.
6. Seat availability is segment-aware and transactionally protected.
7. Booking/payment commands are idempotent.
8. Location access follows privacy rules.
9. Organization data is tenant-isolated.
10. Important state transitions are auditable.
11. External providers are behind adapters.
12. Provider-specific logic does not enter domain rules.
13. One user may hold multiple roles.
14. Future vertical functionality is excluded from the Mobility MVP unless explicitly approved.
15. Do not sacrifice architectural integrity for speed.
16. Bookings and trips use controlled state machines.
17. Directional routes are distinct.
18. Pickup uses designated stops, not arbitrary roadside points.
19. Offline behavior never overrides server financial truth.
20. Start modular; distribute only when justified.
