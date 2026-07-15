# Metadata-Driven Multi-Company ERP — Design Blueprint

**Role:** ERP Architect / Techno-Functional Consultant
**Context:** Custom ERP platform designed and documented during my tenure as Head of ERP at Automation Services Ltd (ASL), Dhaka
**Scope:** Full system design blueprint — database schema, screen design, and functional specifications across 8 core modules and 100+ transaction screens

---

## Overview

This project is a full architectural blueprint for a **modular, multi-company/multi-business ERP system**, designed to be configurable rather than hardcoded — new screens, menus, and access rules can be defined as data rather than requiring new code for every business unit onboarded.

The blueprint was produced end-to-end by me: requirement discovery, database schema design, screen/UI specification, and functional process documentation, intended as the build reference for the development team.

## Architecture Highlights

**Metadata-driven UI engine**
Rather than hardcoding each screen, the system defines menus, screens, and field-level attributes as configuration records (`Menu Master`, `Screen Master`, `Screen Attributes`). A single rendering engine reads this metadata to generate the UI, access controls, and validation — closer to a low-code platform pattern than a traditional fixed-form ERP.

**Granular privilege model**
Access control is resolved per user, per screen, per attribute (field-level permissions), rather than just per-module — supporting fine-grained approval and visibility rules across business units.

**Multi-company / multi-business core**
Every core table is scoped by a business/organization identifier, allowing the same schema and application layer to serve multiple legal entities or business units from one platform — the same pattern used in the multi-company Lira Group ERP rollout.

**Consistent module coding convention**
Every screen carries a functional code (e.g. `SA` = System Admin, `AD` = Administration, `MD` = Master Data, `FA` = Finance & Accounts, `PO` = Procurement, `SO` = Sales/CRM/POS, `IM` = Inventory, `PM` = Project Management), giving the whole platform a predictable, navigable structure for both developers and functional consultants.

## Module Coverage

| Module | Code Prefix | Coverage |
|---|---|---|
| System Administration | SA | Menu master, screen master, screen attributes, dynamic query windows |
| Administration | AD | User management, privilege/access profiles, codes & parameters, audit trail |
| Master Data | MD | Item, cost, supplier, customer, party, employee, bank, document masters |
| Finance & Accounts | FA | Chart of accounts, general/integrated/imported vouchers, AR/AP allocation, receivables & payables, GL interfaces from Purchase/Sales/Inventory/Manufacturing |
| Procurement | PO | Supplier quotation & analysis, purchase requisition/order, GRN, direct purchase, purchase return, service requisition, work order, quality certificate |
| Sales & CRM | SO | Sales quotation, requisition, order, invoice, direct sales, sales return, POS entry & card transactions, lead management, CRM quotation |
| Inventory | IM | Store requisition & approval, inter-business transfer, stock take/adjustment, damage/conversion entries, ~20 sub-ledger receive/issue interfaces per source module |
| Project Management | PM | Project/contract master, site master, tasks, budget entry, budget/expense transactions |

## Design Process

1. **Requirement discovery** — mapped business processes across finance, procurement, sales, inventory, and project operations
2. **Database schema design** — normalized core tables with clear primary/foreign key relationships and multi-business scoping
3. **View/query layer** — reusable view schema to support reporting and dashboards without duplicating business logic
4. **Screen design** — functional specification per screen: fields, validations, workflow states, and linked GL/inventory postings
5. **Process documentation** — end-to-end flows for login, screen rendering, report/dashboard rendering, search, and favorites

## Outcome

This blueprint became the reference architecture later adapted and extended for the Lira Group multi-company ERP rollout (6 sister concerns across manufacturing, distribution, and retail), demonstrating the design's reusability across different client environments.

---

*Note: This repository contains a high-level architectural summary only. Detailed table structures, field-level specifications, and screen mockups from the original client-facing document are not published here.*
