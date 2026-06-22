The anti-pattern my team is most at risk of is treating the lakehouse like a
data swamp: landing raw events but delaying schema, quality checks, and
ownership until "later". LLM observability data grows fast, and raw JSON logs
can look flexible at first, but without a Bronze -> Silver contract the same
request_id can be counted twice, error rates become inconsistent, and cost
metrics lose trust.

This lab showed why medallion design matters. Bronze should preserve source
truth, Silver should enforce parsing and deduplication, and Gold should expose
stable metrics such as p50/p95 latency, cost_usd, and error_rate. The biggest
lesson is that open table format features like ACID commits, schema evolution,
time travel, and restore are not just storage details; they are guardrails that
keep metrics reproducible when pipelines or assumptions change.
