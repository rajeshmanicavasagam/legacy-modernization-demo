# Legacy Architecture – Before Modernization

## Overview
The legacy system is implemented as a **tightly coupled monolithic application**.
All responsibilities are concentrated in a single deployable unit.

---

## High-Level Architecture+-----------------------------+
| Web UI (MVC) |
+-------------+---------------+
|
v
+-----------------------------+
| Business Logic Layer |
| (Mixed Responsibilities) |
+-------------+---------------+
|
v
+-----------------------------+
| Data Access (Direct SQL) |
+-------------+---------------+
|
v
+-----------------------------+
| Shared Database |
+-----------------------------+


---

## Key Characteristics

- UI, business logic, and data access are tightly coupled
- Direct database access from multiple layers
- Shared schema across all domains
- Single deployment unit

---

## Challenges

- High regression risk when making changes
- Difficult to scale specific functionality
- Slow release cycles
- Limited testability
- Not cloud-ready

---

## Summary
This architecture was common and effective in the past, but it becomes a bottleneck
as systems grow in complexity and business change accelerates.


