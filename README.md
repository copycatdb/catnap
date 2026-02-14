# catnap 💤

Connection pooler for SQL Server. PgBouncer but it lands on its feet.

Part of [CopyCat](https://github.com/copycatdb) 🐱

## What is this?

A lightweight connection pooler that sits between your application and SQL Server. Maintains a pool of persistent TDS connections and hands them out to clients, dramatically reducing connection overhead.

```
App connections (hundreds) → catnap → SQL Server connections (tens)
```

## Why?

SQL Server connection establishment is expensive — TCP handshake, TLS negotiation, TDS login, authentication. Doing that per-request is like a cat jumping off the counter, landing, climbing back up, and jumping again. For every. Single. Query.

catnap keeps connections warm so your app doesnt have to wait.

## Modes

- **Session pooling** — one server connection per client session
- **Transaction pooling** — connection returned after each transaction (most common)
- **Statement pooling** — connection returned after each statement (aggressive)

## Status

🚧 Coming soon. Currently napping.

## Attribution

Inspired by [PgBouncer](https://github.com/pgbouncer/pgbouncer). A masterclass in doing one thing well. We woke up from our nap and decided to copy it.

## License

MIT
