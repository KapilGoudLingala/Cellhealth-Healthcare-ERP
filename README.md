# CellHealth – Healthcare ERP Platform

## Overview
CellHealth is a production-grade Healthcare ERP platform built on the **Frappe Framework** and **ERPNext Healthcare**, implemented for a live Cell Health Clinic.

The platform manages the **complete patient lifecycle** through a tightly controlled,
role-based workflow spanning reception, counselling, doctors, laboratory, billing,
pharmacy, and nutrition departments.

This repository documents the **system architecture, workflows, functional portals,
and core business logic** of the implementation.

> ⚠️ **Note:** Source code is not included due to client access restrictions and
patient data privacy requirements.

---

## Key Objectives
- Standardize patient movement across all clinical and operational departments
- Eliminate billing and prescription mismatches through workflow enforcement
- Enable longitudinal analysis of laboratory results across patient visits
- Establish accountability using role-based workflow approvals
- Improve operational efficiency and clinical coordination

---

## Technology Stack
- **Framework:** Frappe Framework
- **Healthcare Platform:** ERPNext Healthcare
- **Languages:** Python, JavaScript
- **Database:** MariaDB
- **Workflow Engine:** Frappe Workflow
- **Reporting:** Script Reports, Query Reports

---

## Core Workflow
The **Patient Encounter** document functions as the backbone of the platform,
orchestrating the complete clinical and operational journey of a patient.

Each encounter progresses through **18+ controlled workflow states**, ensuring that:
- No clinical or billing step is skipped
- All actions are role-restricted
- Transitions are auditable and approval-based

---

## Author
**Kapil Goud Lingala**  
Python Developer | Frappe & ERPNext Consultant  
Healthcare ERP Implementation Specialist

---

## License
MIT License
