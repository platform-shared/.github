<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/platform-shared/.github/raw/main/profile/banner-dark.png?v=2">
  <source media="(prefers-color-scheme: light)" srcset="https://github.com/platform-shared/.github/raw/main/profile/banner-light.png?v=2">
  <img alt="Platform.Shared — building blocks for .NET microservices" src="https://github.com/platform-shared/.github/raw/main/profile/banner-dark.png?v=2">
</picture>

The plumbing every service needs, written and proven once: a service brings its domain, these libraries bring the
rest. They know no product — capabilities only, never a domain feature.

| Package | What it gives a service |
|---|---|
| `Platform.Shared.Kernel` | Entities and aggregates, domain events, UUIDv7 keys, results and typed domain errors, the one JSON policy, the contract of a list (pages, cursors, sorts) |
| `Platform.Shared.Contracts` | The envelope of an integration event: its id, its time, the trace it belongs to |
| `Platform.Shared.Validation` | The checks of a list request in the application layer: its page, its cursor, its search text — a bad one is a 400 under its field |
| `Platform.Shared.Infrastructure` | EF Core on PostgreSQL: one save per command, the outbox, audit and soft-delete, every aggregate's optimistic concurrency, lists read by keyset or page, the database checked at start, scheduled jobs |
| `Platform.Shared.Web` | One error contract (ProblemDetails with an error code and the trace), readiness a container's health check can ask, rate limits, request logs, settings from an environment file |
| `Platform.Shared.Security` | JWT bearer sign-in, every route closed unless it says it is open, the caller's id read in one place, scopes, the admin policy |
| `Platform.Shared.Messaging` | MassTransit on RabbitMQ: retries, the inbox and the outbox (a service that only consumes gets the inbox alone), one trace across the broker |
| `Platform.Shared.Caching` | Redis as a best-effort cache: it speeds a read up and never fails one; an entry is read only in the shape it was written in, and a read never puts back a value a write replaced meanwhile |
| `Platform.Shared.Storage` | Any S3-compatible object storage, its buckets made at start |
| `Platform.Shared.Bff` | A backend-for-frontend in a few calls: the sign-in by Authorization Code + PKCE, the session in Redis behind a random secret in an HttpOnly cookie, the access token refreshed in silence — one refresh per session at a time, its expiry never guessed — and attached to every proxied request, CSRF, the sign-out with revocation |
| `Platform.Shared.Testing` | The test kit: containers at the stack's own versions, a quiet step log, an OpenID Connect stand-in, the checks of a list's index, a schema, the settings and who may call each route, a check that names every problem it finds, a test host's requests from a proxy's address |
| `Platform.Shared.Build` | The shared checks every project of a repository builds under: the analyzers, every warning an error, the banned APIs, the dependency rule of a service's layers, the audit of vulnerable packages, the secret scanner's rules |

**Proven where it lives:** retries and the outbox on a real broker, the trace across it, the cache's failure, the
database's collation, the body limit on a real Kestrel, a lost concurrent change refused, a BFF's sign-in, refresh and
sign-out against an OpenID Connect stand-in — each tested here once, so a service tests only its own configuration.

Versioned together (one version for every package), published to GitHub Packages, each version's notes on the
repository's Releases page.

### Status

The repository is private for now and opens together with the platform.
