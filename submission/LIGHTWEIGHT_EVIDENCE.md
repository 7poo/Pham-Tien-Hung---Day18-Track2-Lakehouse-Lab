# Lightweight Lab Evidence

This page is separate from the notebook work and is intended to summarize the
Lightweight submission evidence.

## Runtime

- Path: Lightweight default path, using `deltalake`, DuckDB, Polars, PyArrow,
  JupyterLab, and Jupytext.
- Smoke test: passed with `python3 scripts/verify_lite.py`.
- Jupyter notebooks: all four lightweight notebooks were executed in place.

## Executed Notebooks

- `notebooks/01_delta_basics.ipynb`
- `notebooks/02_optimize_zorder.ipynb`
- `notebooks/03_time_travel.ipynb`
- `notebooks/04_medallion.ipynb`

## Rubric Evidence

| Notebook | Evidence |
|---|---|
| `01_delta_basics` | Delta table created with `_delta_log`; bad schema write blocked; `tier` column added by schema merge. |
| `02_optimize_zorder` | 200 files before OPTIMIZE; 55 files after OPTIMIZE+ZORDER; speedup 8.5x; files-pruned ratio 55x. |
| `03_time_travel` | History shows 5 versions including RESTORE; MERGE 100K rows completed in 0.07s; restore completed under 30s and `score < 0` count is 0. |
| `04_medallion` | Bronze, Silver, and Gold tables exist; Silver rows 190,052 < Bronze rows 200,000; Gold has p50/p95 latency, cost_usd, error_rate across 8 dates and 3 models. |

## Storage Evidence

See:

- `submission/screenshots/lakehouse_tree.txt`
- `submission/screenshots/delta_log_sample.md`
- `submission/screenshots/lakehouse_evidence.png`

These files show the local `_lakehouse/` layout and a real Delta transaction
log sample from:

`_lakehouse/bronze/llm_calls_raw/_delta_log/00000000000000000000.json`
