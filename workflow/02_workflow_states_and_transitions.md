# Workflow States & Transitions  
**Workflow Name:** Patient Encounter WF  
**Document Type:** Patient Encounter  
**Workflow State Field:** workflow_state  

This document defines all allowed workflow transitions for the Patient Encounter,
including permitted actions, next states, and approving roles.

All transitions are **explicit, role-controlled, and approval-based** to ensure
clinical accuracy, billing integrity, and operational accountability.

---

## Workflow Control Principles

- Transitions are triggered **only via defined actions**
- Each action is **restricted to a specific role**
- **Skipping workflow states is not allowed**
- Parallel clinical paths are supported (Lab before / after doctor)
- Self-approval is **disabled** for all transitions
- Every transition is auditable

---

## Workflow States & Transitions Matrix

| Sr | Current State | Action | Next State | Allowed Role |
|----|--------------|--------|------------|--------------|
| 1 | Pending With Backend | Send To Junior Doctor | Pending With Junior Doctor | Backend Workflow Approver |
| 2 | Pending With Junior Doctor | Send To Billing & Lab | Pending With Billing (Before Lab) | Junior Doctor Workflow Approver |
| 3 | Pending With Junior Doctor | Send To Nutritionist & Showing Testimonials | Pending With Nutritionist & Showing Testimonials | Junior Doctor Workflow Approver |
| 4 | Pending With Junior Doctor | Send To Sr. Doctor | Pending With Senior Doctor | Junior Doctor Workflow Approver |
| 5 | Pending With Billing (Before Lab) | Send To Lab | Pending With Laboratory | Billing Workflow Approver |
| 6 | Pending With Laboratory | Send To Nutritionist & Showing Testimonials | Pending With Nutritionist & Showing Testimonials | Lab Workflow Approver |
| 7 | Pending With Laboratory | Send To Junior Doctor | Pending With Junior Doctor | Lab Workflow Approver |
| 8 | Pending With Laboratory | Send To Sr. Doctor | Pending With Senior Doctor | Lab Workflow Approver |
| 9 | Pending With Nutritionist & Showing Testimonials | Send To Sr. Doctor | Pending With Senior Doctor | Nutritionist Workflow Approver |
| 10 | Pending With Nutritionist & Showing Testimonials | Send To Billing & Pharmacy | Pending With Billing (For Supplements/Medicines) | Nutritionist Workflow Approver |
| 11 | Pending With Senior Doctor | Send To Counsellor & Taking Testimonials | Pending With Counsellor & Taking Testimonials | Senior Doctor Workflow Approver |
| 12 | Pending With Senior Doctor | Send To Billing & Pharmacy | Pending With Billing (For Supplements/Medicines) | Senior Doctor Workflow Approver |
| 13 | Pending With Counsellor & Taking Testimonials | Send To Billing & Pharmacy | Pending With Billing (For Supplements/Medicines) | Nutritionist Workflow Approver |
| 14 | Pending With Billing (For Supplements/Medicines) | Send To Pharmacy | Pending With Pharmacy | Billing Workflow Approver |
| 15 | Pending With Pharmacy | Send To Nutritionist For Diet Plan | Pending With Nutritionist For Diet Plan | Pharmacy Workflow Approver |
| 16 | Pending With Nutritionist For Diet Plan | Complete | Completed | Nutritionist Workflow Approver |

---

## Key Design Outcomes

- Ensures **department-wise accountability**
- Prevents **unauthorized state transitions**
- Supports **real-world clinical flexibility**
- Maintains **billing and prescription integrity**
- Guarantees **end-to-end workflow completion**

---

## Final State

**Completed**  
This state indicates that:
- All clinical consultations are finished
- Billing and pharmacy processes are complete
- Diet plan is delivered
- Patient encounter is officially closed
