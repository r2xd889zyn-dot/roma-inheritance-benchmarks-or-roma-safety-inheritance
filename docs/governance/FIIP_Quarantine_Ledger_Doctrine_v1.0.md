# Millings Method OS™  
## Formal Information Ingestion Protocol (FIIP)  
### Quarantine Ledger Doctrine — v1.0 (Canonical)

**Status:** SEALED  
**Scope:** FIIP Stage 2–4  
**Last Updated:** 2026-01-04  
**System:** Millings Method OS™

---

## Purpose

The Quarantine Ledger is a governance-critical component of the  
**Formal Information Ingestion Protocol (FIIP)**.

Its purpose is to ensure that information entering the system is:
- isolated before evaluation,
- traceable without influence,
- rejected by default,
- and only advanced through explicit, constrained verification.

> **Nothing is learned until it survives rejection.**

---

## Governing Principles

1. **Minimalism**  
   Only essential fields are recorded to prevent semantic drift and cognitive bloat.

2. **Security**  
   Cryptographic hashing ensures tamper evidence.  
   No executable content is permitted in snapshots.

3. **Scalability**  
   The ledger supports future extensions (e.g., rate limits) without redesign.

4. **Interoperability**  
   Field definitions align with later FIIP stages to preserve continuity.

5. **Rejection Bias**  
   Entries auto-reject after expiry unless explicitly advanced.

6. **Privacy & Compliance**  
   No sensitive data is stored. Snapshots must be sanitized.

---

## Position in FIIP

The Quarantine Ledger operates at:

- **Stage 2 — Quarantine Buffer**
- Referenced by **Stage 3 — Constraint Filter**
- Verified by **Stage 4 — Recursive Verification**

The ledger **records** inputs but does not:
- influence reasoning,
- alter heuristics,
- or affect system behavior.

Memory ≠ Integration.

---

## Ledger Structure

### Global Header

- `ledger_version`
- `creation_timestamp` (ISO 8601)
- `system_id`
- `rolling_hash`

---

### Entry Fields

| Field | Description |
|------|-------------|
| Entry_ID | Unique, immutable identifier |
| Timestamp | ISO 8601 UTC timestamp |
| Source | Origin of the input |
| Input_Snapshot | Safe, representational text snapshot |
| Input_Hash | Cryptographic hash of full input |
| Metadata | Non-evaluative context only |
| Quarantine_Status | Pending / Rejected / Escalated |
| Expiry_Timestamp | Auto-rejection deadline |
| Previous_Entry_Hash | Hash chain pointer |
| Entry_Hash | Self-hash for verification |

**Rules:**
- Append-only
- No overwrites
- Status changes logged as new records

---

## Stage 3 — Constraint Filter (Summary)

Each entry is evaluated against:

1. Authorship Constraint  
2. Continuity Constraint  
3. Proof Constraint  
4. Governance Constraint  
5. Recursion Constraint  

Failure of **any** constraint results in rejection.

---

## Stage 4 — Verification Criteria (Canonical)

### Objective
Verify that the system:
- preserves isolation,
- enforces rejection by default,
- resists pressure to integrate aligned content,
- and maintains auditability.

### Accepted Outcomes

- **Verified-Rejected (Healthy Failure)**  
- **Verified (Eligible for Sealing)**  
- **Verification Failed**

> Rejection via expiry is a successful verification outcome.

---

## Documented Expiry Event (Reference Case)

**Entry:** QL-20260103-003  
**Outcome:** Verified-Rejected  
**Cause:** Expiry without intervention  
**Significance:** Confirms rejection bias and system health

---

## Canonical Doctrine Statements

- Rejection is success.
- Inaction is governance.
- Alignment is not proof.
- Memory does not imply acceptance.
- Verification evaluates behavior, not content quality.

---

## Versioning & Amendments

This doctrine is **canonical v1.0**.

Amendments require:
- explicit authorship,
- documented rationale,
- and a higher-order governance decision.

---

**End of Doctrine**
