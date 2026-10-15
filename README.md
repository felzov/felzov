# Hi, I'm Max

**Computing student · Backend engineering · Python & PostgreSQL**

I'm a Computing student in London who likes understanding how systems behave when things go wrong — two requests hitting the same account at once, a retry that runs twice, a migration that half-applies. Most of my time goes into building backend projects that deal with exactly those problems, and into making sure I can explain every decision in them.

I'm looking for a **Software Engineering internship** where I can work on real backend systems with people who care about getting the details right.

---

## What I'm working on

### 🏦 [Banking Ledger API](https://github.com/felzov/banking-ledger-api)

A banking backend built around a double-entry ledger. The interesting part isn't the endpoints — it's keeping money correct:

- **Double-entry bookkeeping** — every transfer produces balanced ledger entries, so balances can always be reconstructed and checked
- **Atomic transfers** — PostgreSQL transactions ensure a transfer either fully happens or doesn't happen at all
- **Concurrency safety** — row-level locking to prevent race conditions when the same account is debited in parallel
- **Idempotency keys** — a retried request doesn't move money twice
- **Audit trail** — a record of what changed and why
- **Tests for failure paths**, not just the happy path

`Python` · `FastAPI` · `PostgreSQL` · `SQLAlchemy 2.0` · `Alembic` · `pytest` · `Docker` · `GitHub Actions`

### 📊 [Banking Transaction Analytics](https://github.com/felzov/banking-transaction-analytics)

Imports, validates and analyses bank-statement CSVs. Real exports are messy, so the focus is on handling bad input safely:

- **Exact money** — amounts stored as integer minor units, never floats
- **Row-level validation errors** — one bad row is reported clearly instead of failing the whole import
- **Parsing and normalisation** of inconsistent CSV formats into a clean PostgreSQL schema
- **Analytics API** for filtering and summarising transactions

`Python` · `FastAPI` · `PostgreSQL`

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
