# Contributing to LoopNet

## What belongs here

- LoopNet record schema (`ln/record-v1`)
- Seed and future corpus data with documented splits
- Validation scripts and dataset card
- HuggingFace builder and export tooling

## What does not belong here

- LSS schema — [Loop Core Engineering](https://github.com/KanakMalpani/Loop-Core-Engineering)
- Loop execution — [LoopGym](https://github.com/KanakMalpani/LoopGym)
- Benchmark tasks — [LoopBench](https://github.com/KanakMalpani/LoopBench)

## Before opening a PR

```bash
pip install -r requirements.txt
python scripts/generate_seed.py --count 500 --seed 42
python scripts/validate_record.py --require-count 500
```

## Data contributions (v1.0+)

Community submissions will follow the labeling guide in [`guides/LABELING-GUIDE.md`](guides/LABELING-GUIDE.md). v0.1 is synthetic-only.

## License

Code contributions: MIT. Dataset contributions: CC BY 4.0 (see [DATACARD.md](DATACARD.md)).
