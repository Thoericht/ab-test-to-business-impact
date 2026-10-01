# From Experiment to Impact

## A/B Test Evaluation and Campaign Scenario Planning

This project evaluates a publicly available marketing A/B test to assess whether advertising exposure is associated with a meaningful increase in recorded conversion compared with a PSA control group.

Beyond statistical significance, the project translates the observed conversion difference into transparent business scenarios for campaign reach, contribution margin, and campaign cost.

## Business question

> Does the advertising treatment outperform the PSA control group, and under which assumptions would the estimated conversion lift create meaningful incremental business value?

## Project objectives

- Validate and prepare a user-level A/B test dataset.
- Compare recorded conversion rates for the advertising and PSA groups.
- Estimate absolute and relative conversion lift with uncertainty intervals.
- Assess statistical and practical significance.
- Explore conversion patterns by day, hour, and ad exposure.
- Build conservative, base-case, and upside business scenarios.
- Translate analytical results into a decision-oriented recommendation.

## Dataset

The project uses the **Marketing A/B Testing** dataset published by Favio Vázquez on Kaggle.

- **Source:** [Marketing A/B Testing – Kaggle](https://www.kaggle.com/datasets/faviovaz/marketing-ab-testing)
- **Unit of analysis:** User-level experiment record
- **Scale:** 588,101 records
- **Groups:** `ad` treatment group and `psa` control group
- **Primary outcome:** Recorded conversion
- **License:** CC0 1.0 / Public Domain

The dataset is described as a simple marketing campaign with an experiment and control group for A/B testing. [1265][1268]

## Analysis plan

### Primary analysis

The primary comparison evaluates whether the recorded conversion rate differs between:

```text
Treatment: users assigned to the advertising group
Control: users assigned to the PSA group
```

Key outputs:

- Conversion rate by group
- Absolute conversion lift in percentage points
- Relative conversion lift
- 95% confidence interval
- Statistical test result
- Incremental conversions per 100,000 users reached

### Scenario analysis

The source data do not include revenue, contribution margin, campaign cost, or customer lifetime value. Financial outcomes are therefore modelled through explicit assumptions rather than treated as observed facts.

```text
Incremental conversions
= Campaign reach × estimated conversion lift

Incremental profit
= Incremental conversions × assumed contribution margin
  − assumed campaign cost
```

Scenarios will be reported as:

- Conservative
- Base case
- Upside

## Methodological scope

This project evaluates an available experiment extract. The source does not document the original randomisation mechanism, intended allocation ratio, experiment duration, conversion window, or campaign economics.

Results are therefore reported as differences in recorded conversion between the ad and PSA groups. A causal interpretation is conditional on valid original assignment. Subgroup and exposure analyses are exploratory. In particular, ad exposure is not treated as a pre-treatment control variable in the primary treatment-effect analysis.

## Tools

- Python
- pandas and NumPy
- SciPy and/or statsmodels
- matplotlib and seaborn
- Power BI for optional interactive scenario planning
- Git and GitHub

## Repository structure

```text
.
├── 01_data/
│   ├── 01_raw/                         # Original source data
│   └── 02_processed/                   # Cleaned and analysis-ready data
├── 02_notebooks/
├── 03_outputs/
├── 04_dashboard/                    # Optional Power BI scenario planner
├── 05_screenshots/
├── requirements.txt
└── README.md
```

## Status

🚧 In progress