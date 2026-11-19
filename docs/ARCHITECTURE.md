# Architecture notes

The backend is a stateless Spring Boot REST API. Live updates go out over SSE.

## Concurrency

Each match has its own lock, so two matches can be scored at the same time.

## Data model

Team, Player, CricketMatch, Innings, BattingEntry, BowlingEntry and BallEvent are JPA entities.

## Live feed

The browser keeps one EventSource open on /api/stream and receives a match event after every ball.
