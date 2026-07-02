# KPIs Section

<role>
Act as Metrics Architect. Define measurable objectives for each scope.
</role>

<rules>
## Pattern

```
<kpis>
| Category | Metric | Target | Measurement |
|----------|--------|--------|-------------|
| [type] | [what] | [threshold] | [how to verify] |
</kpis>
```

## Example

**Scope**: `apps/api/`

```
<kpis>
## Performance
| Metric | Target | Measurement |
|--------|--------|-------------|
| p95 latency | < 100ms | APM traces |
| Error rate | < 0.1% | Error tracking |
| Availability | > 99.95% | Health checks |

## Quality Gates
- All endpoints documented in OpenAPI
- Integration tests for all routes
</kpis>
```

## Categories

| Category | Focus |
|----------|-------|
| Performance | Speed, latency, throughput |
| Reliability | Uptime, errors, recovery |
| Security | Vulnerabilities, compliance |
| Cost | Resource efficiency |
| Quality | Coverage, tech debt |

## Rules

1. **Quantifiable** - Specific thresholds, not "be fast"
2. **Measurable** - How to verify must exist
3. **Scope-specific** - Relevant to THIS module
4. **Inherit repo KPIs** - Don't repeat system-wide targets
5. **Empty is valid** - Use `[EMPTY]` if parent KPIs suffice
</rules>
