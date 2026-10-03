# Yield Curve Lab

Nelson-Siegel-Svensson (NSS) curve fitting, PCA, recession signals and a UK gilt comparison for US Treasuries, July 2001 to 1 October 2026. Built in Google Colab; the output is a single interactive HTML report.

**Live report:** https://edrosling.github.io/yield-curve-lab/

## Key results
- **Fit:** NSS curves fitted daily to zero-coupon yields bootstrapped from Treasury par yields: mean error 4.1 bp, about 12 bp (10Y) and 14 bp (30Y) RMSE against the Federal Reserve's GSW curve.
- **Recessions:** 10y-3m spread AUC 0.81 in-sample (four recessions since 1983), 0.70 out-of-sample from 1995 (95% CI 0.41-0.94); 10y-2y 0.61 (0.25-0.98). Suggestive, not conclusive.
- **UK vs US:** weekly 10Y correlation 0.76; level and slope factors have similar structure; gilt sensitivity to US moves rose from 0.68 to 0.80 after 2022 (p = 0.03 vs 2008-21, p = 0.12 vs 2016-21).
- **Hedging:** hedging a 10Y zero with 2Y+30Y, a PCA hedge left 39% of unhedged risk (2012-2026) vs 37% for a barbell and 41% for a 5Y hedge.

## Data (downloaded automatically by the notebook)
FRED (API key needed), Bank of England yield curves and Bank Rate, Federal Reserve Board GSW curve (feds200628). Raw data files are not included; see the report's reference section for links.

## Run it
1. Get a free FRED API key and store it as the Colab secret `FRED_API_KEY`.
2. Open the notebook in Google Colab and choose Runtime > Run all (the BoE and Fed data download automatically).
3. The final report is `yield_curve_lab_report_v6.html`; rename it `index.html` to publish with GitHub Pages.

## Files
- `yield_curve_lab.ipynb` - the notebook (run top to bottom)
- `index.html` - the final report
- `requirements.txt` - Python packages

## Reproducibility notes
- Data refreshes daily, so latest values (such as current spreads) will differ from the report.
- The out-of-sample and hedging results quoted in the report's text were typed in from the notebook's printed output, so rerunning on new data will not update that text.
- Intermediate HTML files are written along the way; only the last one is the report.

## Limitations
Weakly identified NSS betas; fit differs from the Fed's curve; only four recessions; final (not real-time) NBER dates; descriptive policy-week table; idealised hedging demo. Details are in the report.

Educational project, not investment advice.
