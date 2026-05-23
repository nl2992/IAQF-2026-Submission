# When "$1" Is Not One: Stablecoin Discounts and Market Fragmentation

**Team:** Bayes on the River, Columbia University Mathematics of Finance<br>
**Captain:** Nigel Li<br>
**Competition:** 2026 IAQF Academic Affiliate Membership Student Competition<br>
**Recognition:** Selected as one of six winning teams in the Fifteenth Annual IAQF Student Competition.<br>
**Focus:** Law-of-one-price deviations, stablecoin funding stress, liquidity fragmentation, and arbitrage limits during the March 2023 USDC de-peg.

This repository contains the final paper, IAQF winners notice, empirical notebooks, data panels, figures, and addendum for a study of how stablecoin stress propagated through BTC spot markets during the March 2023 USDC de-peg. The analysis combines 1-minute and 1-hour price panels, stablecoin FX rates, order-book microstructure measures, cross-exchange comparisons, arbitrage simulations, and mean-reversion models.

## Submission Documents

| Document | Path |
|---|---|
| Final paper | [`docs/submission/Columbia_Bayes_on_the_River.pdf`](docs/submission/Columbia_Bayes_on_the_River.pdf) |
| IAQF winners announcement | [`docs/submission/IAQF_2026_winners_notice.pdf`](docs/submission/IAQF_2026_winners_notice.pdf) |
| Technical addendum | [`IAQF 2026 Paper (CIP) - Addendum.pdf`](IAQF%202026%20Paper%20%28CIP%29%20-%20Addendum.pdf) |
| Competition prompt | [`docs/IAQFStudentCompetition2026.pdf`](docs/IAQFStudentCompetition2026.pdf) |

## Research Questions

1. How large did BTC law-of-one-price deviations become across USD, USDT, and USDC quote currencies?
2. Did stablecoin discounts transmit into spot BTC markets and liquidity conditions?
3. How did spreads, depth, price impact, and realized volatility differ by quote currency during the crisis?
4. When did arbitrage become economically infeasible after transaction costs, latency, and capital haircuts?
5. What do these results imply for stablecoin settlement adoption and market-structure policy?

## Key Findings

- **Law-of-one-price dislocation:** BTC/USDC versus BTC/USD deviations reached more than **1,200 bps** during the crisis, compared with a pre-crisis median near zero.
- **Stablecoin funding shock:** USDC/USD traded at a median discount of roughly **300 bps** during the crisis on Binance.US and Kraken, with intraday stress substantially larger at the trough.
- **Venue synchronization:** Cross-venue USDC deviation correlation rose to approximately **0.91**, indicating a systemic stablecoin shock rather than an isolated exchange anomaly.
- **Liquidity fragmentation:** BTC/USDC price impact was materially higher than BTC/USDT, and quoted spreads widened across both stablecoin- and dollar-quoted markets.
- **Arbitrage impairment:** Estimated OU half-life increased from **3.2 minutes** before the crisis to **602.7 minutes** during the crisis, showing that deviations persisted when balance-sheet and execution constraints tightened.
- **Cross-exchange contagion:** Bybit and Kraken evidence shows the stress was not confined to Binance.US; offshore and cross-venue markets also reflected the de-peg.

## Main Figures

The README uses full-width figures so the plots are readable in GitHub's renderer. Additional appendix figures are listed below.

### Figure 1: Price and LOP Overview

<img src="figures/master/master_fig1_price_lop_overview.png" alt="BTC price, stablecoin FX rates, and LOP deviations during the March 2023 USDC de-peg" width="100%">

### Figure 2: Stablecoin De-Peg Dynamics

<img src="figures/master/master_fig3_stablecoin_depeg.png" alt="USDC/USD and stablecoin FX deviations during the crisis window" width="100%">

### Figure 3: Crisis Deep Dive

<img src="figures/master/master_fig9_crisis_deep_dive.png" alt="Crisis-window BTC/USDC price, LOP deviation, implied liquidity, and order-flow imbalance" width="100%">

### Figure 4: Quote-Currency Price Impact

<img src="figures/master/master_fig6_kyle_lambda.png" alt="Kyle lambda estimates by quote currency and regime" width="100%">

### Figure 5: Regression Evidence

<img src="figures/master/master_fig11_regression_coefs.png" alt="Regression coefficient estimates for LOP drivers" width="100%">

### Figure 6: Spread, Depth, and Volatility

<img src="figures/lop/fig_x_spread_depth_vol.png" alt="Spread, depth, and realized volatility across BTC quote currencies" width="100%">

### Figure 7: GENIUS Act Sensitivity

<img src="figures/lop/fig_r1_genius_sensitivity.png" alt="Sensitivity table and expected holding-time comparisons under stablecoin adoption assumptions" width="100%">

## Appendix Figure Index

| Area | Figure | Path |
|---|---|---|
| Arbitrage simulation | Basis versus transaction costs | `figures/arb/arb_fig1_basis_vs_costs.png` |
| Arbitrage simulation | Profitability heatmap | `figures/arb/arb_fig2_profitability_heatmap.png` |
| Arbitrage simulation | Crisis-window deep dive | `figures/arb/arb_fig5_crisis_window.png` |
| OU mean reversion | Residual basis by regime | `figures/ou/ou_fig1_residual_timeseries.png` |
| OU mean reversion | Impulse response by regime | `figures/ou/ou_fig2_impulse_response.png` |
| Kraken cross-exchange | BTC/USD venue wedge | `figures/kraken/kraken_fig1_wedge_timeseries.png` |
| Kraken cross-exchange | Stablecoin FX deviations | `figures/kraken/kraken_fig2_stablecoin_fx.png` |
| Bybit cross-exchange | Crisis-window microstructure | `figures/bybit/bybit_fig1_crisis_window.png` |
| Advanced models | HMM regime detection | `figures/advanced/adv_fig1_hmm.png` |
| Advanced models | GARCH volatility | `figures/advanced/adv_fig2_garch.png` |
| Advanced models | Hawkes process stress clustering | `figures/advanced/adv_fig7_hawkes.png` |

## Repository Layout

```text
IAQF-2026-Submission/
├── README.md
├── IAQF 2026 Paper (CIP) - Addendum.pdf
├── docs/
│   ├── IAQFStudentCompetition2026.pdf
│   └── submission/
│       ├── Columbia_Bayes_on_the_River.pdf
│       └── IAQF_2026_winners_notice.pdf
├── data/
│   ├── parquet/                  # Main Binance.US/Coinbase price and feature panels
│   └── cross_exchange/           # Kraken and Bybit cross-exchange panels
├── figures/
│   ├── master/                   # Main paper figures
│   ├── lop/                      # Spread/depth/volatility and policy-sensitivity figures
│   ├── arb/                      # Arbitrage simulation figures
│   ├── br/                       # Basis-risk figures
│   ├── ou/                       # OU mean-reversion figures
│   ├── bybit/                    # Bybit cross-exchange figures
│   ├── kraken/                   # Kraken cross-exchange figures
│   └── advanced/                 # HMM, GARCH, random forest, Markov, Hawkes, PCA figures
├── notebooks/
│   ├── IAQF_Master_Analysis.ipynb
│   ├── IAQF_Advanced_Models.ipynb
│   ├── IAQF_Arbitrage_Simulation_executed.ipynb
│   ├── IAQF_BasisRisk_Analysis_executed.ipynb
│   ├── IAQF_OU_Analysis_executed.ipynb
│   ├── IAQF_CrossExchange_Bybit_executed.ipynb
│   └── IAQF_CrossExchange_Kraken.ipynb
├── scripts/                      # Data-fetching and feature-construction helpers
├── generate_data.py              # Builds the main data panels
├── fetch_cross_exchange.py       # Fetches Kraken and Bybit cross-exchange data
├── compute_table_vii.py
├── compute_table_x.py
└── compute_sensitivity_table.py
```

## Reproducibility

Install the Python dependencies:

```bash
pip install pandas numpy matplotlib seaborn statsmodels scipy \
            hmmlearn arch scikit-learn tslearn openpyxl pyarrow \
            requests jupyter nbformat nbconvert
```

Generate the main LOP panel without the large tick-data download:

```bash
python generate_data.py --skip-l2
```

Generate the full L2 microstructure dataset:

```bash
python generate_data.py
```

This downloads and processes large Binance public-archive tick files. Expect roughly 20 GB of raw tick data and a longer runtime.

Fetch cross-exchange Kraken and Bybit panels:

```bash
python fetch_cross_exchange.py
```

Run the notebooks from the `notebooks/` directory after the corresponding data panels are present.

## Notebook Map

| Notebook | Purpose | Data dependency |
|---|---|---|
| `IAQF_Master_Analysis.ipynb` | Main LOP, stablecoin, and microstructure analysis | `data/parquet/panel_1min.parquet`, `panel_1hour.parquet`, L2 files |
| `IAQF_Advanced_Models.ipynb` | HMM, GARCH, random forest, Markov switching, Hawkes, PCA | `data/parquet/panel_1min.parquet` |
| `IAQF_Arbitrage_Simulation_executed.ipynb` | Transaction-cost and arbitrage profitability simulation | `data/parquet/panel_1min.parquet` |
| `IAQF_BasisRisk_Analysis_executed.ipynb` | Basis decomposition, moments, and tail-risk analysis | `data/parquet/panel_1min.parquet` |
| `IAQF_OU_Analysis_executed.ipynb` | OU mean-reversion and half-life estimates | Self-fetches required Binance.US data |
| `IAQF_CrossExchange_Bybit_executed.ipynb` | Bybit offshore cross-exchange analysis | `data/cross_exchange/bybit_*.parquet` |
| `IAQF_CrossExchange_Kraken.ipynb` | Kraken venue wedge and stablecoin FX analysis | `data/cross_exchange/kraken_*.parquet` |

## Paper Artifact Map

| Paper item | Repository artifact |
|---|---|
| Final paper | `docs/submission/Columbia_Bayes_on_the_River.pdf` |
| IAQF winners notice | `docs/submission/IAQF_2026_winners_notice.pdf` |
| Submitted paper addendum | `IAQF 2026 Paper (CIP) - Addendum.pdf` |
| Main figures | `figures/master/` and `figures/lop/` |
| Appendix figures | `figures/arb/`, `figures/br/`, `figures/ou/`, `figures/bybit/`, `figures/kraken/`, `figures/advanced/` |
| Main data panels | `data/parquet/` |
| Cross-exchange panels | `data/cross_exchange/` |
| Competition prompt | `docs/IAQFStudentCompetition2026.pdf` |
