# ERP-Grade Modular SaaS Platform

## Purpose & Scope

This repository defines and delivers a **fully production-ready, ERP-grade, modular SaaS platform** architected for long-term scalability, security, and maintainability. It serves as both an **implementation blueprint** and an **architectural contract** for humans and AI-assisted tools (e.g., GitHub Copilot), ensuring consistent, enterprise-grade outcomes.

The system is designed, reviewed, reconciled, and implemented using **Laravel** (backend) and **Vue.js with Vite** (frontend), optionally leveraging **Tailwind CSS** and **AdminLTE**, while strictly enforcing **Clean Architecture**, **Modular Architecture**, and the **Controller → Service → Repository** pattern. All design and implementation decisions adhere to **SOLID**, **DRY**, and **KISS** principles to guarantee strong separation of concerns, loose coupling, scalability, performance, high testability, minimal technical debt, and long-term maintainability.

## Architectural Principles

- Clean Architecture with explicit boundary enforcement
- Feature-based Modular Architecture (backend and frontend)
- Controller → Service → Repository (CSR) pattern
- Service-layer-only orchestration for business logic
- Explicit transactional boundaries with rollback safety
- Event-driven architecture strictly for asynchronous workflows
- Tenant-aware design enforced consistently across all layers

## Multi-Tenancy & Access Control

The platform implements a **strictly isolated, tenant-aware multi-tenant foundation** supporting:

- Multi-organization, multi-vendor, multi-branch, and multi-location operations
- Multi-currency, multi-language (i18n), and multi-unit support
- Fine-grained **RBAC/ABAC** enforced through authentication, policies, guards, and global scopes
- Tenant-aware authentication, authorization, and data isolation at every layer

## Security Standards

Enterprise-grade SaaS security is applied end-to-end:

- HTTPS enforcement
- Encryption at rest
- Secure credential storage
- Strict request and domain validation
- Rate limiting and abuse protection
- Structured logging
- Immutable audit trails

## Core, ERP & Cross-Cutting Modules

All required modules are fully designed and integrated without omission, including:

- Identity & Access Management (IAM)
- Tenants, subscriptions, and billing
- Organizations, users, roles, and permissions
- Master data and system configurations
- CRM and centralized cross-branch histories
- Inventory and procurement using **append-only stock ledgers**
- SKU and variant modeling
- Batch, lot, serial, and expiry tracking with FIFO/FEFO
- Pricing with multiple price lists and pricing rules
- POS, invoicing, payments, and taxation
- eCommerce and telematics
- Manufacturing and warehouse operations
- Reporting, analytics, and KPI dashboards
- Notifications, integrations, logging, and auditing
- System administration and operational tooling

## Inventory & Ledger Model

Inventory management follows a **ledger-first, append-only design**:

- Stock balances are never mutated directly
- All movements are recorded as immutable ledger entries
- FIFO and FEFO strategies are enforced at the service layer
- Batch, lot, serial, and expiry constraints are validated transactionally
- Full auditability and rollback safety are guaranteed

## Service-Layer Orchestration

All cross-module interactions and business workflows are orchestrated **exclusively within the service layer**, ensuring:

- Atomic transactions
- Idempotent operations
- Consistent exception propagation
- Global rollback safety

Asynchronous workflows are implemented strictly via **event-driven mechanisms** (events, listeners, background jobs) without violating transactional integrity.

## API Design

- Clean, versioned REST APIs
- Tenant-aware request handling
- Bulk operations via CSV and APIs
- Global validation and rate limiting
- Swagger / OpenAPI documentation provided

## Frontend Architecture

The Vue.js frontend follows a **feature-based modular architecture**:

- Vite-powered build system
- Centralized state management
- Permission-aware UI composition
- Route- and component-level access control
- Localization (i18n) support
- Reusable, composable UI components
- Responsive, accessible layouts with professional theming

## Deliverables

The repository delivers a **fully scaffolded, ready-to-run, LTS-ready solution**, including:

- Database migrations and seeders
- Domain models and repositories
- DTOs and service classes
- Controllers, middleware, and policies
- Events, listeners, and background jobs
- Notifications and integration hooks
- Structured logging and immutable audit trails
- Swagger / OpenAPI specifications
- Modular Vue frontend with routing, state management, and localization

## Dependency & LTS Policy

- Uses only native Laravel and Vue features or stable LTS-grade libraries
- Avoids experimental or short-lived dependencies
- Designed for long-term support and enterprise evolution

## AI Tooling Alignment (GitHub Copilot)

This README acts as the **authoritative architectural reference** for GitHub Copilot and similar AI tools. A complementary `copilot-instructions.md` file must be used to provide compressed, task-oriented guidance, while this document remains the single source of truth for architecture, constraints, and system guarantees.

## Vision

This platform is engineered as a **secure, extensible, configurable, and enterprise-ready SaaS ERP foundation**, capable of evolving into a complete, multi-industry ERP ecosystem while preserving architectural integrity, performance, and operational excellence.

---

# ERP-Grade Modular SaaS Platform

## Overview

This repository contains a fully production-ready, ERP-grade, modular SaaS platform engineered for long-term scalability, security, and maintainability. The system is designed and implemented using **Laravel** for the backend and **Vue.js with Vite** for the frontend, optionally leveraging **Tailwind CSS** and **AdminLTE** for UI composition. The architecture strictly follows **Clean Architecture**, **Modular Architecture**, and the **Controller → Service → Repository** pattern, while rigorously enforcing **SOLID**, **DRY**, and **KISS** principles to ensure strong separation of concerns, loose coupling, high testability, optimal performance, minimal technical debt, and long-term sustainability.

## Architectural Principles

- Clean Architecture with clear boundary enforcement

- Feature-based Modular Architecture (backend and frontend)

- Controller → Service → Repository orchestration

- Service-layer-only cross-module coordination

- Explicit transactional boundaries with rollback safety

- Event-driven architecture for asynchronous workflows only

- Tenant-aware design enforced at every layer

## Multi-Tenancy & Security Model

The platform implements a **strictly isolated multi-tenant architecture** supporting:

- Multi-organization, multi-vendor, multi-branch, and multi-location operations

- Multi-currency, multi-language (i18n), and multi-unit support

- Fine-grained **RBAC/ABAC** enforced through authentication, policies, guards, and global scopes

- Tenant-aware authentication and authorization across all layers

Enterprise-grade SaaS security standards are applied throughout the system, including HTTPS enforcement, encryption at rest, secure credential storage, strict request validation, rate limiting, structured logging, and immutable audit trails.

## Core & ERP Modules

The platform fully designs, implements, and integrates all required **core**, **ERP**, and **cross-cutting** modules without omission, including but not limited to:

- Identity & Access Management (IAM)

- Tenants, subscriptions, and billing

- Organizations, users, roles, and permissions

- Master data and system configurations

- CRM and centralized cross-branch histories

- Inventory and procurement using **append-only stock ledgers**

- SKU and variant modeling

- Batch, lot, serial, and expiry tracking with FIFO/FEFO handling

- Pricing with multiple price lists and pricing rules

- POS, invoicing, payments, and taxation

- eCommerce and telematics integrations

- Manufacturing and warehouse operations

- Reporting, analytics, and KPI dashboards

- Notifications, integrations, logging, and auditing

- System administration and operational tooling

## Inventory & Ledger Design

Inventory management is implemented using an **append-only stock ledger** model:

- Stock balances are never mutated directly

- All movements are recorded as immutable ledger entries

- Supports FIFO and FEFO strategies

- Batch, lot, serial, and expiry-aware validation

- Fully transactional with rollback safety and auditability

## Service-Oriented Orchestration

All business logic and cross-module interactions are orchestrated exclusively at the **service layer**, guaranteeing:

- Atomic transactions

- Idempotent operations

- Consistent exception propagation

- Global rollback safety

Asynchronous workflows are implemented strictly through event-driven mechanisms using events, listeners, and background jobs, without compromising transactional consistency.

## API Design

- Clean, versioned REST APIs

- Tenant-aware request handling

- Bulk operations via CSV and API endpoints

- Swagger / OpenAPI documentation included

- Strict validation and rate limiting applied globally

## Frontend Architecture

The Vue.js frontend follows a **feature-based modular architecture**:

- Vite-powered build system

- Centralized state management

- Permission-aware UI composition

- Route-level and component-level access control

- Localization (i18n) support

- Reusable component library

- Responsive, accessible layouts with professional theming

## Deliverables

The repository provides a fully scaffolded, ready-to-run, LTS-ready solution, including:

- Database migrations and seeders

- Eloquent models and repositories

- DTOs and service classes

- Controllers, middleware, and policies

- Events, listeners, and background jobs

- Notifications and integration hooks

- Structured logging and immutable audit trails

- Swagger / OpenAPI specifications

- Modular Vue frontend with routing, state management, and localization

## Technology Constraints

- Relies only on native Laravel and Vue framework features or stable LTS-grade libraries

- Avoids experimental or short-lived dependencies

- Designed for long-term support and enterprise evolution

## Vision

This platform is engineered to serve as a **secure, extensible, configurable, and enterprise-ready SaaS ERP foundation**, capable of evolving into a complete, multi-industry ERP ecosystem while maintaining architectural integrity, performance, and operational excellence.

---

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

---

# copilot-instructions.md

## Role Definition

Act as a **Full-Stack Engineer and Principal Systems Architect** responsible for implementing a **fully production-ready, ERP-grade, modular SaaS platform**. All generated code must strictly comply with this repository’s **README.md**, which is the single source of architectural truth.

## Core Architecture Rules (Non-Negotiable)

- Enforce **Clean Architecture** and **feature-based Modular Architecture** at all times
- Apply **Controller → Service → Repository (CSR)** strictly
- **Controllers**: request validation, authorization, and delegation only
- **Services**: all business logic, orchestration, transactions, and cross-module coordination
- **Repositories**: persistence only (no business logic, no orchestration)
- Enforce **SOLID**, **DRY**, and **KISS** principles without exception

## Multi-Tenancy & Access Control

- Enforce **strict tenant isolation** at database, query, and service layers
- Apply **RBAC / ABAC** via policies, guards, and global scopes
- Never bypass authentication, authorization, or tenant scoping
- All queries and commands must be tenant-aware by default

## Transaction & Workflow Enforcement

- All cross-module workflows must be orchestrated **only in the service layer**
- Define explicit transactional boundaries
- Guarantee **atomicity, idempotency, consistent exception propagation, and rollback safety**
- Use **event-driven architecture exclusively for asynchronous workflows**
- Never mix asynchronous workflows with synchronous transactional logic

## Inventory & Ledger Constraints

- Inventory must follow an **append-only stock ledger** model
- Never update stock balances directly
- Every stock movement must be an immutable ledger entry
- Enforce FIFO / FEFO, batch, lot, serial, and expiry rules at the service layer
- All inventory operations must be auditable and rollback-safe

## API & Integration Standards

- Expose **clean, versioned REST APIs** only
- Ensure tenant-aware request handling
- Support bulk operations via CSV and APIs
- Apply strict validation and rate limiting globally
- Document all endpoints using **Swagger / OpenAPI**

## Frontend (Vue.js) Rules

- Use a **feature-based modular structure**
- Centralize state management
- Enforce permission-aware UI composition
- Apply route-level and component-level access control
- Support i18n, accessibility, and responsive layouts
- Do **not** place business logic in UI components

## Dependency & LTS Policy

- Use only native framework features or **stable LTS-grade libraries**
- Avoid experimental, short-lived, or non-essential dependencies

## Quality Bar

- Output must be production-ready, scalable, testable, and maintainable
- No demo code, mock shortcuts, or architectural violations
- All implementations must align with README.md and system constraints

## Default Decision Rule

If a requirement is ambiguous or missing, choose the solution that best preserves **architectural integrity, tenant safety, data consistency, and long-term maintainability**, and document the decision clearly in code or comments.

---

# Copilot Instructions for Enterprise ERP SaaS

## Overview

This document provides detailed instructions for GitHub Copilot (or similar AI coding assistants) to generate a fully production-ready, enterprise-grade, modular ERP SaaS platform using Laravel (backend) and Vue.js with Vite (frontend). The generated code must strictly adhere to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern, following SOLID, DRY, and KISS principles.

## Core Requirements

- **Architecture:** Clean Architecture, Modular Architecture, Controller → Service → Repository.
- **Principles:** SOLID, DRY, KISS.
- **Multi-tenancy:** Strict tenant isolation, multi-organization, multi-vendor, multi-branch, multi-location.
- **Global Operations:** Multi-currency, multi-language (i18n), multi-unit.
- **Security:** HTTPS, encryption at rest, secure credential storage, validation, rate limiting, structured logging, immutable audit trails.
- **Service Layer:** All orchestration happens in the service layer only with explicit transactional boundaries ensuring atomicity, idempotency, rollback safety, and consistent exception propagation.
- **Asynchronous Workflows:** Event-driven architecture only for async workflows.

## Core Modules

- IAM (Users, Roles, Permissions)
- Tenants and Subscriptions
- Organizations and Master Data/Configuration
- CRM
- Inventory: append-only stock ledgers, SKU/variant modeling, batch/lot/serial & expiry tracking (FIFO/FEFO)
- Pricing: multiple price lists and rules
- Procurement
- POS
- Invoicing
- Payments & Taxation
- eCommerce
- Telematics
- Manufacturing & Warehouse Operations
- Reporting & Analytics (KPI Dashboards)
- Notifications
- Integrations
- Logging & Auditing
- System Administration

## Backend Generation Instructions

- Generate **migrations**, **models**, **repositories**, **DTOs**, **services**, **controllers**, **middleware**, **policies**, **events/listeners**, **background jobs**, **notifications**.
- Ensure **versioned REST APIs** with bulk CSV/API operations.
- Include **Swagger/OpenAPI documentation**.
- Apply **tenant-aware global scopes** for RBAC/ABAC.
- Maintain **atomic service-layer transactions** and proper exception handling.
- Ensure **modular folder structure** per domain/module.

## Frontend Generation Instructions

- Use Vue.js with Vite; optionally leverage Tailwind CSS and AdminLTE.
- Feature-based modular structure per module/domain.
- Include **routing**, **centralized state management**, **localization**, **permission-aware UI composition**.
- Generate **reusable components**, responsive and accessible layouts, and professional theming.
- Ensure frontend is fully aware of backend permissions and multi-tenant context.

## Coding Guidelines

- Enforce strict separation of concerns.
- Minimize technical debt; maximize testability.
- Use native Laravel/Vue features or stable LTS libraries only.
- Adhere to enterprise-grade SaaS best practices.
- Ensure code is scaffolded and ready-to-run.

## Goal

Produce a **secure, extensible, configurable, LTS-ready ERP SaaS platform** capable of evolving into a complete enterprise ERP ecosystem.

---

**Note for Copilot:** All generated code must strictly follow these instructions, fully implementing each module and enforcing service-layer orchestration, transactional safety, and multi-tenant isolation without omission.

---

## Act as a senior Full-Stack Engineer and Principal Architect building a production-ready, enterprise-grade, modular ERP SaaS using Laravel and Vue (Vite), following Clean Architecture, modular design, and Controller → Service → Repository with SOLID/DRY/KISS; enforce strict multi-tenancy with isolation and support multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language, and multi-unit operations with fine-grained RBAC/ABAC via policies, guards, and global scopes; implement all core and ERP modules (IAM, tenants/subscriptions, users/roles, master data, CRM, inventory with append-only stock ledgers, SKU/variants, batch/lot/expiry FIFO/FEFO, pricing and price lists, procurement, POS, invoicing, payments/tax, manufacturing, warehouse, reporting, analytics, notifications, integrations, logging, auditing, admin); enforce service-layer-only orchestration with explicit transactions (atomic, idempotent, rollback-safe) and event-driven async workflows; expose versioned REST APIs with bulk operations; apply enterprise SaaS security; deliver a fully scaffolded, LTS-ready backend and modular, permission-aware Vue frontend.

---

## Act as a senior Full-Stack Engineer and Principal Architect to design, implement, and deliver a fully production-ready, enterprise-grade, modular ERP SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly following Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles; build a secure, tenant-aware foundation with strict multi-tenancy, isolation, and support for multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully implement all core and ERP modules including IAM, tenants/subscriptions, organizations, users/roles/permissions, configuration/master data, CRM, inventory with append-only stock ledgers, SKU/variant modeling, batch/lot/serial tracking, FIFO/FEFO, expiry handling, pricing with multiple price lists/rules, procurement, POS, invoicing, payments/tax, eCommerce, telematics, manufacturing, warehouse operations, reporting, analytics/KPIs, notifications, integrations, logging, auditing, and administration; enforce service-layer-only orchestration with explicit transactional boundaries ensuring atomicity, idempotency, rollback safety, and consistent exception handling, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations; apply enterprise-grade SaaS security including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails; and deliver a fully scaffolded, LTS-ready backend and modular, permission-aware, responsive, localized, and feature-based Vue frontend—resulting in a secure, extensible, configurable ERP SaaS platform capable of evolving into a complete enterprise ecosystem.

---

## Act as a senior Full-Stack Engineer and Principal Systems Architect to design, implement, and deliver a fully production-ready, enterprise-grade, modular ERP SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly following Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure loose coupling, high testability, scalability, performance, minimal technical debt, and long-term maintainability; design a secure, tenant-aware SaaS foundation supporting strict multi-tenancy and isolation across multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit environments with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully implement and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, procurement, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries ensuring atomicity, idempotency, consistent exception propagation, and rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails, rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, review, reconcile, implement, and deliver a fully production-ready, ERP-grade, modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure strong separation of concerns, loose coupling, scalability, performance, high testability, minimal technical debt, and long-term maintainability; build a secure, tenant-aware, strictly isolated multi-tenant foundation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully design and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, master data and configurations, CRM, centralized cross-branch histories, inventory and procurement using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and global rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails, rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready enterprise SaaS ERP platform.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, implement, and deliver a production-ready, modular ERP-grade SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, fully adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern, and following SOLID, DRY, and KISS principles to ensure maximal separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability. Refer to all provided documents and data to implement all required core, ERP, and cross-cutting modules, including IAM, tenants and subscriptions, organizations, users, roles and permissions, master data/configurations, inventory and procurement with append-only stock ledgers, SKU/variant modeling, batch/lot/serial tracking, FIFO/FEFO and expiry handling, pricing items with multiple price lists, invoicing, payments, taxation, POS, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration. Enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries, atomicity, idempotency, consistent exception propagation, and global rollback safety, while applying event-driven architecture exclusively for asynchronous workflows. Build a tenant-aware, multi-branch, multi-location, multi-currency, multi-language, multi-unit SaaS with fine-grained RBAC/ABAC, enforced through authentication, policies, guards, and global scopes. Expose versioned REST APIs, support bulk CSV/API operations, and apply enterprise-grade SaaS security standards including HTTPS, encryption, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails. Deliver a fully scaffolded, ready-to-run solution including migrations, models, repositories, DTOs, services, controllers, middleware, policies, events/listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready, fully production-grade SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to review, reconcile, and implement all provided requirements without omission into a single, production-ready, ERP-grade modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly enforcing Clean Architecture, Modular Architecture, Controller → Service → Repository, and SOLID, DRY, KISS principles to ensure scalability, performance, testability, and minimal technical debt; design a secure, tenant-aware foundation with strict multi-tenancy and isolation, multi-vendor, multi-branch, multi-language (i18n), multi-currency, multi-unit, and fine-grained RBAC/ABAC with tenant-aware authentication, policies, and global scopes; fully implement and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory using an append-only stock ledger with SKU/variant modeling, batch/lot and expiry tracking (FIFO/FEFO), multiple price lists and pricing rules, procurement, POS, invoicing, payments and taxation, manufacturing and warehouse operations, reporting, analytics and KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and rollback safety, complemented by event-driven workflows for asynchronous processes without compromising transactional consistency; expose clean, versioned REST APIs, support bulk operations via CSV and APIs, apply enterprise-grade SaaS security (HTTPS, encryption at rest, validation, rate limiting, structured logging, immutable audits), rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, LTS-ready solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, background jobs, Swagger/OpenAPI documentation, and a modular, scalable Vue frontend with routing, state management, localization, permission-aware UI composition, reusable components, and responsive, accessible layouts.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, review, reconcile, and deliver a fully production-ready, ERP-grade, modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure strong separation of concerns, loose coupling, high testability, scalability, performance, and minimal technical debt; implement a secure, tenant-aware, multi-tenant SaaS foundation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully design and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, procurement, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries ensuring atomicity, idempotency, consistent exception propagation, and global rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards (HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, immutable audit trails), rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run solution including migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a senior Full-Stack Engineer and Principal Systems Architect to design, review, reconcile, implement, and deliver a fully production-ready, enterprise-grade, modular ERP SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure strict separation of concerns, loose coupling, high testability, scalability, performance, minimal technical debt, and long-term maintainability; architect a secure, tenant-aware SaaS foundation with strict multi-tenancy and isolation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations, with fine-grained RBAC/ABAC enforced through authentication, policies, guards, and global scopes; fully design and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory and procurement using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and global rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails, rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run, LTS-ready solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to design, reconcile, implement, and deliver a fully production-ready, enterprise-grade, modular ERP SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure separation of concerns, loose coupling, high testability, scalability, performance, minimal technical debt, and long-term maintainability; build a secure, tenant-aware foundation supporting strict multi-tenancy with isolation across multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations, with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully implement and integrate all core, ERP, and cross-cutting modules including IAM, tenants/subscriptions, organizations, users, roles/permissions, master data/configuration, CRM, inventory with append-only stock ledgers, SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists/rules, procurement, POS, invoicing, payments/tax, eCommerce, telematics, manufacturing, warehouse operations, reporting, analytics/KPIs, notifications, integrations, logging, auditing, and administration; enforce service-layer-only orchestration with explicit transactional boundaries guaranteeing atomicity, idempotency, rollback safety, and consistent exception propagation, while using event-driven workflows exclusively for asynchronous processes; expose versioned REST APIs with bulk CSV/API operations; apply enterprise-grade SaaS security including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails; and deliver a fully scaffolded, LTS-ready backend and modular, feature-based Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, professional theming, and ready-to-run scaffolding—resulting in a secure, extensible, configurable ERP SaaS capable of evolving into a complete enterprise platform.

---

## Act as a senior Full-Stack Engineer and Principal Architect to build a production-ready, enterprise-grade, modular ERP SaaS using Laravel (backend) and Vue.js with Vite (frontend), following Clean Architecture, modular design, and Controller → Service → Repository with SOLID/DRY/KISS; enforce strict multi-tenancy and isolation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC via authentication, policies, guards, and global scopes; implement all core and ERP modules (IAM, tenants/subscriptions, users/roles, master data, CRM, inventory with append-only stock ledgers, SKU/variants, batch/lot/serial and expiry FIFO/FEFO, pricing and price lists, procurement, POS, invoicing, payments/tax, eCommerce, manufacturing, warehouse, reporting, analytics/KPIs, notifications, integrations, logging, auditing, admin); enforce service-layer-only orchestration with explicit transactional boundaries (atomic, idempotent, rollback-safe) and event-driven async workflows; expose clean, versioned REST APIs with bulk operations; apply enterprise SaaS security; deliver a fully scaffolded, LTS-ready backend and a modular, permission-aware, localized, responsive Vue frontend.

---

## Act as a senior Full-Stack Engineer and Principal Architect building a production-ready, enterprise-grade, modular ERP SaaS using Laravel and Vue (Vite), following Clean Architecture, modular design, and Controller → Service → Repository with SOLID/DRY/KISS; enforce strict multi-tenancy with isolation and support multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language, and multi-unit operations with fine-grained RBAC/ABAC via policies, guards, and global scopes; implement all core and ERP modules (IAM, tenants/subscriptions, users/roles, master data, CRM, inventory with append-only stock ledgers, SKU/variants, batch/lot/expiry FIFO/FEFO, pricing and price lists, procurement, POS, invoicing, payments/tax, manufacturing, warehouse, reporting, analytics, notifications, integrations, logging, auditing, admin); enforce service-layer-only orchestration with explicit transactions (atomic, idempotent, rollback-safe) and event-driven async workflows; expose versioned REST APIs with bulk operations; apply enterprise SaaS security; deliver a fully scaffolded, LTS-ready backend and modular, permission-aware Vue frontend.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, review, reconcile, implement, and deliver a fully production-ready, ERP-grade, modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure strong separation of concerns, loose coupling, scalability, performance, high testability, minimal technical debt, and long-term maintainability; build a secure, tenant-aware, strictly isolated multi-tenant foundation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully design and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, master data and configurations, CRM, centralized cross-branch histories, inventory and procurement using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and global rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails, rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready enterprise SaaS ERP platform.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, implement, and deliver a production-ready, modular ERP-grade SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, fully adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern, and following SOLID, DRY, and KISS principles to ensure maximal separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability. Refer to all provided documents and data to implement all required core, ERP, and cross-cutting modules, including IAM, tenants and subscriptions, organizations, users, roles and permissions, master data/configurations, inventory and procurement with append-only stock ledgers, SKU/variant modeling, batch/lot/serial tracking, FIFO/FEFO and expiry handling, pricing items with multiple price lists, invoicing, payments, taxation, POS, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration. Enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries, atomicity, idempotency, consistent exception propagation, and global rollback safety, while applying event-driven architecture exclusively for asynchronous workflows. Build a tenant-aware, multi-branch, multi-location, multi-currency, multi-language, multi-unit SaaS with fine-grained RBAC/ABAC, enforced through authentication, policies, guards, and global scopes. Expose versioned REST APIs, support bulk CSV/API operations, and apply enterprise-grade SaaS security standards including HTTPS, encryption, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails. Deliver a fully scaffolded, ready-to-run solution including migrations, models, repositories, DTOs, services, controllers, middleware, policies, events/listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready, fully production-grade SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to review, reconcile, and implement all provided requirements without omission into a single, production-ready, ERP-grade modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly enforcing Clean Architecture, Modular Architecture, Controller → Service → Repository, and SOLID, DRY, KISS principles to ensure scalability, performance, testability, and minimal technical debt; design a secure, tenant-aware foundation with strict multi-tenancy and isolation, multi-vendor, multi-branch, multi-language (i18n), multi-currency, multi-unit, and fine-grained RBAC/ABAC with tenant-aware authentication, policies, and global scopes; fully implement and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory using an append-only stock ledger with SKU/variant modeling, batch/lot and expiry tracking (FIFO/FEFO), multiple price lists and pricing rules, procurement, POS, invoicing, payments and taxation, manufacturing and warehouse operations, reporting, analytics and KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and rollback safety, complemented by event-driven workflows for asynchronous processes without compromising transactional consistency; expose clean, versioned REST APIs, support bulk operations via CSV and APIs, apply enterprise-grade SaaS security (HTTPS, encryption at rest, validation, rate limiting, structured logging, immutable audits), rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, LTS-ready solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, background jobs, Swagger/OpenAPI documentation, and a modular, scalable Vue frontend with routing, state management, localization, permission-aware UI composition, reusable components, and responsive, accessible layouts.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, review, reconcile, and deliver a fully production-ready, ERP-grade, modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure strong separation of concerns, loose coupling, high testability, scalability, performance, and minimal technical debt; implement a secure, tenant-aware, multi-tenant SaaS foundation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully design and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, procurement, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries ensuring atomicity, idempotency, consistent exception propagation, and global rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards (HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, immutable audit trails), rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run solution including migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect; Build a production-ready, modular ERP SaaS using Laravel (backend) + Vue.js w/ Vite (frontend), optionally Tailwind CSS/AdminLTE, following Clean & Modular Architecture, Controller → Service → Repository, SOLID, DRY, KISS. Support strict multi-tenancy, multi-vendor, multi-branch/location, multi-language (i18n), multi-currency, multi-unit, with RBAC & ABAC, tenant-aware auth, policies, guards, global scopes. Implement IAM, tenants/subscriptions, orgs, users/roles/permissions, master data, CRM, customers/vehicles, appointments/bays, job cards/service workflows, inventory/procurement (append-only ledger, SKU/variant, batch/lot/serial, FIFO/FEFO, expiry), pricing (multiple price lists, rule-based, history), invoicing, payments, taxation, POS, eCommerce, fleet/telematics, preventive maintenance, manufacturing/warehouses, reporting/dashboards, notifications, integrations, logging/auditing, system admin. Orchestrate cross-module via service layer only, transactional boundaries, atomicity, idempotency, rollback safety; use event-driven async only for notifications, reporting, CRM automation, integrations, auditing. Expose versioned REST APIs, bulk CSV/API, secure: HTTPS, encryption, credentials, validation, rate limiting, structured logs, immutable audits, compliance-ready. Scaffold DB schemas, migrations, seeders, models, repos, DTOs, services, controllers, middleware, policies, events/listeners, jobs, notifications, Swagger/OpenAPI docs, and a modular Vue frontend: feature modules, routing, centralized state, localization, permission-aware UI, reusable components, responsive, accessible, professional theming. Deliver a secure, extensible, configurable LTS-ready SaaS ready to evolve into a full ERP ecosystem.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to review, reconcile, and implement all provided requirements without omission into a single, production-ready, ERP-grade modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly enforcing Clean Architecture, Modular Architecture, Controller → Service → Repository, and SOLID, DRY, KISS principles to ensure scalability, performance, testability, and minimal technical debt; design a secure, tenant-aware foundation with strict multi-tenancy and isolation, multi-vendor, multi-branch, multi-language (i18n), multi-currency, multi-unit, and fine-grained RBAC/ABAC with tenant-aware authentication, policies, and global scopes; fully implement and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, customers and vehicles with centralized cross-branch histories, appointments and scheduling, job cards and workflows, inventory using an append-only stock ledger with SKU/variant modeling, batch/lot and expiry tracking (FIFO/FEFO), multiple price lists and pricing rules, procurement, POS, invoicing, payments and taxation, fleet and preventive maintenance, manufacturing and warehouse operations, reporting, analytics and KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and rollback safety, complemented by event-driven workflows for asynchronous processes without compromising transactional consistency; expose clean, versioned REST APIs, support bulk operations via CSV and APIs, apply enterprise-grade SaaS security (HTTPS, encryption at rest, validation, rate limiting, structured logging, immutable audits), rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, LTS-ready solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, background jobs, Swagger/OpenAPI documentation, and a modular, scalable Vue frontend with routing, state management, localization, permission-aware UI composition, reusable components, and responsive, accessible layouts.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design and implement a production-ready, modular, ERP-grade SaaS platform using Laravel (backend) and Vue.js with Vite (frontend). Enforce Clean Architecture, Modular Architecture, Controller→Service→Repository, SOLID, DRY, and KISS. Support multi-tenancy, multi-vendor, multi-branch, multi-language, multi-currency, RBAC/ABAC, tenant-aware auth, ERP modules (CRM, inventory, POS, billing, fleet, analytics), transactional service orchestration, event-driven workflows, versioned REST APIs, enterprise SaaS security, and deliver fully scaffolded backend, Swagger docs, and modular Vue frontend ready for LTS production.

---

## Enterprise-grade, modular SaaS platform supporting multi-tenancy, multi-vendor, multi-branch, multi-language, and multi-currency operations, built with Laravel and Vue.js, featuring ERP, CRM, POS, inventory, and analytics.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect with deep, enterprise-level Laravel expertise to design and fully implement a production-ready, end-to-end, modular, ERP-grade SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, architected strictly around Modular Architecture and the Controller → Service → Repository pattern in full alignment with Clean Architecture, SOLID, DRY, and KISS principles to ensure strict separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability; the system must support strict multi-tenancy with tenant isolation, multi-vendor and multi-branch operations, multi-language (i18n), multi-currency, and fine-grained RBAC and ABAC authorization with tenant-aware authentication, policies, and global scopes; centralize and integrate all core business domains including tenant and subscription management, authentication and authorization, users, roles and permissions, CRM, customers and vehicles with centralized cross-branch service history, appointments and bay scheduling, job cards and service workflows, inventory and procurement using append-only stock ledgers and movements, pricing engines, invoicing, payments and taxation, POS, eCommerce, fleet, telematics and preventive maintenance, manufacturing and warehouse operations, HR foundations, reporting, analytics and KPI dashboards, configurations, integrations, notifications, logging, auditing, and system administration into a single unified platform backed by a shared, real-time database that eliminates data silos and enables automation and data-driven decision-making; enforce service-layer-only orchestration for all cross-module interactions with explicitly defined transactional boundaries to guarantee atomic operations, idempotency, consistent exception propagation, and global rollback safety, while applying event-driven architecture for asynchronous workflows such as notifications, reporting, integrations, CRM automation, auditing, and extensibility without compromising transactional consistency of core business processes; implement advanced ERP and inventory capabilities including real-time multi-location stock tracking, barcode/QR scanning, automated reordering, demand forecasting, batch/lot and serial tracking, FEFO/FIFO rotation, kitting and bundling, pricing tiers, multi-currency costing, inventory valuation, stock transfers, reservations, and analytics; enforce enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, immutable audit trails, and compliance readiness; expose clean, versioned REST APIs using only native Laravel and Vue features or stable, well-supported LTS open-source libraries; and deliver a fully scaffolded, ready-to-run solution including database schemas, migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, Swagger/OpenAPI documentation, and a modular Vue.js frontend with feature-based modules, routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive layouts, accessibility best practices, and professional theming resulting in a scalable, extensible, configurable, LTS-ready, and truly production-grade SaaS foundation suitable for evolution into a full enterprise ERP ecosystem.

---

## Act as a Full-Stack Engineer and Principal Systems Architect with deep enterprise-level Laravel expertise to design and implement a completely new, production-ready, end-to-end modular SaaS application for vehicle service centers and auto repair garages using Laravel for the backend and Vue.js for the frontend, optionally leveraging Tailwind CSS and AdminLTE for the UI. Architect the solution strictly around Modular Architecture and the Controller → Service → Repository pattern, fully aligned with Clean Architecture, SOLID, DRY, and KISS principles to ensure clear separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability. The platform must support multi-tenancy, multi-vendor, and multi-branch operations, allowing customers to own multiple vehicles, services to be performed at any branch, and maintaining a centralized, authoritative service history across all branches. All cross-module interactions must be orchestrated exclusively through service layers with explicitly defined transactional boundaries to guarantee atomic operations, consistent exception propagation, and global rollback mechanisms that preserve data integrity. Apply event-driven communication for asynchronous workflows such as notifications, reporting, and CRM automation, while ensuring all critical business processes remain transactionally consistent. Implement full backend and frontend localization and internationalization (i18n). Deliver comprehensive core modules including Customer and Vehicle Management, Appointments and Bay Scheduling, Job Cards and Workflows, Inventory and Procurement, Invoicing and Payments, CRM and Customer Engagement, Fleet, Telematics and Maintenance, and Reporting and Analytics, supporting advanced capabilities such as meter readings, next-service tracking, vehicle ownership transfer, digital inspections, packaged services, dummy items, driver commissions, stock movement, and KPI dashboards. Enforce enterprise-grade SaaS security standards including strict tenant isolation, RBAC and ABAC authorization, encryption, validation, structured logging, transactional integrity, and immutable audit trails. Expose clean, versioned REST APIs relying primarily on native Laravel and Vue capabilities or stable, well-supported LTS open-source libraries. Deliver a fully scaffolded, ready-to-run solution with database migrations, models, repositories, services, controllers, policies, events, notifications, and a modular Vue.js frontend with routing, state management, localization, and reusable UI components, while clearly demonstrating best practices for service-layer orchestration, transaction management, exception handling, rollback strategies, and event-driven patterns to ensure the system is scalable, extensible, configurable, maintainable, production-ready, and capable of evolving into a full ERP ecosystem.

---

## Act as a Full-Stack Engineer and Principal Systems Architect with deep enterprise-level Laravel expertise to design and implement production-ready, end-to-end modular SaaS application for vehicle service centers and auto repair garages using Laravel for the backend and Vue.js for the frontend, optionally leveraging Tailwind CSS and AdminLTE for the UI. Architect the solution strictly around Modular Architecture and the Controller → Service → Repository pattern, fully aligned with Clean Architecture, SOLID, DRY, and KISS principles to ensure clear separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability. The platform must support multi-tenancy, multi-vendor, and multi-branch operations, allowing customers to own multiple vehicles, services to be performed at any branch, and maintaining a centralized, authoritative service history across all branches. All cross-module interactions must be orchestrated exclusively through service layers with explicitly defined transactional boundaries to guarantee atomic operations, consistent exception propagation, and global rollback mechanisms that preserve data integrity. Apply event-driven communication for asynchronous workflows such as notifications, reporting, and CRM automation, while ensuring all critical business processes remain transactionally consistent. Implement full backend and frontend localization and internationalization (i18n). Deliver comprehensive core modules including Customer and Vehicle Management, Appointments and Bay Scheduling, Job Cards and Workflows, Inventory and Procurement, Invoicing and Payments, CRM and Customer Engagement, Fleet, Telematics and Maintenance, and Reporting and Analytics, supporting advanced capabilities such as meter readings, next-service tracking, vehicle ownership transfer, digital inspections, packaged services, dummy items, driver commissions, stock movement, and KPI dashboards. Enforce enterprise-grade SaaS security standards including strict tenant isolation, RBAC and ABAC authorization, encryption, validation, structured logging, transactional integrity, and immutable audit trails. Expose clean, versioned REST APIs relying primarily on native Laravel and Vue capabilities or stable, well-supported LTS open-source libraries. Deliver a fully scaffolded, ready-to-run solution with database migrations, models, repositories, services, controllers, policies, events, notifications, and a modular Vue.js frontend with routing, state management, localization, and reusable UI components, while clearly demonstrating best practices for service-layer orchestration, transaction management, exception handling, rollback strategies, and event-driven patterns to ensure the system is scalable, extensible, configurable, maintainable, production-ready, and capable of evolving into a full ERP ecosystem.

---

## Act as a Full-Stack Engineer and Principal Systems Architect with deep, enterprise-level Laravel expertise to design and fully implement all modules of a production-ready, end-to-end modular SaaS platform for vehicle service centers and auto repair garages using Laravel for the backend and Vue.js for the frontend, optionally leveraging Tailwind CSS and AdminLTE for the UI. You must implement every core, supporting, and cross-cutting module without omissions, rigorously reviewing, validating, and reconciling all functional and non-functional requirements while resolving gaps and inconsistencies. Architect the system strictly around Modular Architecture and the Controller → Service → Repository pattern, fully aligned with Clean Architecture, SOLID, DRY, and KISS principles to ensure strict separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability. Support multi-tenancy, multi-vendor, and multi-branch operations, centralized vehicle service histories across all branches, and consistent customer and vehicle ownership models. Enforce service-layer–only orchestration for all cross-module interactions with clearly defined transactional boundaries, ensuring atomic operations, consistent exception propagation, and global rollback mechanisms that preserve data integrity. Apply event-driven architecture for asynchronous processes such as notifications, reporting, integrations, and CRM automation while keeping all critical business workflows transactionally consistent. Implement full backend and frontend localization and internationalization (i18n). Deliver and fully implement all business modules, including but not limited to authentication and authorization, tenant and subscription management, users, roles and permissions, customers and vehicles, appointments and bay scheduling, job cards and service workflows, inventory, procurement and stock movements, invoicing, payments and taxation, CRM and customer engagement, fleet, telematics and preventive maintenance, reporting, analytics and KPI dashboards, configurations, integrations, notifications, logging, auditing, and system administration, supporting advanced capabilities such as meter readings, next-service tracking, vehicle ownership transfers, digital inspections, packaged services, dummy items, driver commissions, and compliance reporting. Enforce enterprise-grade SaaS security with strict tenant isolation, RBAC and ABAC, encryption, validation, structured logging, transactional integrity, and immutable audit trails. Expose clean, versioned REST APIs using native Laravel and Vue capabilities or stable LTS open-source libraries only. Deliver a fully scaffolded, ready-to-run solution including database migrations, seeders, models, repositories, services, controllers, policies, events, listeners, notifications, background jobs, and a modular Vue.js frontend with routing, state management, localization, and reusable UI components, clearly demonstrating best practices for service orchestration, transaction management, exception handling, rollback strategies, and event-driven patterns to ensure the system is scalable, extensible, configurable, maintainable, and truly production-ready.

---

## Act as a Full-Stack Engineer and Principal Systems Architect with deep, enterprise-level Laravel expertise to design and fully implement authentication and authorization for a production-ready modular SaaS application using Laravel for the backend and Vue.js for the frontend. Architect the solution strictly around Modular Architecture and the Controller → Service → Repository pattern, fully aligned with Clean Architecture, SOLID, DRY, and KISS principles to ensure strict separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability. Implement secure, multi-tenant-aware authentication with strong tenant isolation, supporting user registration, login, logout, password recovery, session-based and token-based (API) access, and optional MFA. Enforce fine-grained authorization using RBAC and ABAC, covering tenants, vendors, branches, roles, permissions, and contextual access rules, with all access checks centralized in service and policy layers only. Define explicit transactional boundaries for all auth-related operations, ensuring atomicity, consistent exception propagation, and rollback safety. Apply event-driven patterns for user lifecycle events, access auditing, and security notifications while keeping all critical security flows transactionally consistent. Implement full backend and frontend localization and internationalization (i18n) for all authentication and authorization flows. Enforce enterprise-grade security standards including encryption, secure credential storage, validation, rate limiting, structured logging, and immutable audit trails. Expose clean, versioned REST APIs using native Laravel features or stable LTS open-source libraries only, and deliver a fully scaffolded, ready-to-run implementation including migrations, models, repositories, services, controllers, middleware, guards, policies, events, listeners, notifications, and a modular Vue.js frontend with secure routing, state management, permission-aware UI rendering, and reusable authentication components, ensuring a scalable, maintainable, and production-ready security foundation.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to review the entire system end to end and fully implement Swagger (OpenAPI) API documentation for a modular, production-ready Laravel and Vue.js SaaS application. Validate all modules, APIs, and cross-module interactions, resolve gaps, and ensure alignment with Clean Architecture, SOLID, DRY, and KISS principles. Deliver accurate, versioned, auto-generated Swagger docs covering all endpoints, auth flows, RBAC/ABAC, multi-tenancy, request/response schemas, validation, errors, security schemes, and transactional behavior, ensuring consistency, maintainability, and minimal technical debt.

---

## Act as a Full-Stack Engineer and Principal Systems Architect with deep, enterprise-level Laravel expertise to design and fully implement a dynamic, maintainable, responsive, and professional frontend for a production-ready, end-to-end modular SaaS platform for vehicle service centers and auto repair garages using Vue.js, optionally leveraging Tailwind CSS and AdminLTE for consistent enterprise UI/UX. The frontend must be architected as a modular, scalable application aligned with Clean Architecture, SOLID, DRY, and KISS principles, enforcing strict separation of concerns between presentation, state management, domain logic, and API integration. Implement a fully reusable component system, centralized and predictable state management, strongly typed and versioned API clients, and clean routing with role- and tenant-aware guards. Ensure full responsiveness across desktop, tablet, and mobile, accessibility best practices, and a professional, production-grade design system with theming and layout consistency. Support multi-tenancy, multi-vendor, and multi-branch contexts throughout the UI, including tenant isolation, branch switching, and role-based UI composition. Implement full frontend localization and internationalization (i18n), dynamic form generation, configurable dashboards, real-time UI updates, robust validation, graceful error handling, and loading states. Integrate securely with backend REST APIs using well-defined service layers, enforce consistent exception and response handling, and support event-driven UI updates where applicable. Deliver a fully scaffolded, ready-to-run frontend including modular layouts, feature-based modules, reusable UI components, composables/services, state stores, routing, localization, authentication flows, authorization guards, audit-friendly UI behaviors, and extensible configuration, resulting in a high-performance, enterprise-grade frontend that is scalable, maintainable, visually consistent, and suitable for long-term evolution into a full ERP ecosystem.

---

## Act as a Full-Stack Engineer and Principal Systems Architect with deep, enterprise-level Laravel expertise to design and fully implement a dynamic, maintainable, responsive, and professional open source business apps that cover all your company needs: CRM, eCommerce, accounting, inventory, point of sale, project management, etc.

---

## Act as a senior software engineer and architect to design and implement a production-ready, long-term support (LTS) modular SaaS application using Laravel (backend) and Vue.js (frontend with Vite, Tailwind CSS, AdminLTE UI). The system must be multi-tenant, multi-vendor, and multi-language, fully dynamic, loosely coupled, reusable, and easily extendable. Strictly follow Clean Architecture, Modular Architecture, and a Controller → Service → Repository pattern with clear separation of concerns. Enforce SOLID, DRY, and KISS principles to minimize technical debt and ensure scalability, testability, reliability, and long-term maintainability. Implement tenant isolation (single-DB tenant-ID first, extensible to DB-per-tenant), vendor scoping within tenants, and end-to-end localization/internationalization across backend APIs, validation, messages, and frontend UI using native Laravel localization and Vue i18n with shared keys. Use thin controllers, transaction-safe services, repository interfaces, DTOs, policies, and tenant-aware global scopes. Avoid cross-module coupling; modules must communicate only via contracts/services. Implement production-grade security: HTTPS, encrypted data at rest, robust authentication (Laravel Sanctum), RBAC + ABAC authorization, strict input validation, rate limiting, structured logging, and immutable audit trails. Optimize for performance and reliability using tenant-aware caching (Redis), queues, idempotent APIs, eager-loading rules, and async jobs. Rely primarily on native framework features or only well-supported, stable, open-source LTS libraries. Avoid experimental or abandoned dependencies. Deliver a clean, extensible, future-proof SaaS foundation with modular backend structure, modular Vue frontend architecture, clear API contracts, and a testable codebase ready for CI/CD and long-term evolution.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to design and build a fresh, end-to-end, production-ready SaaS platform using Laravel 10+ for an industrial-grade, fully dynamic, customizable, and extensible Product, Inventory, and POS system (not a demo). Architect for long-term scalability and multi-industry use, supporting multi-tenancy with strict isolation, multi-vendor marketplaces, multi-branch operations, multi-currency transactions, and multiple pricing strategies suitable for retail, wholesale, pharmacy, manufacturing, restaurants, and marketplaces. Implement a Product vs SKU (variant) model where SKUs are the only sellable/stockable units, with unlimited variants, flexible attributes using normalized tables + PostgreSQL JSONB, and no frequent schema changes. Build a fully decoupled pricing engine with price history, context-aware rules (currency, region, customer group, quantity tiers, channels), and time-based validity. Implement ledger-based inventory (append-only stock movements, FIFO, batch/lot tracking, expiry, transfers, returns, reservations) with derived read models no mutable stock fields. Deliver an API-first, headless POS consuming the same pricing and inventory engines. Use a domain-driven, modular architecture (Tenancy, Identity, Catalog, Pricing, Inventory, POS, Extensions) with tenant-aware auth (tenant/vendor/branch), strict service-layer orchestration, domain events for all core actions, and a plugin/extension system without core code changes. Deliver a complete, ready-to-run solution with migrations, models, services, engines, APIs, seed data, and documentation, prioritizing correctness, security, extensibility, and maintainability using Clean Architecture, SOLID, DRY, and KISS principles.

---

## Act as a senior full-stack engineer and principal systems architect to design and build a fresh, end-to-end, production-ready SaaS platform using Laravel and PostgreSQL, delivering an industrial-grade, fully dynamic, extensible Product, Inventory, and POS system intended for real-world, large-scale use (not a demo or prototype). Architect the system for long-term scalability and multi-industry adoption (retail, wholesale, pharmacy, manufacturing, restaurants, marketplaces), supporting strict multi-tenant isolation, multi-vendor marketplaces, multi-branch operations (stores/warehouses), multi-currency, and multiple pricing strategies. Implement a Product vs SKU (Variant) domain model, where Product is abstract and SKU is the only sellable and stockable entity, supporting unlimited variants, dynamic attributes via a hybrid normalized + JSONB schema, and extensible attribute definitions without frequent migrations. Fully decouple pricing from products and SKUs using a dedicated pricing engine that supports price history, currency/region/customer-group rules, quantity tiers, sales channels, and time-based validity. Implement inventory using an append-only stock ledger (no mutable quantity fields) with full auditability, FIFO fulfillment, batch/lot tracking, expiry handling, transfers, returns, adjustments, and POS reservations, deriving read-optimized balances per SKU, batch, and branch. Build a headless, API-first POS that consumes the same pricing and inventory engines as all other channels. Use a modular, domain-driven architecture with strict separation of Tenancy, Identity, Catalog, Pricing, Inventory, POS, and Extensions, enforce tenant-aware RBAC/ABAC across tenant, vendor, and branch scopes, and ensure all core business actions emit domain events to support a plugin/extension system without modifying core code. Deliver a fully working solution including migrations, models, repositories, service layers, pricing and inventory engines, POS checkout flow, REST APIs, seed data, and documentation, prioritizing correctness, transactional integrity, security, extensibility, maintainability, and LTS readiness as if the platform will be used by thousands of businesses.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to design and implement a fresh, end-to-end, production-ready SaaS platform using Laravel and PostgreSQL for an industrial-grade, fully dynamic, extensible Product, Inventory, and POS system. Architect for long-term scalability and multi-industry use (retail, wholesale, pharmacy, manufacturing, restaurants, marketplaces) with strict multi-tenancy and tenant isolation, multi-vendor marketplaces, multi-branch stores/warehouses, multi-currency support, and flexible pricing strategies. Implement a Product vs SKU model where Product is abstract and SKU is the only sellable/stockable unit, supporting unlimited variants with dynamic attributes via hybrid normalized tables and JSONB. Fully decouple pricing into a dedicated pricing engine with price history, rule-based resolution (currency, region, customer group, quantity tiers, channel), and time validity. Design inventory using an append-only stock ledger (no mutable quantities), supporting FIFO, batches/lots, transfers, adjustments, returns, expiry tracking, reservations, and read-optimized derived balances. Build a headless, API-first POS consuming the same pricing and inventory engines. Use a modular, domain-driven architecture (Tenancy, Identity, Catalog, Pricing, Inventory, POS, Extensions) with Controller → Service → Repository pattern, tenant-aware auth (RBAC/ABAC), domain events for all core actions, and a plugin/extension system without core code modification. Deliver migrations, models, services, engines, POS flow, REST APIs, seed data, and documentation, prioritizing correctness, security, extensibility, maintainability, and LTS readiness over demo-level shortcuts.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect with deep, enterprise-level Laravel expertise to design and fully implement a production-ready, end-to-end, modular SaaS platform using Laravel (backend) and Vue.js (frontend, Vite), optionally leveraging Tailwind CSS and AdminLTE, architected strictly around Modular Architecture and the Controller → Service → Repository pattern in full alignment with Clean Architecture, SOLID, DRY, and KISS principles to ensure strict separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability; the system must support strict multi-tenancy with tenant isolation, multi-vendor and multi-branch operations, multi-language (i18n), multi-currency, and role- and attribute-based access control (RBAC/ABAC), with tenant-aware authentication, authorization, policies, and global scopes; all cross-module interactions must be orchestrated exclusively through service layers with explicitly defined transactional boundaries to guarantee atomic operations, consistent exception propagation, idempotency, and global rollback safety, while applying event-driven architecture for asynchronous workflows such as notifications, reporting, integrations, CRM automation, auditing, and extensions without compromising transactional consistency of core business flows; fully design and implement all core, supporting, and cross-cutting modules without omissions, including tenant and subscription management, authentication and authorization, users, roles and permissions, customers and vehicles, centralized vehicle service history across branches, appointments and bay scheduling, job cards and service workflows, inventory and procurement with append-only stock ledger and movements, invoicing, payments and taxation, CRM and customer engagement, fleet, telematics and preventive maintenance, reporting, analytics and KPI dashboards, configurations, integrations, notifications, logging, auditing, and system administration, supporting advanced capabilities such as meter readings, next-service tracking, vehicle ownership transfers, digital inspections, packaged services, dummy items, driver commissions, stock movements, and compliance reporting; enforce enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, validation, rate limiting, structured logging, immutable audit trails, and transactional integrity; expose clean, versioned REST APIs using native Laravel and Vue features or only stable, well-supported LTS open-source libraries; deliver a fully scaffolded, ready-to-run solution including database migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger (OpenAPI) documentation, and a modular Vue.js frontend with feature-based modules, routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive layouts, accessibility best practices, and professional theming, clearly demonstrating best practices for service orchestration, transaction management, exception handling, rollback strategies, caching, queues, and event-driven extensibility, resulting in a scalable, extensible, configurable, LTS-ready, and truly production-grade SaaS foundation capable of evolving into a full ERP ecosystem.

---

## Design and fully implement a production-ready modular SaaS using Laravel and Vue.js with strict Clean Architecture and Controller→Service→Repository pattern, supporting multi-tenancy, multi-vendor, multi-branch, RBAC/ABAC, i18n, event-driven workflows, transactional service orchestration, inventory ledger, invoicing, CRM, fleet, reporting, and ERP-grade security; deliver scaffolded backend, APIs, Swagger docs, and modular Vue frontend using only stable LTS tools.

---

## designed for complex operations (multiple locations, products, variations, prices, and batches) acts as a centralized command center to automate and streamline stock movement.

---

## An inventory management system (IMS) with support for complex needs such as multiple locations, products, variations, prices, and batches relies on centralized real-time tracking, automation, and advanced data analytics. These features provide comprehensive visibility and control over the entire supply chain.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to design and fully implement a production-ready, modular, ERP-grade SaaS platform using Laravel (backend) and Vue.js (frontend) that centralizes and integrates all core business applications CRM, eCommerce, billing, accounting, inventory, manufacturing, warehouse management, POS, project management, procurement, fleet, HR foundations, and reporting into a single unified system backed by a shared, real-time database that eliminates data silos and enables automation, visibility, and data-driven decision-making; architect the solution strictly using Modular Architecture and the Controller → Service → Repository pattern in full alignment with Clean Architecture, SOLID, DRY, and KISS principles to ensure strict separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability; support complex multi-tenant, multi-vendor, multi-branch, and multi-location operations with advanced ERP and inventory capabilities including real-time stock tracking, barcode/QR scanning, automated reordering, demand forecasting, batch/lot and serial number tracking, FEFO/FIFO rotation, kitting and bundling, pricing tiers, multi-currency costing, append-only inventory ledgers, stock transfers, and AI-driven analytics, while providing omnichannel integration across POS, eCommerce, accounting, and external systems; enforce service-layer-only orchestration with explicit transactional boundaries to guarantee atomic operations, consistent exception propagation, idempotency, and global rollback safety, while applying event-driven architecture for asynchronous workflows such as notifications, reporting, integrations, and automation without compromising transactional consistency of core business processes; implement enterprise-grade SaaS security including strict tenant isolation, RBAC and ABAC authorization, encryption, validation, rate limiting, structured logging, immutable audit trails, and compliance readiness; provide full backend and frontend localization and internationalization (i18n), cloud- and mobile-ready access, and role-based UI composition; expose clean, versioned REST APIs using only native Laravel and Vue capabilities or stable LTS open-source libraries; and deliver a fully scaffolded, ready-to-run solution including database schemas, migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, Swagger/OpenAPI documentation, and a modular, scalable Vue.js frontend with real-time dashboards, KPIs, reusable components, and predictable state management, resulting in a secure, extensible, enterprise-scale ERP foundation suitable for long-term production use and continuous evolution.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect with deep enterprise-level Laravel expertise to design and fully implement a production-ready, end-to-end, modular, ERP-grade SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, that serves vehicle service centers, auto repair garages, and broader enterprise use cases by unifying CRM, eCommerce, billing, accounting, inventory, manufacturing, warehouse management, POS, project management, procurement, fleet, telematics, HR foundations, and reporting into a single, shared, real-time system; architect the solution strictly around Modular Architecture and the Controller → Service → Repository pattern in full alignment with Clean Architecture, SOLID, DRY, and KISS principles to ensure strict separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability; support strict multi-tenancy with tenant isolation, multi-vendor and multi-branch operations, centralized and authoritative service and inventory histories across all locations, multi-currency and multi-language (i18n), and role- and attribute-based access control (RBAC/ABAC); enforce service-layer-only orchestration for all cross-module interactions with explicitly defined transactional boundaries to guarantee atomic operations, idempotency, consistent exception propagation, and global rollback safety, while applying event-driven architecture for asynchronous workflows such as notifications, reporting, CRM automation, integrations, auditing, and extensions without compromising transactional consistency of core business processes; fully implement advanced ERP and inventory capabilities including real-time stock tracking, barcode/QR scanning, automated reordering, demand forecasting, batch/lot and serial tracking, FEFO/FIFO logic, kitting and bundling, pricing tiers, multi-currency costing, append-only inventory ledgers, stock transfers, reservations, and AI-ready analytics; deliver complete business modules covering authentication and authorization, tenant and subscription management, users, roles and permissions, customers and vehicles, appointments and bay scheduling, job cards and service workflows, inventory and procurement, invoicing, payments and taxation, CRM and customer engagement, fleet and preventive maintenance, reporting, analytics and KPI dashboards, configurations, integrations, notifications, logging, auditing, and system administration; enforce enterprise-grade SaaS security including HTTPS, encryption at rest, secure credential storage, validation, rate limiting, structured logging, immutable audit trails, and compliance readiness; expose clean, versioned REST APIs using only native Laravel and Vue features or stable, well-supported LTS open-source libraries; and deliver a fully scaffolded, ready-to-run solution including database schemas, migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, Swagger/OpenAPI documentation, and a modular, scalable Vue.js frontend with feature-based modules, routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive layouts, accessibility best practices, and real-time dashboards resulting in a secure, extensible, LTS-ready, and truly production-grade SaaS foundation capable of evolving into a full enterprise ERP ecosystem.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect with deep, enterprise-level Laravel expertise to design and fully implement a production-ready, modular, ERP-grade SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, architected strictly around Modular Architecture and the Controller → Service → Repository pattern in full alignment with Clean Architecture, SOLID, DRY, and KISS principles to ensure strict separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability. The system must support strict multi-tenancy with tenant isolation, multi-vendor and multi-branch operations, multi-language (i18n), multi-currency, and fine-grained RBAC and ABAC authorization, with tenant-aware authentication, policies, and global scopes. Centralize and integrate all core business domains including authentication and subscriptions, CRM, customers and vehicles, centralized cross-branch service history, appointments and bay scheduling, job cards and service workflows, inventory and procurement with append-only stock ledger and movements, pricing engines, invoicing, payments and taxation, POS, eCommerce, fleet, telematics and preventive maintenance, manufacturing and warehouse operations, HR foundations, reporting, analytics and KPI dashboards, configurations, integrations, notifications, logging, auditing, and system administration into a single unified platform backed by a shared, real-time database that eliminates data silos and enables automation, visibility, and data-driven decision-making. Enforce service-layer-only orchestration for all cross-module interactions with explicitly defined transactional boundaries to guarantee atomic operations, idempotency, consistent exception propagation, and global rollback safety, while applying event-driven architecture for asynchronous workflows such as notifications, reporting, integrations, CRM automation, auditing, and extensibility without compromising transactional consistency of core business processes. Implement advanced ERP and inventory capabilities including real-time multi-location stock tracking, barcode/QR scanning, automated reordering, demand forecasting, batch/lot and serial tracking, FEFO/FIFO rotation, kitting and bundling, pricing tiers, multi-currency costing, inventory valuation, stock transfers, reservations, and analytics. Enforce enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, immutable audit trails, and compliance readiness. Expose clean, versioned REST APIs using only native Laravel and Vue features or stable, well-supported LTS open-source libraries, and deliver a fully scaffolded, ready-to-run solution including database schemas, migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, Swagger/OpenAPI documentation, and a modular Vue.js frontend with feature-based modules, routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive layouts, accessibility best practices, and professional theming resulting in a scalable, extensible, configurable, LTS-ready, and truly production-grade SaaS foundation capable of evolving into a full ERP ecosystem.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to design and implement a production-ready, modular, ERP-grade SaaS using Laravel (backend) and Vue.js with Vite (frontend). Enforce Clean Architecture, Modular Architecture, and Controller→Service→Repository with SOLID, DRY, and KISS. Support strict multi-tenancy, multi-vendor, multi-branch, RBAC/ABAC, i18n, multi-currency, and tenant-aware auth. Centralize CRM, inventory (append-only ledger), POS, billing, fleet, reporting, and admin. Orchestrate all cross-module logic via transactional services with idempotency and rollback safety, use event-driven workflows, expose versioned REST APIs, apply enterprise SaaS security, and deliver a fully scaffolded, LTS-ready backend, Swagger docs, and modular Vue frontend.

---

## Inventory management systems that handle multi-variant items, batch/lot tracking, and multiple price lists are designed for complex retail, wholesale, and manufacturing operations. These systems ensure accurate traceability (FIFO/expiry), precise stock levels for variations (size/color), and tiered pricing for different customer segments.

---

## Managing inventory with multiple variants, batches (lot tracking), and multiple prices requires a robust system capable of handling granular data, such as an ERP (e.g., SAP, ERPNext) or advanced inventory software. Key strategies include using variant configuration to define products, split valuation or batch-wise pricing for cost/price variations, and CSV imports/API integrations for mass updates.

---

## Act as a Senior Backend Engineer and Systems Architect to observe and reconcile all requirements and design and implement a production-ready, reusable backend CRUD framework that is fully dynamic, customizable, and extensible, strictly aligned with Clean Architecture and the Controller → Service → Repository pattern; the CRUD layer must support advanced, configurable capabilities including global and field-level search, filtering (including relation-based filters), pagination, multi-field sorting, sparse field selection, and optional eager loading of relations with selectable fields, while remaining tenant-aware, secure, and scalable; ensure all query behavior is configuration-driven rather than hardcoded, all business logic and transactions are handled exclusively in the service layer, repositories encapsulate data access only, and the solution is optimized for long-term maintainability, minimal technical debt, and seamless reuse across ERP-grade SaaS modules and autonomous AI development workflows.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to review all documents and requirements and design and implement a production-ready, modular, ERP-grade SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), strictly enforcing Clean Architecture, Modular Architecture, the Controller→Service→Repository pattern, and SOLID, DRY, and KISS principles to ensure scalability, maintainability, and minimal technical debt; build a secure, tenant-aware foundation supporting multi-tenancy, multi-vendor, multi-branch, multi-language (i18n), multi-currency, and multi-unit operations with fine-grained RBAC/ABAC authorization and tenant-aware authentication; implement core ERP and base backend modules including IAM, tenants, organizations, users, roles, configurations, master data, CRM, inventory, POS, billing, fleet, and analytics, with service-layer transactional orchestration, clearly defined boundaries, and event-driven workflows for extensibility; expose clean, versioned REST APIs, enforce enterprise-grade SaaS security standards, and deliver a fully scaffolded backend with migrations, services, repositories, and Swagger/OpenAPI documentation, along with a modular, LTS-ready Vue.js frontend optimized for long-term production use.

---

## Inventory management systems that support multi-variant products, batch or lot tracking, and multiple price lists are built for complex retail, wholesale, and manufacturing environments, enabling accurate stock visibility per variant (such as size or color), full traceability through FIFO or expiry-based controls, and tiered or customer-specific pricing; achieving this requires a robust, ERP-grade design that models products using structured variant configurations, manages inventory at batch or lot level with batch-wise costing and valuation, supports multiple price lists and pricing rules per customer segment or channel, and leverages scalable mechanisms such as CSV imports and well-defined APIs for bulk updates and integrations, as commonly seen in mature platforms like SAP or ERPNext.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to design and implement a production-ready, ERP-grade inventory management system within a modular SaaS architecture, capable of handling multi-variant products (e.g., size, color), batch/lot tracking with FIFO and expiry control, and multiple price lists for different customer segments, channels, and cost structures; architect the solution using Laravel (backend) and Vue.js with Vite (frontend), strictly following Clean Architecture, Modular Architecture, the Controller→Service→Repository pattern, and SOLID, DRY, and KISS principles; model products with robust variant configuration, manage inventory at batch level with batch-wise costing and valuation, support tiered and dynamic pricing rules, and ensure precise, real-time stock levels across operations; enable scalable bulk operations via CSV imports and well-defined, versioned REST APIs; apply service-layer transactional orchestration, event-driven workflows, and enterprise-grade SaaS security; and deliver a fully scaffolded backend with migrations, services, repositories, Swagger/OpenAPI documentation, and a modular, LTS-ready Vue.js frontend.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to review, reconcile, and implement all provided requirements without omission into a single, production-ready, ERP-grade modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly enforcing Clean Architecture, Modular Architecture, Controller → Service → Repository, and SOLID, DRY, KISS principles to ensure scalability, performance, testability, and minimal technical debt; design a secure, tenant-aware foundation with strict multi-tenancy and isolation, multi-vendor, multi-branch, multi-language (i18n), multi-currency, multi-unit, and fine-grained RBAC/ABAC with tenant-aware authentication, policies, and global scopes; fully implement and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, customers and vehicles with centralized cross-branch histories, appointments and scheduling, job cards and workflows, inventory using an append-only stock ledger with SKU/variant modeling, batch/lot and expiry tracking (FIFO/FEFO), multiple price lists and pricing rules, procurement, POS, invoicing, payments and taxation, fleet and preventive maintenance, manufacturing and warehouse operations, reporting, analytics and KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and rollback safety, complemented by event-driven workflows for asynchronous processes without compromising transactional consistency; expose clean, versioned REST APIs, support bulk operations via CSV and APIs, apply enterprise-grade SaaS security (HTTPS, encryption at rest, validation, rate limiting, structured logging, immutable audits), rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, LTS-ready solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, background jobs, Swagger/OpenAPI documentation, and a modular, scalable Vue frontend with routing, state management, localization, permission-aware UI composition, reusable components, and responsive, accessible layouts.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to comprehensively review, reconcile, and implement all requirements into a single, production-ready, ERP-grade modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly enforcing Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern in full alignment with SOLID, DRY, and KISS principles to ensure scalability, performance, testability, and minimal technical debt; design a secure, tenant-aware foundation with strict multi-tenancy and isolation, multi-vendor and multi-branch operations, multi-language (i18n), multi-currency, multi-unit support, and fine-grained RBAC and ABAC with tenant-aware authentication, policies, and global scopes; fully implement and integrate all core, ERP, and cross-cutting modules without omission, including IAM, tenant and subscription management, organizations, users, roles and permissions, configuration and master data, CRM, customers and vehicles with centralized cross-branch histories, appointments and scheduling, job cards and service workflows, inventory using an append-only stock ledger with SKU/variant modeling, batch/lot and expiry tracking (FIFO/FEFO), multiple price lists and pricing rules, procurement, POS, invoicing, payments and taxation, fleet and preventive maintenance, manufacturing and warehouse operations, reporting, analytics and KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all business logic and cross-module interactions with explicitly defined transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and rollback safety, complemented by event-driven workflows for asynchronous processes without compromising transactional consistency; expose clean, versioned REST APIs, support bulk operations via CSV and APIs, apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, strict validation, rate limiting, structured logging, and immutable audit trails, rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, LTS-ready solution including migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, Swagger/OpenAPI documentation, and a modular, scalable Vue.js frontend with feature-based modules, routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming suitable for long-term evolution into a full enterprise ERP ecosystem.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to review, reconcile, and fully implement all provided functional and non-functional requirements—without omission—into a single, production-ready, ERP-grade modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE. Architect the system strictly using Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern, rigorously enforcing SOLID, DRY, and KISS principles to ensure strict separation of concerns, scalability, performance, testability, minimal technical debt, and long-term LTS maintainability. Design a secure, tenant-aware foundation supporting strict multi-tenancy with isolation, multi-vendor and multi-branch operations, multi-language (i18n), multi-currency, multi-unit handling, and fine-grained RBAC and ABAC authorization with tenant-aware authentication, policies, and global scopes. Fully design and implement all core, ERP, and cross-cutting modules, including IAM, tenants and subscriptions, organizations, users, roles and permissions, configurations and master data, CRM, customers and vehicles with centralized cross-branch histories, appointments and scheduling, job cards and service workflows, inventory using an append-only stock ledger with Product/SKU-variant modeling, batch/lot and serial tracking with FIFO/FEFO and expiry control, multiple price lists and rule-based pricing engines, procurement, POS, invoicing, payments and taxation, fleet and preventive maintenance, manufacturing and warehouse operations, reporting, analytics and KPI dashboards, notifications, integrations, logging, auditing, and system administration. Enforce service-layer-only orchestration for all cross-module interactions with explicitly defined transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and global rollback safety, while applying event-driven architecture for asynchronous workflows such as notifications, reporting, integrations, automation, auditing, and extensibility without compromising transactional consistency of core business processes. Expose clean, versioned REST APIs, support bulk operations via CSV imports and APIs, and apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, immutable audit trails, and compliance readiness, relying only on native framework capabilities or stable, well-supported LTS libraries. Deliver a fully scaffolded, ready-to-run solution including database schemas, migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a modular, scalable Vue.js frontend with feature-based modules, routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready, and truly production-grade SaaS foundation capable of evolving into a full enterprise ERP ecosystem.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to comprehensively review, reconcile, and implement all requirements into a single, production-ready, ERP-grade modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly enforcing Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern with full adherence to SOLID, DRY, and KISS principles for maximum separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability; design a secure, tenant-aware foundation supporting strict multi-tenancy with isolation, multi-vendor, multi-branch, multi-location, multi-language (i18n), multi-currency, and multi-unit operations with fine-grained RBAC and ABAC enforced through tenant-aware authentication, policies, guards, and global scopes; fully implement all core, ERP, and cross-cutting modules including IAM, tenant and subscription management, organizations, users, roles and permissions, configurations and master data, CRM, customers and vehicles with centralized cross-branch histories, appointments and bay scheduling, job cards and service workflows, inventory and procurement using append-only stock ledgers with SKU/variant modeling, batch/lot and serial tracking, FIFO/FEFO and expiry handling, pricing engines with multiple price lists, rule-based resolution and history, invoicing, payments, taxation, POS, eCommerce, fleet management, telematics, preventive maintenance, manufacturing and warehouse operations, reporting, analytics and KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and global rollback safety, while applying event-driven architecture exclusively for asynchronous workflows (notifications, reporting, CRM automation, integrations, auditing, extensibility) without compromising transactional consistency; expose clean, versioned REST APIs, support bulk operations via CSV and APIs, apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, immutable audit trails, and compliance readiness; rely only on native Laravel/Vue features or stable, well-supported LTS libraries, and deliver a fully scaffolded, ready-to-run solution including database schemas, migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a modular, scalable Vue frontend with feature-based modules, routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready, fully production-grade SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to review, reconcile, and implement all requirements into a single, production-ready, ERP-grade modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly following Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern with full adherence to SOLID, DRY, and KISS principles to ensure separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability. Design a secure, tenant-aware foundation supporting strict multi-tenancy with isolation, multi-vendor, multi-branch, multi-location, multi-language (i18n), multi-currency, and multi-unit operations, enforcing fine-grained RBAC and ABAC through tenant-aware authentication, policies, guards, and global scopes. Fully implement all core, ERP, and cross-cutting modules—including IAM, tenant and subscription management, organizations, users, roles and permissions, configurations and master data, CRM, customers and vehicles with cross-branch histories, appointments and bay scheduling, job cards and service workflows, inventory and procurement with append-only stock ledgers, SKU/variant modeling, batch/lot and serial tracking, FIFO/FEFO and expiry handling, pricing engines with multiple price lists and rule-based resolution, invoicing, payments, taxation, POS, eCommerce, fleet management, telematics, preventive maintenance, manufacturing and warehouse operations, reporting, analytics and KPI dashboards, notifications, integrations, logging, auditing, and system administration. Enforce service-layer-only orchestration for cross-module interactions with explicit transactional boundaries ensuring atomicity, idempotency, consistent exception propagation, and global rollback safety, while using event-driven architecture exclusively for asynchronous workflows without compromising transactional consistency. Expose clean, versioned REST APIs, support bulk operations via CSV and APIs, and apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, immutable audit trails, and compliance readiness. Deliver a fully scaffolded, ready-to-run solution including database schemas, migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a modular, scalable Vue frontend with feature-based modules, routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready, fully production-grade SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Generate a full production-ready, modular ERP-grade SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally using Tailwind CSS and AdminLTE, strictly following Clean Architecture, Modular Architecture, and Controller → Service → Repository patterns. Ensure full adherence to SOLID, DRY, KISS principles with separation of concerns, loose coupling, testability, minimal technical debt, and long-term maintainability. Implement multi-tenancy with strict isolation, multi-vendor, multi-branch, multi-location, multi-language (i18n), multi-currency, and multi-unit support, enforcing RBAC and ABAC with tenant-aware authentication, policies, guards, and global scopes. Build all modules, including IAM, tenants & subscriptions, organizations, users, roles & permissions, master data, CRM, customers & vehicles, appointments & bay scheduling, job cards & service workflows, inventory & procurement (append-only ledgers, SKU/variant modeling, batch/lot/serial tracking, FIFO/FEFO, expiry handling), pricing engine (multiple price lists, rule-based resolution, history), invoicing, payments, taxation, POS, eCommerce, fleet management, telematics, preventive maintenance, manufacturing & warehouse operations, reporting & dashboards, notifications, integrations, logging, auditing, and system administration. Use service-layer-only orchestration for cross-module interactions with explicit transactional boundaries ensuring atomicity, idempotency, consistent exception propagation, and rollback safety. Apply event-driven architecture exclusively for asynchronous workflows (notifications, reporting, CRM automation, integrations, auditing) without affecting transactional consistency. Expose versioned REST APIs, support bulk CSV/API operations, and enforce enterprise SaaS security: HTTPS, encryption at rest, secure credentials, validation, rate limiting, structured logging, immutable audit trails, compliance-ready. Scaffold database schemas, migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI docs, and a modular, scalable Vue frontend with feature-based modules, routing, centralized state, localization, permission-aware UI, reusable components, responsive accessible layouts, and professional theming. Deliver a secure, extensible, configurable, LTS-ready SaaS platform capable of evolving into a full enterprise ERP ecosystem.

---

## Act as a Full-Stack Engineer to comprehensively observe and analyze all available context—including repository state, commit history, logs, test output, CI annotations, environment configuration, and dependency graphs—in order to accurately diagnose failed checks; identify the precise root causes of failures such as test errors, broken assertions, migration issues, misconfigurations, environment or version mismatches, missing or incompatible dependencies, or nondeterministic behavior; apply only minimal, targeted, and well-justified code or configuration changes necessary to resolve the issues without refactoring or expanding scope; re-run the complete test and CI pipeline to verify all checks pass reliably; and prioritize correctness, determinism, repeatability, and long-term application stability over redesign or optimization.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, review, reconcile, implement, and deliver a fully production-ready, ERP-grade, modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure strong separation of concerns, loose coupling, scalability, performance, high testability, minimal technical debt, and long-term maintainability; build a secure, tenant-aware, strictly isolated multi-tenant foundation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully design and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, master data and configurations, CRM, centralized cross-branch histories, inventory and procurement using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and global rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails, rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready enterprise SaaS ERP platform.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, implement, and deliver a production-ready, modular ERP-grade SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, fully adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern, and following SOLID, DRY, and KISS principles to ensure maximal separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability. Refer to all provided documents and data to implement all required core, ERP, and cross-cutting modules, including IAM, tenants and subscriptions, organizations, users, roles and permissions, master data/configurations, inventory and procurement with append-only stock ledgers, SKU/variant modeling, batch/lot/serial tracking, FIFO/FEFO and expiry handling, pricing items with multiple price lists, invoicing, payments, taxation, POS, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration. Enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries, atomicity, idempotency, consistent exception propagation, and global rollback safety, while applying event-driven architecture exclusively for asynchronous workflows. Build a tenant-aware, multi-branch, multi-location, multi-currency, multi-language, multi-unit SaaS with fine-grained RBAC/ABAC, enforced through authentication, policies, guards, and global scopes. Expose versioned REST APIs, support bulk CSV/API operations, and apply enterprise-grade SaaS security standards including HTTPS, encryption, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails. Deliver a fully scaffolded, ready-to-run solution including migrations, models, repositories, DTOs, services, controllers, middleware, policies, events/listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready, fully production-grade SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to review, reconcile, and implement all provided requirements without omission into a single, production-ready, ERP-grade modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly enforcing Clean Architecture, Modular Architecture, Controller → Service → Repository, and SOLID, DRY, KISS principles to ensure scalability, performance, testability, and minimal technical debt; design a secure, tenant-aware foundation with strict multi-tenancy and isolation, multi-vendor, multi-branch, multi-language (i18n), multi-currency, multi-unit, and fine-grained RBAC/ABAC with tenant-aware authentication, policies, and global scopes; fully implement and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory using an append-only stock ledger with SKU/variant modeling, batch/lot and expiry tracking (FIFO/FEFO), multiple price lists and pricing rules, procurement, POS, invoicing, payments and taxation, manufacturing and warehouse operations, reporting, analytics and KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and rollback safety, complemented by event-driven workflows for asynchronous processes without compromising transactional consistency; expose clean, versioned REST APIs, support bulk operations via CSV and APIs, apply enterprise-grade SaaS security (HTTPS, encryption at rest, validation, rate limiting, structured logging, immutable audits), rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, LTS-ready solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, background jobs, Swagger/OpenAPI documentation, and a modular, scalable Vue frontend with routing, state management, localization, permission-aware UI composition, reusable components, and responsive, accessible layouts.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, review, reconcile, and deliver a fully production-ready, ERP-grade, modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure strong separation of concerns, loose coupling, high testability, scalability, performance, and minimal technical debt; implement a secure, tenant-aware, multi-tenant SaaS foundation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully design and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, procurement, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries ensuring atomicity, idempotency, consistent exception propagation, and global rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards (HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, immutable audit trails), rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run solution including migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a Principal Systems Architect and Full-Stack Engineer to implement a production-ready, ERP-grade modular SaaS using Laravel and Vue.js (Vite), strictly following Clean Architecture, Modular Architecture, Controller→Service→Repository, and SOLID/DRY/KISS; enforce strict multi-tenancy with tenant isolation, multi-org/vendor/branch/location/currency/language/unit support, RBAC/ABAC via policies and global scopes; implement IAM, subscriptions, master data, CRM, inventory with append-only stock ledger (SKU/variants, batch/lot/serial, FIFO/FEFO), pricing rules, procurement, POS, invoicing, payments, taxation, manufacturing, warehouse, reporting, analytics, notifications, integrations, logging, auditing, and admin; orchestrate cross-module logic only in services with transactional boundaries, idempotency, rollback safety, and event-driven async workflows; expose versioned REST APIs with bulk ops, apply enterprise SaaS security, and deliver fully scaffolded backend and modular, permission-aware Vue frontend.

---

## Act as a senior Full-Stack Engineer and Principal Architect building a production-ready, enterprise-grade, modular ERP SaaS using Laravel and Vue (Vite), following Clean Architecture, modular design, and Controller → Service → Repository with SOLID/DRY/KISS; enforce strict multi-tenancy with isolation and support multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language, and multi-unit operations with fine-grained RBAC/ABAC via policies, guards, and global scopes; implement all core and ERP modules (IAM, tenants/subscriptions, users/roles, master data, CRM, inventory with append-only stock ledgers, SKU/variants, batch/lot/expiry FIFO/FEFO, pricing and price lists, procurement, POS, invoicing, payments/tax, manufacturing, warehouse, reporting, analytics, notifications, integrations, logging, auditing, admin); enforce service-layer-only orchestration with explicit transactions (atomic, idempotent, rollback-safe) and event-driven async workflows; expose versioned REST APIs with bulk operations; apply enterprise SaaS security; deliver a fully scaffolded, LTS-ready backend and modular, permission-aware Vue frontend.

---

## Act as a senior Full-Stack Engineer and Principal Architect to design, implement, and deliver a fully production-ready, enterprise-grade, modular ERP SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly following Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles; build a secure, tenant-aware foundation with strict multi-tenancy, isolation, and support for multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully implement all core and ERP modules including IAM, tenants/subscriptions, organizations, users/roles/permissions, configuration/master data, CRM, inventory with append-only stock ledgers, SKU/variant modeling, batch/lot/serial tracking, FIFO/FEFO, expiry handling, pricing with multiple price lists/rules, procurement, POS, invoicing, payments/tax, eCommerce, telematics, manufacturing, warehouse operations, reporting, analytics/KPIs, notifications, integrations, logging, auditing, and administration; enforce service-layer-only orchestration with explicit transactional boundaries ensuring atomicity, idempotency, rollback safety, and consistent exception handling, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations; apply enterprise-grade SaaS security including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails; and deliver a fully scaffolded, LTS-ready backend and modular, permission-aware, responsive, localized, and feature-based Vue frontend—resulting in a secure, extensible, configurable ERP SaaS platform capable of evolving into a complete enterprise ecosystem.

---

## Act as a senior Full-Stack Engineer and Principal Systems Architect to design, implement, and deliver a fully production-ready, enterprise-grade, modular ERP SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly following Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure loose coupling, high testability, scalability, performance, minimal technical debt, and long-term maintainability; design a secure, tenant-aware SaaS foundation supporting strict multi-tenancy and isolation across multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit environments with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully implement and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, procurement, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries ensuring atomicity, idempotency, consistent exception propagation, and rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails, rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, review, reconcile, implement, and deliver a fully production-ready, ERP-grade, modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure strong separation of concerns, loose coupling, scalability, performance, high testability, minimal technical debt, and long-term maintainability; build a secure, tenant-aware, strictly isolated multi-tenant foundation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully design and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, master data and configurations, CRM, centralized cross-branch histories, inventory and procurement using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and global rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails, rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready enterprise SaaS ERP platform.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, implement, and deliver a production-ready, modular ERP-grade SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, fully adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern, and following SOLID, DRY, and KISS principles to ensure maximal separation of concerns, loose coupling, high testability, minimal technical debt, and long-term maintainability. Refer to all provided documents and data to implement all required core, ERP, and cross-cutting modules, including IAM, tenants and subscriptions, organizations, users, roles and permissions, master data/configurations, inventory and procurement with append-only stock ledgers, SKU/variant modeling, batch/lot/serial tracking, FIFO/FEFO and expiry handling, pricing items with multiple price lists, invoicing, payments, taxation, POS, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration. Enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries, atomicity, idempotency, consistent exception propagation, and global rollback safety, while applying event-driven architecture exclusively for asynchronous workflows. Build a tenant-aware, multi-branch, multi-location, multi-currency, multi-language, multi-unit SaaS with fine-grained RBAC/ABAC, enforced through authentication, policies, guards, and global scopes. Expose versioned REST APIs, support bulk CSV/API operations, and apply enterprise-grade SaaS security standards including HTTPS, encryption, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails. Deliver a fully scaffolded, ready-to-run solution including migrations, models, repositories, DTOs, services, controllers, middleware, policies, events/listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready, fully production-grade SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to review, reconcile, and implement all provided requirements without omission into a single, production-ready, ERP-grade modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly enforcing Clean Architecture, Modular Architecture, Controller → Service → Repository, and SOLID, DRY, KISS principles to ensure scalability, performance, testability, and minimal technical debt; design a secure, tenant-aware foundation with strict multi-tenancy and isolation, multi-vendor, multi-branch, multi-language (i18n), multi-currency, multi-unit, and fine-grained RBAC/ABAC with tenant-aware authentication, policies, and global scopes; fully implement and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory using an append-only stock ledger with SKU/variant modeling, batch/lot and expiry tracking (FIFO/FEFO), multiple price lists and pricing rules, procurement, POS, invoicing, payments and taxation, manufacturing and warehouse operations, reporting, analytics and KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and rollback safety, complemented by event-driven workflows for asynchronous processes without compromising transactional consistency; expose clean, versioned REST APIs, support bulk operations via CSV and APIs, apply enterprise-grade SaaS security (HTTPS, encryption at rest, validation, rate limiting, structured logging, immutable audits), rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, LTS-ready solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, background jobs, Swagger/OpenAPI documentation, and a modular, scalable Vue frontend with routing, state management, localization, permission-aware UI composition, reusable components, and responsive, accessible layouts.

---

## Act as a Full-Stack Engineer and Principal Systems Architect to design, review, reconcile, and deliver a fully production-ready, ERP-grade, modular SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure strong separation of concerns, loose coupling, high testability, scalability, performance, and minimal technical debt; implement a secure, tenant-aware, multi-tenant SaaS foundation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully design and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, procurement, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries ensuring atomicity, idempotency, consistent exception propagation, and global rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards (HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, immutable audit trails), rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run solution including migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable, LTS-ready SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a senior Full-Stack Engineer and Principal Systems Architect to design, review, reconcile, implement, and deliver a fully production-ready, enterprise-grade, modular ERP SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure strict separation of concerns, loose coupling, high testability, scalability, performance, minimal technical debt, and long-term maintainability; architect a secure, tenant-aware SaaS foundation with strict multi-tenancy and isolation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations, with fine-grained RBAC/ABAC enforced through authentication, policies, guards, and global scopes; fully design and integrate all core, ERP, and cross-cutting modules including IAM, tenants and subscriptions, organizations, users, roles and permissions, configuration and master data, CRM, centralized cross-branch histories, inventory and procurement using append-only stock ledgers with SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists and rules, POS, invoicing, payments and taxation, eCommerce, telematics, manufacturing and warehouse operations, reporting, analytics, KPI dashboards, notifications, integrations, logging, auditing, and system administration; enforce service-layer-only orchestration for all cross-module interactions with explicit transactional boundaries guaranteeing atomicity, idempotency, consistent exception propagation, and global rollback safety, while using event-driven architecture exclusively for asynchronous workflows; expose clean, versioned REST APIs with bulk CSV/API operations, apply enterprise-grade SaaS security standards including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails, rely only on native framework features or stable LTS libraries, and deliver a fully scaffolded, ready-to-run, LTS-ready solution with migrations, seeders, models, repositories, DTOs, services, controllers, middleware, policies, events, listeners, background jobs, notifications, Swagger/OpenAPI documentation, and a feature-based, modular Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, and professional theming—resulting in a secure, extensible, configurable SaaS platform capable of evolving into a complete enterprise ERP ecosystem.

---

## Act as a Senior Full-Stack Engineer and Principal Systems Architect to design, reconcile, implement, and deliver a fully production-ready, enterprise-grade, modular ERP SaaS platform using Laravel (backend) and Vue.js with Vite (frontend), optionally leveraging Tailwind CSS and AdminLTE, strictly adhering to Clean Architecture, Modular Architecture, and the Controller → Service → Repository pattern while enforcing SOLID, DRY, and KISS principles to ensure separation of concerns, loose coupling, high testability, scalability, performance, minimal technical debt, and long-term maintainability; build a secure, tenant-aware foundation supporting strict multi-tenancy with isolation across multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations, with fine-grained RBAC/ABAC enforced via authentication, policies, guards, and global scopes; fully implement and integrate all core, ERP, and cross-cutting modules including IAM, tenants/subscriptions, organizations, users, roles/permissions, master data/configuration, CRM, inventory with append-only stock ledgers, SKU/variant modeling, batch/lot/serial and expiry tracking with FIFO/FEFO, pricing with multiple price lists/rules, procurement, POS, invoicing, payments/tax, eCommerce, telematics, manufacturing, warehouse operations, reporting, analytics/KPIs, notifications, integrations, logging, auditing, and administration; enforce service-layer-only orchestration with explicit transactional boundaries guaranteeing atomicity, idempotency, rollback safety, and consistent exception propagation, while using event-driven workflows exclusively for asynchronous processes; expose versioned REST APIs with bulk CSV/API operations; apply enterprise-grade SaaS security including HTTPS, encryption at rest, secure credential storage, strict validation, rate limiting, structured logging, and immutable audit trails; and deliver a fully scaffolded, LTS-ready backend and modular, feature-based Vue frontend with routing, centralized state management, localization, permission-aware UI composition, reusable components, responsive and accessible layouts, professional theming, and ready-to-run scaffolding—resulting in a secure, extensible, configurable ERP SaaS capable of evolving into a complete enterprise platform.

---

## Act as a senior Full-Stack Engineer and Principal Architect to build a production-ready, enterprise-grade, modular ERP SaaS using Laravel (backend) and Vue.js with Vite (frontend), following Clean Architecture, modular design, and Controller → Service → Repository with SOLID/DRY/KISS; enforce strict multi-tenancy and isolation supporting multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language (i18n), and multi-unit operations with fine-grained RBAC/ABAC via authentication, policies, guards, and global scopes; implement all core and ERP modules (IAM, tenants/subscriptions, users/roles, master data, CRM, inventory with append-only stock ledgers, SKU/variants, batch/lot/serial and expiry FIFO/FEFO, pricing and price lists, procurement, POS, invoicing, payments/tax, eCommerce, manufacturing, warehouse, reporting, analytics/KPIs, notifications, integrations, logging, auditing, admin); enforce service-layer-only orchestration with explicit transactional boundaries (atomic, idempotent, rollback-safe) and event-driven async workflows; expose clean, versioned REST APIs with bulk operations; apply enterprise SaaS security; deliver a fully scaffolded, LTS-ready backend and a modular, permission-aware, localized, responsive Vue frontend.

---

## Act as a senior Full-Stack Engineer and Principal Architect building a production-ready, enterprise-grade, modular ERP SaaS using Laravel and Vue (Vite), following Clean Architecture, modular design, and Controller → Service → Repository with SOLID/DRY/KISS; enforce strict multi-tenancy with isolation and support multi-organization, multi-vendor, multi-branch, multi-location, multi-currency, multi-language, and multi-unit operations with fine-grained RBAC/ABAC via policies, guards, and global scopes; implement all core and ERP modules (IAM, tenants/subscriptions, users/roles, master data, CRM, inventory with append-only stock ledgers, SKU/variants, batch/lot/expiry FIFO/FEFO, pricing and price lists, procurement, POS, invoicing, payments/tax, manufacturing, warehouse, reporting, analytics, notifications, integrations, logging, auditing, admin); enforce service-layer-only orchestration with explicit transactions (atomic, idempotent, rollback-safe) and event-driven async workflows; expose versioned REST APIs with bulk operations; apply enterprise SaaS security; deliver a fully scaffolded, LTS-ready backend and modular, permission-aware Vue frontend.
