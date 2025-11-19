
# Synthetic Control Method Project — California (Simulated dataset)
**Treated unit**: California  
**Intervention year**: 1988  
**Dataset**: project/data/cleaned_dataset.csv

## Abstract
This project applies the Synthetic Control Method (SCM) to estimate the impact of a public-health policy in California on cigarette sales per capita. We construct a synthetic counterfactual from donor states by optimizing non-negative weights to match pre-intervention trends.

## Key results
- RMSPE (pre-intervention): 1.9664  
- RMSPE (post-intervention): 9.0309  
- Mean post-period treatment effect (gap): -8.2919

## Top donor states and weights
| state    |      weight |
|:---------|------------:|
| State_5  | 0.283753    |
| State_23 | 0.237496    |
| State_25 | 0.140671    |
| State_6  | 0.11752     |
| State_2  | 0.0845943   |
| State_31 | 0.065112    |
| State_21 | 0.029716    |
| State_49 | 0.0279813   |
| State_3  | 0.0131576   |
| State_22 | 2.28394e-18 |

## Placebo summary (top 5 RMSPE ratio)
| state    |   rmspe_pre |   rmspe_post |   rmspe_ratio |   post_gap_mean |
|:---------|------------:|-------------:|--------------:|----------------:|
| State_34 |     1.47172 |      2.98445 |       2.02786 |        0.672434 |
| State_9  |     3.06715 |      5.5373  |       1.80535 |        3.8206   |
| State_12 |     9.86415 |     14.2276  |       1.44235 |       13.8692   |
| State_25 |     2.88094 |      3.97402 |       1.37942 |       -1.76059  |
| State_5  |    24.3319  |     31.3725  |       1.28936 |       31.1782   |

## Robustness
- Leave-one-out results saved in `project/results/tables/leave_one_out.csv`.
- Placebo distribution plotted in `project/results/plots/placebo_dist.png`.

## Limitations
- Synth uses observed outcomes only; unobserved time-varying confounders may bias estimates.
- For publication-grade inference, consider inference via placebo permutation p-values and alternative V-matrix calibration.

## Files produced
- `project/results/tables/weights.csv`, `top_weights.csv`, `scm_output.csv`, `placebo_results.csv`  
- `project/results/plots/*.png`  
- `project/data/cleaned_dataset.csv`  

## Conclusion
The SCM analysis indicates a sustained reduction in cigarette sales in the treated unit post-intervention compared to its synthetic counterpart. Refer to the visuals and placebo tests for evidence of statistical significance.

