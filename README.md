# Evidence Dataset

This folder contains structured extraction tables for a systematic evidence review on physics-informed, data-driven, safe, and constrained learning methods for microgrid and power-system operation.

The dataset separates source-level decisions from claim-level evidence. A source is counted once in `source_inventory.csv` and `eligibility_decisions.csv`. A claim is a method-task-context unit extracted from an included source and is counted in `evidence_claims.csv`.

## Core Tables

| File | Purpose |
| --- | --- |
| `source_inventory.csv` | Bibliographic and topical inventory for all reviewed sources. |
| `eligibility_decisions.csv` | Included, contextual, and excluded decisions with rationale. |
| `evidence_claims.csv` | Main claim-level evidence table for included sources. |
| `denominators.csv` | Separate source-level and claim-level counts. |
| `coding_rules.csv` | Rules used for eligibility, claim splitting, evidence class, fidelity tier, and auditability tier. |
| `claim_unit_examples.csv` | Examples showing how sources were split into claim units. |
| `classification_decisions.csv` | Difficult classification cases and final decisions. |

## Supporting Tables

| File | Purpose |
| --- | --- |
| `retrieval_log.csv` | Retrieval and screening metadata available from the local corpus. |
| `citation_screening.csv` | Bounded citation-following decisions. |
| `coding_resolution.csv` | Available coding-resolution information. |
| `review_context.csv` | Comparison with review sources in the corpus. |
| `evidence_cross_tabulations.csv` | Cross-tabulated claim counts. |
| `evidence_summaries.csv` | Distribution summaries for included claim evidence. |
| `runtime_complexity.csv` | Latency, runtime, and computational-complexity evidence. |
| `safety_assumptions.csv` | Safety and protection assumptions for operational claims. |
| `uncertainty_evidence.csv` | Uncertainty, calibration, and risk-related evidence. |
| `scalability_evidence.csv` | Large-system, topology, and scaling evidence. |
| `failure_modes.csv` | Feasibility conditions and reported failure modes. |
| `benchmark_requirements.csv` | Evidence-derived benchmark requirements. |
| `evidence_coverage.csv` | Mapping from review needs to supporting tables. |
| `dataset_index.csv` | Compact file index. |

## Reading Order

1. Start with `source_inventory.csv` to identify all reviewed sources and citation keys.
2. Use `eligibility_decisions.csv` to separate included, contextual, and excluded sources.
3. Use `evidence_claims.csv` for the main evidence synthesis. Join it to `eligibility_decisions.csv` using `study_id` or to `source_inventory.csv` using `citation_key`.
4. Use `denominators.csv` when reporting counts. Do not mix source-level and claim-level denominators.
5. Use `coding_rules.csv` and `claim_unit_examples.csv` to interpret classification decisions and claim splitting.

## Key Coding Values

`final_status` uses `Included`, `Contextual`, and `Excluded`.

`validation_fidelity_tier` uses:

- `F0`: static, steady-state, operating-point, analytical, or offline feasibility evaluation.
- `F1`: ordinary time-domain, RMS, DAE, averaged, simulation-level, or non-real-time dynamic evaluation.
- `F2`: high-fidelity transient, EMT, switching-level, or detailed device/protection simulation.
- `F3`: real-time simulation, hardware-in-the-loop, laboratory, field, or prototype evaluation.

`auditability_tier` uses:

- `A0`: operational context or limits not clearly stated.
- `A1`: operational context stated with at least one metric.
- `A2`: explicit test condition plus constraint, violation, stability, or feasibility outcome.
- `A3`: A2 plus robustness breadth, feasible runtime or latency, and baseline or ablation.

`NR` means the information was not reported in the available corpus.

