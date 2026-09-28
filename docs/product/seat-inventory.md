# Seat Inventory

Availability is segment-based. A physical seat can be reused after a passenger leaves. Do not store a single mutable available_seats counter as truth. Prevent overlapping concurrent allocations transactionally.