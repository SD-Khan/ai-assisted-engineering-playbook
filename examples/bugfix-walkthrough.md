# Bugfix Walkthrough (Sanitized)

This walkthrough demonstrates the **Agentic Software Engineering Framework** bugfix loop:

**Observe → Reproduce → Scope → Root Cause → Fix → Regression Test → Verify → Document**

> Note: This is intentionally sanitized. Names, identifiers, and domain entities are generic.

---

## 1) Bug Summary

**Title:** Duplicate processing causes double writes under retry conditions

**Expected behavior**
- A request should be processed exactly once.
- Retries should not create duplicate records.

**Actual behavior**
- Under intermittent network failures and automatic retries, the system creates duplicates.

**Impact**
- Data integrity risk
- Downstream workflows can break (e.g., billing, allocation, reporting)

**Severity:** High

---

## 2) Reproduction

**Minimal reproduction**
1. Trigger an endpoint that performs a write (create/update).
2. Introduce a timeout or simulate a transient failure between request and response.
3. Client retries automatically (or user retries manually).
4. Observe duplicate records.

**Signals / evidence**
- Two records with same logical identifiers created within seconds.
- Logs show the same operation executed more than once.

---

## 3) Root Cause (Evidence-driven)

**Finding**
- The system treats retries as new requests because the write operation is not idempotent.

**Root cause**
- Missing idempotency enforcement for write endpoints.
- No uniqueness constraint on the logical “operation key”.

**Contributing factors**
- Retries occur during timeouts or 5xx responses.
- The handler executes the full write path before the client receives confirmation.

---

## 4) Fix Options

### Option A — Add Idempotency-Key (Preferred)
- Require `Idempotency-Key` for write endpoints.
- Store idempotency records and return the first result if key repeats.

**Pros:** correct, scalable, standard approach  
**Cons:** needs storage + handler logic  

---

### Option B — Add DB Uniqueness Constraint (Partial)
- Add a unique index for the logical operation key.
- If duplicate happens, DB rejects.

**Pros:** simple, strong integrity  
**Cons:** doesn’t return the same response body automatically

---

### Option C — Full Workflow Refactor (Not required)
- Introduce an outbox/eventing mechanism with exactly-once semantics.

**Pros:** ideal for large distributed systems  
**Cons:** overkill for a bugfix

---

## 5) Chosen Fix (Option A + partial Option B)

Implement:
- Application-level idempotency using `Idempotency-Key`
- DB-level safety net with a unique constraint on the idempotency key scope

This gives:
- Correct behavior for retries
- Strong integrity at the database layer

---

## 6) Implementation Plan (Sanitized)

### Data model
- Add `idempotency_record` table (or equivalent)
  - `key`
  - `scope`
  - `request_hash`
  - `response_body`
  - `status`
  - timestamps

### API behavior
- On request:
  1. Validate `Idempotency-Key`
  2. Lookup record by `(scope, key)`
  3. If exists and completed → return stored response
  4. If exists and in-progress → return conflict / retry-after
  5. Else create record → execute operation → store response

### Logging / audit
- Log idempotency hits and replays
- Record correlation ids for traceability

---

## 7) Regression Test Plan

### Unit test
- Same idempotency key returns same response and does not create duplicates.

### Integration test
- Simulate timeout/retry scenario:
  1. First request succeeds but client “times out”
  2. Second request replays with same `Idempotency-Key`
  3. Assert only one record exists

### Negative test
- Same key with different payload → reject with conflict

---

## 8) Verification Steps

- Run unit and integration tests
- Manually test:
  - send request with idempotency key
  - resend same request
  - ensure response is consistent
  - ensure no duplicate data created

---

## 9) Notes / Follow-ups

- Apply idempotency consistently across all write endpoints.
- For high-scale systems, consider adding a background outbox/eventing layer later.