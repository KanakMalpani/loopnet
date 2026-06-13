# Status

| Field | Value |
|-------|-------|
| **Phase** | v0.1 shipped |
| **Symbol** | ✅ |
| **Started** | 2026-06-13 |
| **Shipped** | 2026-06-13 |
| **Owner** | — |
| **Blockers** | — |
| **Notes** | Published at https://github.com/KanakMalpani/loopnet |

## Completion checklist

- [x] `schema/loopnet-record-v1.json`
- [x] `data/seed/` — 500 records (synthetic v0.1)
- [x] `scripts/validate_record.py`
- [x] `scripts/upload_hf.py` (optional)
- [x] `DATACARD.md`
- [x] `guides/LABELING-GUIDE.md`
- [x] `scripts/generate_seed.py`
- [x] `scripts/baseline_failure_mode.py`
- [x] `datasets/loopnet/loopnet.py` (HuggingFace builder)
- [x] CI: validate workflow
- [x] `SYNC.md` — canonical source policy

## Corpus stats (seed v0.1)

Regenerate with `python scripts/generate_seed.py` then validate.

| Metric | Value |
|--------|-------|
| Records | 500 |
| Failure rate | 42.0% (210 failures) |
| Source | 100% synthetic |

## Links

- Parent workspace: [../README.md](../README.md)
- Core dependency: [../01-loop-engineering-core/](../01-loop-engineering-core/)
- Agent brief: [../AGENT-BRIEF.md](../AGENT-BRIEF.md)
- Plan: [PLAN.md](PLAN.md)
