# LoopNet

[![validate-loopnet](https://github.com/KanakMalpani/loopnet/actions/workflows/validate.yml/badge.svg)](https://github.com/KanakMalpani/loopnet/actions/workflows/validate.yml)
[![License: MIT](https://img.shields.io/badge/Code-MIT-yellow.svg)](LICENSE)
[![Dataset: CC BY 4.0](https://img.shields.io/badge/Dataset-CC%20BY%204.0-green.svg)](DATACARD.md)
[![Records: 500](https://img.shields.io/badge/records-500-blue.svg)](data/seed/records.jsonl)

**LoopNet** is the ImageNet of Loop Engineering — a large-scale dataset of loop designs, trajectories, successes, and failures.

**Schema:** `ln/record-v1` · **Spec pins:** `lss@1.0.0`, `les@1.0.0` ([Loop Core Engineering](https://github.com/KanakMalpani/Loop-Core-Engineering))

---

## Ecosystem

| Repo | Purpose |
|------|---------|
| [Loop Core Engineering](https://github.com/KanakMalpani/Loop-Core-Engineering) | LSS / LES specs |
| **LoopNet** (this repo) | Dataset (`ln/record-v1`) |
| [LoopGym](https://github.com/KanakMalpani/LoopGym) | ReplayEnv consumes this corpus |
| [LoopBench](https://github.com/KanakMalpani/LoopBench) | Benchmark suite |

---

## Quick start

```bash
git clone https://github.com/KanakMalpani/loopnet.git
cd loopnet
pip install -r requirements.txt
python scripts/validate_record.py --require-count 500
```

Regenerate the synthetic seed corpus:

```bash
python scripts/generate_seed.py --count 500 --seed 42
python scripts/validate_record.py --require-count 500
```

---

## Load in Python

```python
import json

records = [json.loads(line) for line in open("data/seed/records.jsonl")]
train = [r for r in records if r["split"] == "train"]
```

With HuggingFace Datasets:

```python
from datasets import load_dataset

ds = load_dataset("json", data_files="data/seed/records.jsonl", split="train")
```

---

## Layout

| Path | Purpose |
|------|---------|
| `schema/loopnet-record-v1.json` | Canonical record schema |
| `data/seed/records.jsonl` | 500-record synthetic seed corpus |
| `data/seed/splits.json` | Train/val/test ID manifest |
| `scripts/validate_record.py` | Schema + corpus policy validation |
| `scripts/generate_seed.py` | Regenerate synthetic seed data |
| `scripts/upload_hf.py` | Export Parquet + optional Hub upload |
| `datasets/loopnet/loopnet.py` | HuggingFace `datasets` builder |
| `guides/LABELING-GUIDE.md` | Human labeling instructions |
| `DATACARD.md` | Dataset card |
| `SYNC.md` | Cross-repo sync policy |

---

## Corpus stats (seed v0.1)

| Metric | Value |
|--------|-------|
| Records | 500 |
| Failure rate | 42.0% |
| Source | 100% synthetic |

---

## License

- **Code** (scripts, schema, builders): [MIT](LICENSE)
- **Dataset** (`data/seed/`): [CC BY 4.0](DATACARD.md)

---

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

---

## Status

v0.1 shipped — see [STATUS.md](STATUS.md).
