<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Rollcall-IT/.github/main/profile/assets/rollcall-logo-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Rollcall-IT/.github/main/profile/assets/rollcall-logo.svg">
    <img src="https://raw.githubusercontent.com/Rollcall-IT/.github/main/profile/assets/rollcall-logo.svg" alt="Rollcall" width="320">
  </picture>
</p>

<p align="center">
  <strong>Microsoft 365 onboarding, offboarding, and hybrid Active Directory administration in a few reviewed clicks.</strong>
</p>

<p align="center">
  <a href="https://rollcallit.com">Website</a> ·
  <a href="https://rollcallit.com/pricing">Pricing</a> ·
  <a href="https://docs.rollcallit.com">Documentation</a> ·
  <a href="https://rollcallit.com/security">Security</a> ·
  <a href="https://app.rollcallit.com/signup">Start 14-Day Trial</a>
</p>

---

## What is Rollcall?

**Rollcall** is a Microsoft 365 user-lifecycle and administration portal built to replace fragile PowerShell scripts and multi-console checklists with one calm, auditable workflow. From a single sign-in, technicians manage Microsoft Entra ID users, groups, licenses, Exchange Online mailboxes, Conditional Access policies, MFA settings, and hybrid on-premises Active Directory.

Rollcall is available in two editions built on the same open-core engine:

- **[Open-Rollcall (Community Edition)](https://github.com/Rollcall-IT/Open-Rollcall)** — Free, open-source (`AGPL-3.0-or-later`), self-hosted Docker Compose stack for a single Microsoft 365 tenant, installed with one command.
- **[Rollcall Cloud](https://app.rollcallit.com)** — Fully managed Azure SaaS for internal IT teams and multi-tenant Managed Service Providers (MSPs), adding four-eyes governance, Conditional Access safety rails, scheduling, white-label Welcome Packs, compliance audit exports, and multi-tenant MSP management.

---

## What Rollcall Does

### Preview → Approve → Run Workflow Engine
- **Frozen change previews:** Before making a single write, Rollcall calculates a live diff across Microsoft Graph, Exchange Online, and on-premises Active Directory, hashed with SHA-256.
- **Drift detection & step-level retry:** Live drift checks pause execution if tenant state changes before a run begins. Failed steps retry cleanly from the point of failure without leaving a half-finished account.
- **Tamper-evident audit log:** Every plan, approval, step result, and retry is written to an append-only, per-tenant SHA-256 hash-chained audit log.

### Standardized Onboarding & Offboarding
- **Versioned role templates:** Define once what each role receives—groups, licenses, attributes, and policies—and apply it consistently across every new hire with collision checking and optional scheduled activation.
- **Welcome Pack PDF:** Generates a structured handoff containing the new user's username, Temporary Access Pass (TAP) or one-time password, and first-sign-in steps (white-labeled on Pro and MSP Pro+).
- **Safety-ordered offboarding & one-click restore:** Blocks sign-in, revokes active sessions, resets credentials, removes MFA methods, and converts mailboxes to shared strictly *before* removing licenses. Supports timed OneDrive manager handover, hybrid AD disable/OU moves, and one-click user restore from recorded state.

### Everyday Microsoft 365 & Hybrid AD Management
- **Users, groups, licenses & MFA:** Live directory search, single and bulk attribute edits, Entra ID security/Microsoft 365 groups and Exchange Online distribution lists, license seat tracking (including flagging licenses on disabled accounts), MFA method review, single-view RAM-only Temporary Access Passes, and session revocation.
- **Conditional Access safety rails *(Pro / MSP Pro+)*:** Admin-only policy updates scoped strictly to `conditions.users`, hard-blocking removal of break-glass exclusions, requiring typed policy confirmation plus a second approver, and supporting timed temporary exclusions that revert automatically.
- **Hybrid Active Directory (`Rollcall.Agent`):** Open-source, outbound-only Windows service running under a gMSA with ECDSA P-256 JWT authentication, dual-layer OU allowlist enforcement, Entra Connect sync triggers, zero stored AD passwords, and zero inbound firewall ports.

### Security Architecture
- **Zero stored passwords or client secrets:** Technicians sign in with Microsoft Entra ID single sign-on so existing MFA and Conditional Access policies govern every session. Graph and Exchange Online authenticate exclusively with RSA 3072 X.509 certificates.
- **Defense-in-depth cloud isolation:** Rollcall Cloud isolates every workspace at both the application layer and the PostgreSQL Row-Level Security (RLS) layer, with AES-256-GCM envelope encryption backed by Azure Key Vault.
- **Offboarding safety invariant:** Billing state changes never abort an in-flight offboarding.

---

## Who Rollcall Is For

| Audience | How They Use Rollcall |
| --- | --- |
| **Internal IT Teams** *(1–20 people, cloud-only or hybrid)* | Replace manual M365 admin-center checklists and one-off scripts with repeatable role templates, four-eyes approvals, safe offboardings, and clear audit history—without enterprise IGA complexity or pricing. |
| **Managed Service Providers (MSPs)** | Manage onboarding, offboarding, and hybrid AD across every client Microsoft 365 tenant from one tab-safe portal (`/t/:tenantSlug`) with **unlimited MSP technicians**, an All-Clients overview, a cross-tenant shared role template library, per-client technician RBAC scoping, and client-ready CSV audit packs. |
| **Self-Hosting & Security-Focused Teams** | Run **Open-Rollcall Community Edition** on their own Linux server via Docker Compose and audit every line of the open-source core engine and Windows AD agent under `AGPL-3.0-or-later`. |

---

## Pricing Structure

Start with a **14-day cardless free trial** of **Pro** or **MSP Pro** on [Rollcall Cloud](https://app.rollcallit.com/signup), or self-host **Open-Rollcall Community Edition** free forever. Annual billing saves ~18%.

### Self-Hosted Open Source

| Plan | Price | Scope | Highlights |
| --- | --- | --- | --- |
| **Open-Rollcall Community Edition (CE)** | **Free forever** (`AGPL-3.0-or-later`) | 1 M365 tenant · Unlimited technicians | Self-hosted Docker Compose install, core onboarding & offboarding, role templates, users/groups/licenses/MFA, open-source Hybrid AD agent, and in-UI hash-chained audit logs (BYO Entra app registration). |

### Rollcall Cloud — Internal IT Teams *(Single-Tenant, Managed Azure SaaS)*

Billed per **Admin/Technician seat**. On **Pro** and **Enterprise**, **Approver-only and Viewer seats are free**.

| Plan | Monthly | Annual *(~18% off)* | Highlights |
| --- | --- | --- | --- |
| **Team** | $29 /seat/mo | **$24 /seat/mo** | Managed Azure hosting (1 M365 tenant), 1-click Entra consent & automatic certificate rotation, full onboarding/offboarding, role templates, Hybrid AD, 90-day audit retention, email support. |
| **Pro** *(Most Popular)* | $59 /seat/mo | **$49 /seat/mo** | Everything in Team, **free Approver & Viewer seats**, four-eyes approvals & custom approval rules, Conditional Access safety rails & timed exclusions, scheduled workflows & timed OneDrive reversals, white-label Welcome Pack PDF, 1-year audit retention + CSV export. |
| **Enterprise** | Custom | Custom *(ACH / wire / PO)* | Everything in Pro, BYO Entra App Registration option, 7-year audit retention, SIEM & signed webhook streaming, dedicated single-tenant Azure option & SLA. |

### Rollcall Cloud — Managed Service Providers *(Multi-Tenant, Managed Azure SaaS)*

Billed per **managed client Microsoft 365 tenant** (5-tenant minimum). **Unlimited MSP technicians** are included on every MSP plan.

| Plan | Monthly | Annual *(~18% off)* | Highlights |
| --- | --- | --- | --- |
| **MSP Core** | $19 /tenant/mo | **$16 /tenant/mo** | **Unlimited MSP technicians**, All-Clients overview & tab-safe `/t/:tenantSlug` switcher, 1-click client M365 consent, per-client Hybrid AD, 90-day per-client audit logs. |
| **MSP Pro** *(Flagship)* | $39 /tenant/mo | **$32 /tenant/mo** | Everything in MSP Core, four-eyes approvals, Conditional Access safety rails & scheduling, cross-tenant shared Role Template library, per-client technician RBAC scoping, MSP/client white-label Welcome Packs, 1-year per-client audit retention + client CSV exports. |
| **MSP Enterprise** *(50+ tenants)* | Custom | Custom *(Volume discounts)* | Everything in MSP Pro, custom white-label portal domain (`portal.yourmsp.com`), Microsoft Partner Center / GDAP sync, PSA & SIEM signed webhooks (HaloPSA, ConnectWise, Microsoft Sentinel), BYO Entra App per client, 7-year audit retention. |

### Edition Comparison

| Capability | Community (CE) | Team | Pro | MSP Core | MSP Pro |
| --- | --- | --- | --- | --- | --- |
| **Deployment & Updates** | Self-hosted Docker | Managed Azure SaaS | Managed Azure SaaS | Managed Azure SaaS | Managed Azure SaaS |
| **Managed M365 Tenants** | 1 | 1 | 1 | Unlimited *(5 min)* | Unlimited *(5 min)* |
| **Onboarding, Offboarding, Templates & Hybrid AD** | Included | Included | Included | Included | Included |
| **1-Click Entra Consent & Auto Cert Rotation** | BYO App only | Included | Included | Included | Included |
| **Four-Eyes Approvals & Custom Approval Rules** | — | — | Included | — | Included |
| **Conditional Access Safety Rails & Timed Exclusions** | — | — | Included | — | Included |
| **Scheduled Workflows & Timed Reversals** | — | — | Included | — | Included |
| **White-Label Welcome Pack PDF** | Powered by Rollcall | Powered by Rollcall | White-label | Powered by Rollcall | MSP / Client White-label |
| **Audit Log Retention & Export** | Self-managed (UI) | 90 days (UI) | 1 year + CSV | 90 days (UI) | 1 year + Client CSV |
| **Cross-Tenant Template Library & Per-Client Tech RBAC** | — | — | — | — | Included |
| **Portal Technician Seats** | Unlimited | Per Admin/Tech seat | Approvers/Viewers FREE | Unlimited MSP techs | Unlimited MSP techs |

---

## Get Started

- **Try Rollcall Cloud:** [Start a 14-day cardless free trial](https://app.rollcallit.com/signup) or estimate your cost with the [interactive pricing calculator](https://rollcallit.com/pricing).
- **Self-host Open-Rollcall CE:** Explore [Rollcall-IT/Open-Rollcall](https://github.com/Rollcall-IT/Open-Rollcall) and follow the [Day-1 deployment guide](https://docs.rollcallit.com).
- **Enterprise & MSP inquiries:** [sales@rollcallit.com](mailto:sales@rollcallit.com)
- **Security disclosures:** [security@rollcallit.com](mailto:security@rollcallit.com)

---

*Rollcall is an independent project and is not affiliated with or endorsed by Microsoft. Microsoft 365, Microsoft Entra, and Exchange Online are trademarks of the Microsoft group of companies.*
