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
