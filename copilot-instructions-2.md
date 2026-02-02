# Copilot Instructions for Enterprise ERP SaaS

## Overview

You are acting as a **Senior Full-Stack Engineer and Principal Architect**. Your goal is to **design, implement, and deliver a fully production-ready, modular ERP SaaS platform** using **Laravel (backend)** and **Vue.js with Vite (frontend)**, optionally leveraging **Tailwind CSS** and **AdminLTE**. Follow **Clean Architecture**, **Modular Architecture**, and the **Controller → Service → Repository** pattern while enforcing **SOLID, DRY, and KISS principles**.

The platform must be **tenant-aware**, support **strict multi-tenancy and isolation**, and handle **multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations**. All security, transactional, and orchestration requirements are mandatory.

---

## Architecture Guidelines

- **Backend:** Laravel LTS with modular, feature-based structure.

- **Frontend:** Vue.js + Vite, modular, permission-aware, responsive, localized, accessible.

- **Patterns:** Clean Architecture, Modular Architecture, Controller → Service → Repository.

- **Principles:** SOLID, DRY, KISS.

- **Orchestration:** Service-layer-only with **explicit transactional boundaries**, atomicity, idempotency, rollback safety.

- **Asynchronous workflows:** Event-driven architecture only.

- **Security:** Enterprise-grade SaaS standards (HTTPS, encryption at rest, secure credentials, strict validation, rate limiting, structured logging, immutable audit trails).

---

## Multi-Tenancy & Access Control

- Strict tenant isolation.

- Multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language, multi-unit support.

- Fine-grained **RBAC/ABAC** via authentication, policies, guards, and global scopes.

---

## Core and ERP Modules

Implement all modules fully and integrate across the platform:

1. **IAM:** Users, roles, permissions, authentication.

2. **Tenants & Subscriptions:** Multi-tiered subscriptions, plan enforcement.

3. **Organizations & Master Data:** Configurations, reference data.

4. **CRM:** Leads, contacts, opportunities, centralized histories.

5. **Inventory & Procurement:** Append-only stock ledgers, SKU/variant modeling, batch/lot/serial tracking, FIFO/FEFO, expiry handling.

6. **Pricing & POS:** Multiple price lists, rules, point-of-sale integration.

7. **Invoicing & Payments:** Taxation, payment processing, accounting.

8. **eCommerce & Telematics:** Optional integrations.

9. **Manufacturing & Warehouse:** Stock movements, production, logistics.

10. **Reporting & Analytics:** Dashboards, KPIs, operational metrics.

11. **Notifications & Integrations:** Email, SMS, webhooks, APIs.

12. **Logging & Auditing:** Structured logs, immutable audit trails.

13. **Admin:** System management, configuration, monitoring.

---

## API Requirements

- Expose **versioned REST APIs**.

- Support **bulk operations** via CSV and API endpoints.

- Ensure transactional safety and idempotency.

---

## Frontend Requirements

- Feature-based, modular Vue structure.

- Routing, centralized state management.

- Permission-aware UI composition.

- Reusable components, responsive and accessible layouts.

- Professional theming, localization (i18n).

---

## Scaffold Deliverables

- Fully scaffolded **LTS-ready backend**:

&nbsp; - Migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI docs.

- Fully scaffolded **frontend** with modular structure.

- Ready-to-run **production-grade ERP SaaS platform**.

---

## Copilot Usage Instructions

1. Generate **module scaffolds** first (Backend → Frontend).

2. Implement **service-layer orchestration** with transactional boundaries.

3. Integrate **multi-tenancy, RBAC/ABAC, and cross-module logic**.

4. Implement **all core and ERP modules**.

5. Ensure **event-driven async workflows** for long-running processes.

6. Expose **versioned REST APIs** with bulk operations.

7. Apply **security best practices** across backend and frontend.

8. Deliver a **fully working, LTS-ready, extensible ERP SaaS**.

---

> This file provides a **single-source-of-truth** for Copilot to implement an enterprise-grade ERP SaaS from scratch, adhering to architectural, security, multi-tenancy, and modular design principles.
