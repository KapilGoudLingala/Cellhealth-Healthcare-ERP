# Patient Encounter Workflow

**Workflow Name:** Patient Encounter WF  
**Document Type:** Patient Encounter  
**Workflow State Field:** workflow_state  

The Patient Encounter workflow governs the **entire clinical and operational lifecycle**
of a patient visit. Every department interacts with the same document, and progression
is strictly controlled through workflow states.

This ensures:
- Clear departmental responsibility
- No unauthorized edits
- No skipped clinical or billing steps
- Full auditability

---

## Workflow Edit Control Policy

- For all active workflow states, **document editing is restricted**
- Only users assigned through workflow roles can modify the encounter
- The **Completed** state is locked and read-only
- Workflow transitions are handled via explicit actions only

---

## Workflow States (Authoritative List)

| Sr | Workflow State | Doc Status | Editable |
|----|---------------|-----------|----------|
| 1 | Pending With Backend | 0 | Yes |
| 2 | Pending With Junior Doctor | 0 | Yes |
| 3 | Pending With Billing (Before Lab) | 0 | Yes |
| 4 | Pending With Laboratory | 0 | Yes |
| 5 | Pending With Nutritionist & Showing Testimonials | 0 | Yes |
| 6 | Pending With Senior Doctor | 0 | Yes |
| 7 | Pending With Counsellor & Taking Testimonials | 0 | Yes |
| 8 | Pending With Billing (For Supplements / Medicines) | 0 | Yes |
| 9 | Pending With Pharmacy | 0 | Yes |
| 10 | Pending With Nutritionist For Diet Plan | 0 | Yes |
| 11 | Completed | 1 | No |
| 12 | Pending with Sr. Dr | 0 | Yes |
| 13 | Pending with Counsellor | 0 | Yes |
| 14 | Pending with Doctor | 0 | Yes |
| 15 | Complete | 0 | Yes |

> **Note:**  
> States 12–15 exist to support **legacy, fallback, or transitional scenarios**
> and are retained to ensure backward compatibility and operational flexibility.

---

## Workflow Purpose by Phase

### Initial Consultation Phase
- Pending With Backend  
- Pending With Junior Doctor  

### Diagnostic & Review Phase
- Pending With Billing (Before Lab)  
- Pending With Laboratory  

### Counselling & Nutrition Phase
- Pending With Nutritionist & Showing Testimonials  
- Pending With Counsellor & Taking Testimonials  

### Senior Review Phase
- Pending With Senior Doctor  
- Pending with Sr. Dr  

### Billing & Fulfillment Phase
- Pending With Billing (For Supplements / Medicines)  
- Pending With Pharmacy  

### Diet Planning & Closure
- Pending With Nutritionist For Diet Plan  
- Completed  

---

## Final State: Completed

The **Completed** state indicates that:
- All consultations are finished
- Billing and pharmacy processes are complete
- Diet plan has been delivered
- The patient encounter is officially closed
- No further edits are allowed

This marks the **end of the patient visit lifecycle**.
