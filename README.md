# Hi, I'm Max 👋

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1200&color=58A6FF&vCenter=true&width=640&lines=Backend+engineering+%C2%B7+Python+%26+PostgreSQL;One+hand+builds+it+%C2%B7+the+other+breaks+it;Idempotency+%C2%B7+retries+%C2%B7+failure+paths)](https://github.com/felzov)

I'm Max, a Computing student in London. I build backend projects in Python and PostgreSQL,
mostly around money: ledgers, transfers and bank statements, where a small bug means a wrong
balance.

I'm ambidextrous, and I code the same way: one hand builds the system, the other tries to break
it. Every project I make comes with a page on how it fails, and a test for each way.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Maksym_Krainii-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/maksym-krainii-148890341/)

## 🛠️ Tech stack

[![Stack](https://skillicons.dev/icons?i=python,fastapi,postgres,redis,rabbitmq,docker,githubactions,linux,git)](https://skillicons.dev)

**Python** · FastAPI · Pydantic · asyncio · **PostgreSQL** · SQLAlchemy 2.0 · Alembic · Redis ·
RabbitMQ · pytest · Hypothesis · Docker Compose · GitHub Actions · Linux

## 🚀 Featured projects

| Project | The hard part it solves |
|---|---|
| 🏦 [**banking-ledger-api**](https://github.com/felzov/banking-ledger-api) | A double-entry ledger where PostgreSQL enforces the rules: postings balance to zero or change nothing, parallel transfers neither deadlock nor overdraw, and a retried request never moves money twice |
| 📊 [**banking-transaction-analytics**](https://github.com/felzov/banking-transaction-analytics) | Imports messy bank statements from CSV or from the ledger: row-level errors that never leak personal data, safe re-imports, exact per-currency totals. 850+ tests |
| ⚙️ [**distributed-task-platform**](https://github.com/felzov/distributed-task-platform) | Background jobs through RabbitMQ with explicit failure behaviour: bounded retries with backoff, crashed-worker recovery, dead letters, and a test for each failure path |

## 💡 How I work

- **Correctness first.** A smaller feature that handles failure beats a bigger one that doesn't.
- **Tests that mean something:** duplicates, timeouts, concurrent writes, crashes.
- **Understanding over output.** I use AI tools to move faster, but I don't keep code I can't
  explain.

**Currently learning:** distributed systems · event streaming · database internals · observability
