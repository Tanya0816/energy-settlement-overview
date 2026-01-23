# Pilot Demonstration Walkthrough

This document describes how the pilot demonstration works and
what it is intended to prove.

The demo is designed to be simple, observable, and repeatable,
without requiring an understanding of the underlying implementation.

---

## Purpose of the Demo

The goal of the demo is to demonstrate **post-settlement integrity**.

Specifically, it shows that:
- a settlement can be finalized
- the finalized data can be verified later
- any modification after finalization is detectable

The demo does not attempt to simulate real-time trading,
pricing, or payments.

---

## Demo Inputs

The demo uses structured monthly energy data in CSV format.

Each record represents:
- an entity (e.g., building, department, or organization)
- energy generated during the period
- energy consumed during the period
- the settlement period (e.g., YYYY-MM)

This format mirrors how energy data is commonly handled in
campus or facility environments.

---

## Demo Flow

### Step 1: Upload Energy Data

Monthly energy data is uploaded to the system.

At this stage:
- no settlement is finalized
- data can still be corrected or adjusted
- the system is preparing for reconciliation

---

### Step 2: Generate and Finalize Settlement

The settlement is generated for the given period.

This step:
- computes surplus and deficit across entities
- produces a settlement summary
- represents the point at which the settlement becomes final

A finance-readable settlement statement is produced for review
and record-keeping.

---

### Step 3: Verify Finalized Settlement (VALID)

After finalization, the system performs a verification check.

If the current settlement data matches the finalized version,
the verification result ,This indicates that:

- the data has not been altered since finalization
- the settlement remains consistent with the official record

---

### Step 4: Modify Data After Finalization

To demonstrate post-settlement tampering, the energy data
is modified after finalization.

This modification represents:
- a late adjustment
- an accidental change
- or an unauthorized edit

No re-finalization is performed at this stage.

---

### Step 5: Verify Modified Settlement (TAMPERED)

The verification process is run again.

Because the data no longer matches the finalized version,
This indicates that:

- the settlement data has changed
- the current data no longer matches the finalized record

---

## What the Demo Proves

This demonstration shows that:

- settlement finalization is explicit
- finalized data can be independently verified
- post-finalization changes are detectable
- verification does not rely on trust in the system operator

These properties are critical for environments where
energy settlements are treated as financial records.

---

## Interpretation of Results

- A `VALID` result does not imply correctness of the data,
  only consistency with the finalized version.
- A `TAMPERED` result does not imply malicious intent,
  only that the data differs from the finalized record.

This distinction mirrors real-world audit and reconciliation practices.

---

## Intended Audience

This demo is intended for:
- energy managers
- finance teams
- auditors and compliance reviewers
- stakeholders evaluating pilot feasibility

It is designed to support discussion and feedback.