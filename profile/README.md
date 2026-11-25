<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://github.com/platform-shared/.github/raw/main/profile/banner-dark.png">
  <source media="(prefers-color-scheme: light)" srcset="https://github.com/platform-shared/.github/raw/main/profile/banner-light.png">
  <img alt="Platform.Shared — building blocks for .NET microservices" src="https://github.com/platform-shared/.github/raw/main/profile/banner-dark.png">
</picture>

The plumbing every service needs, written and proven once: a service brings its domain, these libraries bring the
rest. They know no product — capabilities only, never a domain feature.

| Package | What it gives a service |
|---|---|
| `Platform.Shared.Kernel` | Entities and aggregates, domain events, UUIDv7 keys, results and typed domain errors |
| `Platform.Shared.Contracts` | The envelope of an integration event: its id, its time, the trace it belongs to |
| `Platform.Shared.Validation` | The rules of a list: pages, cursors, and the filters and sorts a list allows |
| `Platform.Shared.Infrastructure` | EF Core on PostgreSQL: one save per command, the outbox, audit and soft-delete, the database checked at start, scheduled jobs |
| `Platform.Shared.Web` | One error contract (ProblemDetails with an error code and the trace), readiness a container's health check can ask, rate limits, request logs, settings from an environment file |
| `Platform.Shared.Security` | JWT bearer sign-in, scopes, the admin policy |
| `Platform.Shared.Messaging` | MassTransit on RabbitMQ: retries, inbox and outbox, one trace across the broker |
| `Platform.Shared.Caching` | Redis as a best-effort cache: it speeds a read up and never fails one |
| `Platform.Shared.Storage` | Any S3-compatible object storage, its buckets made at start |
| `Platform.Shared.Testing` | The test kit: containers at the stack's own versions, a quiet step log, an OpenID Connect stand-in |

**Proven where it lives:** retries and the outbox on a real broker, the trace across it, the cache's failure, the
database's collation — each tested here once, so a service tests only its own configuration.

Versioned together (one version for every package), published to GitHub Packages, each version's notes on the
repository's Releases page.

### Status

The repository is private for now and opens together with the platform.
