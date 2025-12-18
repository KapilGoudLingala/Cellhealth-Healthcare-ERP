# System Architecture

The CellHealth Healthcare ERP Platform is built on the **Frappe Framework**, with
**ERPNext Healthcare** serving as the foundational domain layer. The system follows
a **workflow-centric architecture**, where a single clinical document orchestrates
all operational activities.

---

## Architectural Overview

The architecture is designed around a **centralized patient visit model**, ensuring
that all departments work on a unified and consistent data source throughout the
patient lifecycle.

At the core of the system lies the **Patient Encounter**, which acts as the
authoritative document controlling clinical, diagnostic, billing, and fulfillment
processes.

---

## Core System Components

### 1. Patient Appointment
- Entry point of the system
- Manages patient scheduling and availability
- Initiates the Patient Encounter upon patient arrival

### 2. Patient Encounter (Core Workflow Controller)
- Serves as the **single source of truth** for a patient visit
- Controls the complete workflow using defined states and transitions
- Links all clinical and operational activities to one encounter

### 3. Laboratory Management
- Lab Test Templates define test structures
- Service Requests track pending lab work
- Lab Test documents store diagnostic results
- Integrated with workflow for controlled progression

### 4. Billing & Payments
- Sales Invoice manages billing for lab tests, medicines, and supplements
- Payment Entry records patient payments
- Billing is strictly driven by prescriptions to prevent discrepancies

### 5. Pharmacy Management
- Medication Requests capture prescribed medicines
- Pharmacy fulfillment is quantity-controlled and workflow-dependent
- Dispensing is linked back to the Patient Encounter

### 6. Nutrition Management
- Nutrition Assessment records BMI, lifestyle, and dietary habits
- Diet planning is finalized post senior doctor review
- Integrated seamlessly into the encounter workflow

---

## Architecture Principles

### Single Source of Truth
All departments interact with the same **Patient Encounter** document, eliminating
data duplication and inconsistencies.

### Workflow-Controlled Transitions
State changes are governed by the Frappe Workflow Engine, ensuring:
- No unauthorized progression
- No skipped clinical steps
- Full traceability of actions

### Role-Based Access Control
Each department has access only to:
- Relevant fields
- Permitted actions
- Assigned workflow states

### Audit-Friendly Design
- Every workflow transition is logged
- All clinical and billing actions are traceable
- Supports compliance and operational audits

---

## Architectural Benefits

- Improved inter-department coordination
- Reduced manual errors
- Enforced clinical and billing accuracy
- Scalable and maintainable system design
