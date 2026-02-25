# ErpOpenSource

An open source ERP built with a production-ready microservices architecture.

Built for developers who want to understand how to construct an enterprise system — with the same architectural decisions used in real-world projects.

---

## What we're building

A modular ERP platform where every business domain is an independent, observable, and deployable microservice.

```
Clients
  └──► API Gateway (Spring Cloud Gateway)
           ├──► Auth Service
           ├──► Sales Service
           ├──► Inventory Service
           └──► ... (one repo per module)

Observability (shared infrastructure)
  └── OTel Collector · Grafana Tempo · Prometheus · Grafana · Loki
```

---

## Repositories

| Repository | Description |
|---|---|
| [erp-api-gateway](https://github.com/ErpOpenSource/erp-api-gateway) | Single entry point. Routes traffic, propagates X-Request-Id, emits structured logs and traces. |
| [erp-observability-platform](https://github.com/ErpOpenSource/erp-observability-platform) | Full observability stack: metrics, traces, and logs in one `docker compose up`. |

---

## Design principles

- **One service, one repository** — each ERP module lives in its own repo with its own CI pipeline
- **Observable from day one** — every service ships with Prometheus metrics, OpenTelemetry traces, and structured JSON logs
- **Infrastructure as code** — everything runs with Docker Compose; no manual setup
- **Developer-first documentation** — architecture decisions are documented alongside the code

---

## Getting started

Clone the platform docs repository and follow the installation guide:

```bash
git clone https://github.com/ErpOpenSource/erp-platform
```

→ [Full installation guide](https://github.com/ErpOpenSource/erp-platform/blob/main/docs/INSTALLATION.md)
→ [Services reference](https://github.com/ErpOpenSource/erp-platform/blob/main/docs/SERVICES.md)
→ [How to add a new module](https://github.com/ErpOpenSource/erp-platform/blob/main/docs/NEW_MODULE.md)

---

## Tech stack

Java 21 · Spring Boot 3 · Spring Cloud Gateway · OpenTelemetry · Prometheus · Grafana · Docker · GitHub Actions

---

## Contributing

All repositories welcome contributions. Open an issue or a pull request in the relevant repo.
Branch convention: `feat/<scope>-<description>` · `fix/<scope>-<description>`

---

*Building in public. Every architectural decision is documented.*
