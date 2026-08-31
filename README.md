# HED Property & Tenant Management System — Premium Interactive Demo

A presentation-ready interactive prototype for **Honest Estate Developers Ltd**, designed and implemented as an AutoMinds Africa concept demonstration.

> **Important:** all tenants, amounts, transactions, leases, references and operational records in this repository are fictional demo data. This is not a production finance system.

## What this demo demonstrates

The prototype tells the full property-management story rather than showing static screens:

- HED-branded executive and role-specific dashboards
- 48-shop digital building register with occupied, vacant and reserved states
- Tenant CRM and guided onboarding
- Vacant shop → tenant → draft lease → lease activation → invoice workflow
- Lease lifecycle, escalation, renewals and amendments
- Tenant exit, deposit settlement and automatic return to vacancy register
- Recurring invoices, full payments and partial payments
- Payment allocation and simulated MTN/bank reconciliation queue
- Automatic receipt creation and simulated email delivery history
- Controlled payment reversal / void workflow
- Tenant account statement with running balance
- Arrears command centre with ageing and reminders
- Tenant communication centre across Portal, Email, SMS and future WhatsApp channels
- Broadcast announcements
- Maintenance tickets and completion workflow
- Management approval queue for sensitive actions
- Audit trail
- Reports and CSV rent-roll export
- Full tenant self-service portal with inbox, lease, statement, payment, receipt, document upload and maintenance request flows
- Role-based access restrictions
- Global search / command experience (`Ctrl + K`)
- Skeleton loading states and polished transitions
- Presentation mode and resettable browser-based demo state

## Demo accounts

All accounts use the demo-only password: **`HED@2026`**

| Role | Login |
|---|---|
| Super Administrator | `superadmin@hed.demo` |
| Managing Director | `director@hed.demo` |
| Property Manager | `manager@hed.demo` |
| Leasing Officer | `leasing@hed.demo` |
| Accounts Officer | `accounts@hed.demo` |
| Front Desk / Admin | `admin@hed.demo` |
| Maintenance Officer | `maintenance@hed.demo` |
| Tenant Portal | `tenant@hed.demo` |

The login screen also includes quick-login buttons for presentation convenience.

## Branding / logo

The interface uses HED-inspired blue, yellow, red, gold and charcoal tones.

For the final logo, place the official HED image in the repository root as:

```text
logo.png
```

The demo will automatically use it. If `logo.png` is missing, it will also try the existing `Logo.jpeg`, then fall back to an HED mark so the interface never breaks.

## Run locally

This version is intentionally a **zero-build static interactive prototype**. No database or package installation is required.

You can open `index.html` directly, or serve the folder locally:

```bash
python -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

It is also suitable for GitHub Pages or any basic static host.

## Recommended stakeholder demo sequence

1. Log in as **Managing Director** and show executive collections, occupancy, arrears and lease exposure.
2. Open **Shops & Units** and drill into a shop profile.
3. Register a new tenant and assign a vacant shop.
4. Open the generated draft lease and **Activate Lease & Billing**.
5. Switch to **Accounts Officer**, record a partial rent payment and show the automatically generated receipt.
6. Open the tenant statement and remaining arrears position.
7. Demonstrate payment reversal and audit history.
8. Open an expiring lease and run renewal / escalation.
9. Demonstrate tenant exit and deposit settlement returning the shop to vacancy.
10. Log in as the **Tenant** and demonstrate self-service payment, statement, HED inbox, document upload and maintenance request.
11. Log in as **Director** again and approve a controlled financial request.
12. Use `Ctrl + K` to search across tenants, shops, leases, invoices and receipts.

## Demo architecture

The prototype uses plain HTML/CSS/JavaScript with a modular feature structure and browser `localStorage` for presentation persistence. **Reset Demonstration Data** restores the curated seed state.

This choice makes the demo fast to launch and easy to present. The production system should later replace browser persistence with a secure API, PostgreSQL database, cloud document storage, transactional email and approved payment-provider integrations while preserving the demonstrated workflows and UI concepts.

## Main files

- `index.html` — application entry point
- `styles.css` — HED visual design system and responsive layout
- `data.js` — fictional seed data and demo state
- `core-base.js` — auth, role navigation, skeletons and application shell
- `dashboard.js` — executive/role dashboards
- `units.js` — digital building and shop profiles
- `tenants.js` — CRM and tenant onboarding
- `leases.js` — lease lifecycle, activation, renewal, amendments, exit/deposit settlement
- `invoices.js` — billing and invoice register
- `payments.js` — payments, reconciliation, partial payment and reversal
- `receipts.js` — receipt register and print/PDF view
- `statements.js` — account ledger
- `arrears.js` — ageing and reminder workflow
- `communications.js` — tenant messaging and announcements
- `maintenance.js` — work orders
- `approvals.js` — management approvals
- `reports.js` — analytics and exports
- `admin.js` — users/roles, audit and settings
- `tenant-portal.js` — tenant self-service experience
- `runtime.js` — search, notifications, presentation mode and startup

## Production note

This demo intentionally simulates external services such as MTN MoMo, Airtel Money, bank matching, email, SMS and WhatsApp. Production integrations require provider credentials, API/webhook security, idempotency, reconciliation controls, database-backed transactions, real authentication and security testing.

---

**AutoMinds Africa**  
Concept implementation for Honest Estate Developers Ltd.
