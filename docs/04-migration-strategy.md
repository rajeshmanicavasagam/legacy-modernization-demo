# Migration Strategy

## Context
The legacy system is business-critical and cannot tolerate long downtime or high regression risk.  
A full rewrite was deliberately avoided due to cost, risk, and long time-to-value.

The chosen approach focuses on **incremental modernization** while keeping the system operational.

---

## Chosen Approach: Strangler Fig Pattern

The modernization follows the **Strangler Fig Pattern**, where new functionality is gradually extracted and implemented alongside the existing system.

Instead of replacing the system in one step, functionality is migrated **domain by domain**.

---

## Step-by-Step Strategy

### 1. Domain Identification
- Identify stable vs frequently changing areas
- Prioritize high-change, high-value domains
- Define clear bounded contexts

### 2. API Façade Introduction
- Introduce a service layer in front of legacy logic
- Standardize contracts using REST APIs
- Reduce direct database coupling

### 3. Incremental Extraction
- Extract one bounded context at a time
- Implement new functionality in modern ASP.NET Core services
- Route requests selectively to legacy or modern components

### 4. Parallel Run
- Run legacy and modern components side by side
- Compare behavior and data consistency
- Gradually increase traffic to modern services

### 5. Decommissioning
- Retire legacy modules once stability is proven
- Remove unused database tables and dependencies
- Simplify overall system architecture

---

## Why This Strategy Works

- **Risk is controlled**: No big-bang rewrite
- **Business continuity**: System remains operational
- **Incremental learning**: Teams adopt modern practices gradually
- **Faster value delivery**: New features delivered earlier

---

## When This Strategy Is Not Suitable

- Systems with no active users
- Very small applications with minimal risk
- Short-lived or disposable systems

In those cases, a full rewrite may be more efficient.

---

## Conclusion
Incremental modernization balances technical improvement with business reality.  
This approach reflects how modernization is successfully executed in large enterprise environments.
