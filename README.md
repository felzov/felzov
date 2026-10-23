# Hi, I'm Max

**Computing student · Backend engineering · Python & PostgreSQL**

I'm a Computing student in London who likes understanding how systems behave when things go wrong — two requests hitting the same account at once, a retry that runs twice, a migration that half-applies. Most of my time goes into building backend projects that deal with exactly those problems, and into making sure I can explain every decision in them.

I'm looking for a **Software Engineering internship** where I can work on real backend systems with people who care about getting the details right.

---

## Projects

The two projects below work together: the analytics service can take its transactions straight from the ledger API, checking every entry against the ledger's running balance before storing anything.

### 🏦 [Banking Ledger API](https://github.com/felzov/banking-ledger-api)

A banking backend built around a double-entry ledger. The interesting part isn't the endpoints — it's keeping money correct:

- **Double-entry bookkeeping** — every posting produces balanced ledger entries, so balances can always be reconstructed and checked
- **Atomic transfers** — a transfer either fully happens or doesn't happen at all
- **Concurrency safety** — accounts are locked in a fixed order (`SELECT … FOR UPDATE`), so parallel transfers can't deadlock each other; deadlocks and serialization failures are retried
- **Idempotency keys** — a retried request never moves money twice, even when the outcome of a `COMMIT` is unknown
- **Append-only audit trail** — every attempt is recorded, successful or not
- **Authentication and ownership** — Argon2id password login, short-lived bearer tokens, and least-privilege database roles
- **Tests for failure paths** — database outages answer `503`, and cancelled requests are tested to leave the ledger consistent

_Status: final phase in progress — rate limiting and structured logging still to come._

`Python` · `FastAPI` · `PostgreSQL` · `SQLAlchemy 2.0` · `Alembic` · `pytest` · `Docker` · `GitHub Actions`

### 📊 [Banking Transaction Analytics](https://github.com/felzov/banking-transaction-analytics)

Imports, validates and analyses bank statements, from CSV uploads or from the ledger API. Real data is messy, so the focus is on handling bad input safely:

- **Exact money** — amounts stored as integer minor units, never floats, never rounded
- **Row-level validation errors** — one bad row is reported clearly instead of failing the whole import, and errors never echo personal financial data
- **Safe re-imports** — rows an account already holds are skipped and counted, enforced by a unique constraint in PostgreSQL
- **Per-currency analytics** — inflow, outflow and net per currency and month; different currencies are never added together
- **Ownership everywhere** — hashed API tokens, and every query scoped to its owner
- **Ready to run on a server** — readiness probe, per-client rate limiting, database timeouts, and 10 architecture decision records explaining the trade-offs
- **850+ tests**, including integration tests against a real PostgreSQL in CI

_Status: complete — all eight planned phases built._

`Python` · `FastAPI` · `PostgreSQL` · `SQLAlchemy 2.0 (async)` · `Alembic` · `pytest` · `GitHub Actions`

---

## Tech I use

[![Skills](https://skillicons.dev/icons?i=python,fastapi,postgres,redis,docker,git,github,linux)](https://skillicons.dev)

- **Backend:** Python, FastAPI, Pydantic, async Python, REST API design
- **Data:** PostgreSQL, SQL, SQLAlchemy 2.0, Alembic, Redis
- **Testing & quality:** pytest, pytest-asyncio, Ruff
- **Infrastructure:** Docker, Docker Compose, GitHub Actions, Linux

---

## How I like to work

- **Correctness first.** I'd rather ship a smaller feature that handles failure properly than a bigger one that doesn't.
- **Tests that mean something.** Especially for the cases that are easy to forget: duplicates, timeouts, concurrent writes.
- **Understanding over output.** I use AI tools to move faster, but I don't keep code I can't explain.

---

## Currently learning

Distributed systems fundamentals · message queues and event streaming · database internals and query performance · observability

---

## Get in touch

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Maksym_Krainii-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/maksym-krainii-148890341/)

Happy to chat about backend engineering, internships, or anything in my repos.
