# 01 · Scope & Context

> Northwind Health is a **fictional** company created for this portfolio project.

## The Organization

| | |
|---|---|
| **Company** | Northwind Health, Inc. |
| **Industry** | Healthcare SaaS (patient scheduling and reminders) |
| **Size** | ~120 employees, remote-first, HQ in Austin, TX |
| **Customers** | ~400 outpatient clinics across the US |
| **Data held** | ePHI for ~1.2 million patients: names, dates of birth, contact details, appointment history, insurance details, visit reasons |
| **HIPAA role** | Business Associate to its clinic customers (Covered Entities) |
| **Hosting** | AWS (single production region), Google Workspace for staff |

## Why This Assessment Matters

- **HIPAA Security Rule** requires Northwind to conduct a risk analysis and implement risk management measures (§164.308(a)(1)(ii)(A)–(B)).
- **Customers are asking for SOC 2.** Three enterprise clinic groups have made a SOC 2 Type II report a condition of renewal.
- **Board visibility.** The board has asked for a clear view of the top cyber risks and the investment needed to reduce them.

## Scope

**In scope**
- Production patient scheduling platform (web and mobile)
- AWS production environment, including the patient database and document storage
- Workforce identity (SSO, email, endpoints)
- Third parties that store, process, or transmit ePHI

**Out of scope**
- Marketing website (no ePHI)
- Internal finance and HR systems (assessed separately)
- Physical security of customer clinics

## Assumptions

- Assessment based on documentation review and stakeholder interviews (simulated for this project)
- Point-in-time assessment as of **September 2026**
- No penetration testing performed; technical findings are based on configuration review

## Stakeholders Interviewed

| Role | Area |
|---|---|
| CTO | Architecture, cloud, engineering practices |
| IT Manager | Endpoints, identity, onboarding/offboarding |
| Compliance Manager | HIPAA, vendor contracts, policies |
| Customer Success Lead | Customer data requests, vendor usage |
