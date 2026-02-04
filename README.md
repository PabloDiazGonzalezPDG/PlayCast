# PlayCast

PlayCast is a football analytics project for match modeling using deep learning and probabilistic methods, including Monte Carlo simulation to estimate outcome distributions across different time horizons.

## Repository layout (simple)

This repo is organized so you always know where to put things:

### `data/` (local data, not tracked)
Store datasets here. Keep large files out of git.
- `data/raw/`       Original files as downloaded (never edited)
- `data/processed/` Cleaned, aligned, and ready for training/evaluation

### `scripts/` (one-off runnable steps)
Executable scripts you run from the terminal. Each script should do one clear job.
- `scripts/fetch_data.py`        Download / export / collect data into `data/raw/`
- `scripts/preprocess.py`        Convert raw -> processed
- `scripts/build_features.py`    Create derived features (writes into `data/processed/` or feature files)
- `scripts/train.py`             Train a model (writes checkpoints to `outputs/models/`)
- `scripts/evaluate.py`          Evaluate models (writes metrics to `outputs/reports/`)
- `scripts/simulate.py`          Monte Carlo simulations (writes results to `outputs/reports/`)

### `src/PlayCast/` (reusable code)
Core library code that scripts/notebooks import.
- `src/PlayCast/data/`       loaders, dataset classes, schemas
- `src/PlayCast/features/`   reusable feature transforms
- `src/PlayCast/models/`     model definitions (deep learning, baselines, etc.)
- `src/PlayCast/metrics/`    metrics, backtesting utilities
- `src/PlayCast/sim/`        Monte Carlo simulation engine / sampling logic
- `src/PlayCast/utils/`      common helpers (seeding, logging, paths)

### `notebooks/` (experiments)
Jupyter notebooks for exploration and prototyping. If something becomes stable, move it into `src/` + `scripts/`.

### `outputs/` (local artifacts, not tracked)
Generated files you can delete and recreate.
- `outputs/models/`   checkpoints, weights
- `outputs/reports/`  tables, plots, metrics
- `outputs/logs/`     training logs

## Quick workflow (recommended)
1) Fetch data -> `data/raw/`
2) Preprocess -> `data/processed/`
3) Feature building -> `data/processed/` (or dedicated feature files)
4) Train -> `outputs/models/`
5) Evaluate / simulate -> `outputs/reports/`

## Notes
- Keep `data/` and `outputs/` out of git using `.gitignore`.
- Scripts should be runnable and minimal; reusable logic lives in `src/PlayCast/`.
