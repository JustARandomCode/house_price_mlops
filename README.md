# House Price MLOps

End-to-end MLOps project: a house price prediction model taken from versioned
experiments to a deployed, monitored service. Built incrementally across five
lab assignments; each assignment is tagged in Git (`assignment-1` ... `assignment-5`).

| Assignment | Topic                                   | Git tag        |
|------------|-----------------------------------------|----------------|
| 1          | Git branching + MLOps lifecycle docs    | `assignment-1` |
| 2          | Git + DVC reproducible pipeline         | `assignment-2` |
| 3          | FastAPI + Docker model serving          | `assignment-3` |
| 4          | CI/CD (GitHub Actions) + Airflow DAG    | `assignment-4` |
| 5          | Drift monitoring                        | `assignment-5` |

## Branching strategy

| Branch          | Purpose                                              | Merges into |
|-----------------|------------------------------------------------------|-------------|
| `main`          | Production-ready, tagged releases only               | -           |
| `dev`           | Integration branch; all features land here first     | `main`      |
| `feature/<name>`| One unit of work (data, model, API, docs)            | `dev`       |

Rules:
1. Never commit directly to `main` or `dev`.
2. Branch `feature/*` from `dev`; merge back with a pull request (use `--no-ff` locally).
3. Release: merge `dev` into `main`, then tag (`v0.1.0`).
4. Commit messages: `type: summary` (`feat`, `fix`, `docs`, `exp`, `ci`).

Full lifecycle documentation: [docs/MLOPS_LIFECYCLE.md](docs/MLOPS_LIFECYCLE.md)
