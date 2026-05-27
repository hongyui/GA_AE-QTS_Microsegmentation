# Experiment Results for CMC

Raw convergence logs from AEQTS / GA / DE / PSO with different initialization strategies for reproducibility. Each algorithm contains 30 runs across multiple population sizes, seeds, and time/iteration budgets.

---

## Folder Structure

### `aeqts/`
Results for the AEQTS algorithm under single-pair setting experiment settings.

- `stats_single_50P-1min/` — Population size 50, time budget 1 minute
- `stats_single_50P-5000iter/` — Population size 50, 5000 iterations

---

### `stats_*` folders
Aggregated experiment results across multiple seeds, organized by population size and stopping criterion.

| Folder | Population Size | Stopping Criterion |
|---|---|---|
| `stats_50P-1000iter` | 50 | 1000 iterations |
| `stats_50P-5000iter` | 50 | 5000 iterations |
| `stats_50P-1min` | 50 | 1 minute |
| `stats_50P-1_5min` | 50 | 1.5 minutes |
| `stats_100P-1000iter` | 100 | 1000 iterations |
| `stats_150P-1000iter` | 150 | 1000 iterations |
| `stats_150P-5000iter` | 150 | 5000 iterations |
| `stats_150P-1min` | 150 | 1 minute |
| `stats_150P-15min` | 150 | 15 minutes |
| `stats_scale_200_50P-1000iter` | 50 | 1000 iterations (scale test: 200 devices) |

---

## Data Format

Each `convergence_log.json` records the per-iteration convergence trace of a single run:

```json
{
  "iteration": 1,
  "elapsed_time": 0.031,
  "best_fitness": 2717.16,
  "raw_best_fitness": 2717.16,
  "avg_fitness": 3516.07,
  "worst_fitness": 4449.39,
  "avg_entropy": 5.94,
  "num_vlans": 42
}
```

| Field | Description |
|---|---|
| `iteration` | Iteration number |
| `elapsed_time` | Wall-clock time elapsed (seconds) |
| `best_fitness` | Best fitness value in the current population |
| `raw_best_fitness` | Best fitness before any penalty adjustment |
| `avg_fitness` | Average fitness of the population |
| `worst_fitness` | Worst fitness in the current population |
| `avg_entropy` | Average entropy of the population |
| `num_vlans` | Number of VLANs in the best solution |
