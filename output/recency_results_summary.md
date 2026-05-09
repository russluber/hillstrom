# Recency Based Email Targeting Results

## Data loaded
- Rows: 64000
- Columns: 12
- Duplicate rows: 6562
- Quality warnings: none

## Sample construction
- Out-of-range recency (<1 or >12): 0
- Customers excluded from bin analyses (unbinnable): 0
- Winsorization cutoff (p99 of full sample): $0.00
- Per-bin × arm cell counts available in tables/table2_recency_arm_counts.csv.

## Baseline overall email effects
- Mens E-Mail minus No E-Mail: $0.7698 [$0.4851, $1.0545]
- Womens E-Mail minus No E-Mail: $0.4244 [$0.1690, $0.6799]
- Mens E-Mail minus Womens E-Mail: $0.3454 [$0.0326, $0.6583]

## Analysis 1: Spend lift by recency group
- Largest Mens lift: **Warm** at $1.0476, [$0.4642, $1.6310].
- Largest Womens lift: **Cooling** at $0.6655, [$0.1098, $1.2211].
- Full per-bin × comparison estimates: tables/table4_recency_spend_lift.csv.

## Analysis 2: Causal funnel by recency group
- ITT effects on visit, conversion, and spend per recency bin: tables/table5_recency_funnel_lift.csv.
- Visit and conversion estimates are reported in percentage points (estimate_display column).
- Spend estimates are dollars per assigned customer.

## Analysis 3: Recommended targeting policy
- **Warm**: Mens E-Mail — Clear winner. Mens lift $1.0476 [$0.4642, $1.6310]; Womens lift $0.3586 [$-0.1154, $0.8326].
- **Cooling**: Either email — Either email, no clear winner. Mens lift $0.4884 [$0.0089, $0.9679]; Womens lift $0.6655 [$0.1098, $1.2211].
- **Dormant**: Either email — Either email, no clear winner. Mens lift $0.6051 [$0.0642, $1.1460]; Womens lift $0.2995 [$-0.2485, $0.8475].
- **Very dormant**: Either email — Either email, no clear winner. Mens lift $0.7721 [$0.2094, $1.3347]; Womens lift $0.4100 [$-0.0218, $0.8418].

## Analysis 4: Robustness and credibility checks
- All recency × arm cells have n ≥ 500: **TRUE**.
- Winsorized vs raw direction agreement across (bin × comparison): **0%**.
- Covariate-balance flags (numeric SMD > 0.10 or categorical share diff > 2pp): **0**.

## Final managerial takeaway
- Largest Mens E-Mail incremental spend: **Warm** ($1.0476).
- Largest Womens E-Mail incremental spend: **Cooling** ($0.6655).
- Per-bin policy:
- **Warm**: Mens E-Mail — Clear winner. Mens lift $1.0476 [$0.4642, $1.6310]; Womens lift $0.3586 [$-0.1154, $0.8326].
- **Cooling**: Either email — Either email, no clear winner. Mens lift $0.4884 [$0.0089, $0.9679]; Womens lift $0.6655 [$0.1098, $1.2211].
- **Dormant**: Either email — Either email, no clear winner. Mens lift $0.6051 [$0.0642, $1.1460]; Womens lift $0.2995 [$-0.2485, $0.8475].
- **Very dormant**: Either email — Either email, no clear winner. Mens lift $0.7721 [$0.2094, $1.3347]; Womens lift $0.4100 [$-0.0218, $0.8418].
- Robustness: cell sizes all sufficient; winsorized direction agreement 0%; 0 balance flags.
