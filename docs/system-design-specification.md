# System Design Specification: Procurement Digitization

## 1. Executive Summary
This document outlines the technical architecture for the transformation of the manual procurement process into a digital, automated system. The goal is to enforce data integrity, provide real-time tracking, and reduce human error in asset distribution.

## 2. Problem Statement
The legacy process relied on manual email chains and Excel trackers, leading to:
- **Data Silos:** Information was scattered across individual inboxes.
- **Latency:** Approval cycles took 3-5 business days due to manual follow-ups.
- **Lack of Audit Trail:** Difficulty in tracking who authorized high-value asset movements.

## 3. Proposed Solution Architecture
The solution is built on the **Microsoft Power Platform** using a "Low-Code/No-Code" architecture to ensure rapid deployment and easy maintenance.

### 3.1 Data Schema (SharePoint Online)
I designed a relational data structure using SharePoint Lists as the primary data source:
- **Main List:** `ProcurementRequests`
  - `Title` (Single line of text) - Unique Request ID
  - `Requester` (Person/Group) - Lookup to Office 365 Users
  - `AssetCategory` (Choice) - Hardware, Software, Services
  - `EstimatedCost` (Currency) - Used for conditional logic
  - `ApprovalStatus` (Choice) - Pending, Approved, Rejected, More Info Required
  - `TargetDate` (Date) - Delivery deadline

### 3.2 Logic & Workflow (Power Automate)
The automation engine follows a **Conditional Approval Pattern**:
1. **Trigger:** On item creation in `ProcurementRequests`.
2. **Logic Gate:** - If `EstimatedCost > 5000 PLN`: Route to **Senior Management**.
   - If `EstimatedCost <= 5000 PLN`: Route to **Department Lead**.
3. **Escalation:** If no response within 48 hours, a reminder notification is sent via **Microsoft Teams**.

## 4. Security & Governance
- **Role-Based Access Control (RBAC):** Users can only view their own requests via Power Apps "User()" filtering.
- **Data Validation:** Power Apps "DisplayMode" logic ensures that costs cannot be negative and required fields cannot be left blank.

## 5. Future Scalability (DevOps Roadmap)
To bring this system to enterprise standards:
- **ALM:** Exporting the solution to **GitHub** for versioning of the JSON/XML source files.
- **Environments:** Moving from a "Default" environment to a dedicated "UAT" (User Acceptance Testing) environment.
