<h1 align="center">David Gergiev</h1>
<h3 align="center">Backend Developer (Go)</h3>

---

## About

Backend engineer specializing in Go.

Focus areas:

- Concurrency and memory efficiency  
- PostgreSQL performance  
- Distributed job processing  
- API design and service reliability  

Currently studying Raft consensus and Go runtime internals.

---

## Tech Stack

**Primary**

- Go  
- PostgreSQL  
- gRPC  
- Docker  

**Working knowledge**

- Redis  
- Linux  
- CI/CD  
- Testify  
- Nginx  

---

## Featured Project

### Distributed Task Queue  
**Repository:** https://github.com/DavidJackso/distributed-task-queue

Distributed job processing service built with Go and Redis.

**Responsibilities:**

- Designed and implemented worker pool using Go concurrency primitives  
- Built idempotent handlers to ensure safe retries  
- Implemented retry policies with backoff  
- Added structured logging for failure analysis  

**Results:**

- Processes 30k+ jobs/day under synthetic load  
- p95 latency: ~20ms  
- Reduced memory consumption by ~25% after profiling and allocation optimization  

**Tech:** Go, Redis, Docker

---

## Engineering Practices

- Write unit and integration tests for critical paths  
- Profile CPU and memory using pprof  
- Prefer explicit error handling  
- Design APIs with backward compatibility in mind  
- Optimize only after measurement  

---

## Current Focus

- Distributed systems fundamentals  
- Contention reduction and allocation minimization  
- Query optimization in PostgreSQL  
- Service observability  

---

## Contact

- LinkedIn — https://linkedin.com/in/gopherdev  
- Email — hello@gopher.dev
