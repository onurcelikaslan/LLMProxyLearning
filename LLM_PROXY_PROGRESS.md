# LLM Proxy Scale-Up — Progress

**In progress:** Step 1

## Phase 1 — Foundations & Architecture
- [ ] 1. Solution structure, Clean Architecture layout, Docker Compose skeleton (Redis), git init + .gitignore + first commit
  - Acceptance criteria: (1) `docker compose up` → Redis + API ayakta, health endpoint 200; (2) katman referansları tek taraflı (Domain hiçbir şeye bağımlı değil); (3) git repo + ilk commit atılmış.
  ### Interview Angles
  - "Domain katmanı neden zayıf, Clean Architecture'ı yanlış mı uyguluyorsun?" — proxy'nin domain karmaşıklığı düşük, operasyonel karmaşıklığı (concurrency/resilience) yüksek; katmanlama testability ve infra değiştirilebilirliği için.
- [ ] 2. Multi-tenant request model — tenant resolution, routing

## Phase 2 — Traffic Control
- [ ] 3. Rate limiting — Redis token bucket / sliding window
- [ ] 4. Request queueing & backpressure

## Phase 3 — Observability
- [ ] 5. OpenTelemetry instrumentation
- [ ] 6. Prometheus + Grafana wiring

## Phase 4 — Resilience
- [ ] 7. Circuit breaker & retry policies (Polly)
- [ ] 8. Downstream call abstraction — mock vs real provider, timeouts, idempotency

## Phase 5 — Load Testing & Validation
- [ ] 9. k6 test scenarios
- [ ] 10. Bottleneck analysis & fixes
- [ ] 11. Horizontal scaling test

## Phase 6 — Packaging the Story
- [ ] 12. README with architecture diagram and findings
- [ ] 13. LinkedIn article draft
- [ ] 14. Interview story rehearsal (STAR format)
