# Data Documentation

## Dataset

This project uses the publicly available `blocker` dataset from the
`multinma` R package.

The dataset contains mortality outcomes from 22 randomized clinical
trials comparing beta-blocker therapy with control after myocardial
infarction.

## Original Public Source

Official CRAN mirror:

`https://raw.githubusercontent.com/cran/multinma/master/data/blocker.rda`

## Raw Data Structure

The original dataset contains 44 arm-level records: two treatment arms
for each of the 22 trials.

| Variable | Meaning |
|---|---|
| `studyn` | Study identifier |
| `trtn` | Numeric treatment code |
| `trtc` | Treatment label |
| `r` | Number of deaths |
| `n` | Total participants in the study arm |

## Processed Files

| File | Purpose |
|---|---|
| `blocker_multinma_original.rda` | Original public R dataset |
| `blocker_raw.csv` | Untouched CSV copy of the original arm-level data |
| `blocker_clean_arm_level.csv` | Clean arm-level data for Bayesian binomial modeling |
| `blocker_study_level_evidence.csv` | Paired study-level table for descriptive analysis and benchmarking |

## Effect-Size Convention

Study-specific odds ratios compare beta-blocker therapy with control.

- Odds ratio below 1: lower mortality odds with beta blockers.
- Odds ratio above 1: higher mortality odds with beta blockers.

A 0.5 continuity correction is applied only to trials containing a
zero cell and only for study-specific descriptive odds-ratio calculations
and the conventional benchmark analysis.

The primary Bayesian models use the original arm-level binomial event
counts directly.

## Interpretation Boundary

This is a reproducible evidence-synthesis portfolio analysis using a
historical public clinical-trial dataset. It is not a current clinical
practice recommendation.
