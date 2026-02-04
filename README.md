# PlayCast

Minimal project skeleton for experiment-driven development.

## Folders
- `config/`: Configuration files (YAML/JSON/ENV) for experiments and pipelines.
- `data/`: Local datasets.
  - `data/raw/`: Immutable, original data dumps.
  - `data/processed/`: Cleaned or feature-ready datasets.
- `scripts/`: One-off or pipeline scripts.
  - `scripts/data/`: Ingestion and cleaning.
  - `scripts/features/`: Feature engineering.
  - `scripts/train/`: Training jobs.
  - `scripts/eval/`: Evaluation and reporting.
  - `scripts/sim/`: Simulation and scenario runs.
- `src/`: Installable Python package.
  - `src/playcast/`: Core library code.
- `outputs/`: Generated artifacts.
  - `outputs/models/`: Trained models and checkpoints.
  - `outputs/reports/`: Figures, tables, and summaries.
  - `outputs/logs/`: Run logs and diagnostics.
- `notebooks/`: Exploration and analysis notebooks.
