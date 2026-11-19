# Architecture notes

The backend is a stateless Spring Boot REST API. Live updates go out over SSE.

## Concurrency

Each match has its own lock, so two matches can be scored at the same time.
