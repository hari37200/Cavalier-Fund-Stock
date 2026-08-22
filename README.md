# Cavalier Fund — Stock Selection & Portfolio Risk Analysis

Risk–return analysis of four candidate equities for the Cavalier Fund, a
student-managed fund whose mandate is to **outperform the S&P 500 by selecting
undervalued, high-potential stocks**.

The analysis answers one question — *which stock is the most attractive
investment?* — and the six follow-on questions about how risk should be
measured, priced, and diversified.

---

## Candidate Stocks

| Stock | Industry | Anticipated Return | Std. Deviation | Beta (OLS) | Dividend Yield | P/E | Safety | Bond Rating |
|---|---|---|---|---|---|---|---|---|
| Delphi | Auto Parts | 9.1% | 24.8% | 1.30 | 1.52% | 13.6 | 3 | Baa2 |
| Groupon | Internet Information | 9.3% | 67.3% | 1.44 | 0% | NMF | 5 | N/A |
| Kellogg | Packaged Foods | 4.6% | 14.6% | 0.54 | 2.75% | 19.3 | 1 | Baa2 |
| Kinross Gold | Gold Mining | 8.4% | 65.0% | 0.31 | 0% | 24.6 | 5 | Ba1 |

**Market assumptions:** risk-free rate 3.4% (30-day T-bills) · market return
12.0% · market risk premium 8.6%.

---

## Method

1. **Risk characterisation** — total risk via standard deviation, systematic
   risk via OLS beta. The two are deliberately kept separate: they rank the
   stocks differently.
2. **Risk-adjusted return** — Sharpe ratio, `(E[R] - Rf) / sigma`, to compare
   return per unit of total risk.
3. **CAPM pricing** — `Ri = Rf + Bi(Rm - Rf)`. Expected return is compared with
   CAPM-required return to flag over/undervaluation.
4. **Two-asset portfolio risk** —
   `sigma_p^2 = w1^2*sigma1^2 + w2^2*sigma2^2 + 2*w1*w2*rho*sigma1*sigma2`
   applied to a 50–50 Groupon/Kinross pair at an assumed correlation of −0.2.

---

## Key Results

**Recommendation: Delphi Automotive.** Highest Sharpe ratio of the four — 9.1%
expected return at 24.8% volatility, versus Groupon's near-identical 9.3%
return at 67.3%. Beta of 1.30 keeps systematic risk within a reasonable band,
and a P/E of 13.6 with a Baa2 rating and 1.52% dividend yield supports the
valuation case.

**Risk ranking**

- *Riskiest* — **Groupon**: highest total volatility (67.3%) *and* highest
  systematic risk (beta 1.44).
- *Least risky* — **Kellogg**: lowest volatility (14.6%) and low beta (0.54).
- **Kinross Gold** is the instructive case: 65.0% volatility but beta of just
  0.31. Almost all of its risk is idiosyncratic (commodity and geopolitical),
  not market-driven.

**Diversification result.** A 50–50 Groupon/Kinross portfolio has a standard
deviation of **~41.8%** — *lower than either stock alone*. With imperfectly
correlated returns, losses in one are partly offset by gains in the other.
This is the argument for holding Kinross despite its standalone risk profile:
what matters is marginal contribution to portfolio risk, not standalone
volatility.

**Pricing implication.** Investors are compensated only for systematic risk;
idiosyncratic risk can be diversified away and therefore earns no premium.
A stock whose expected return exceeds its CAPM-required return is a candidate
for being undervalued.

---

## Files

| File | Contents |
|---|---|
| `CAV_analysis.pdf` | Full written analysis of all seven questions |
| `FUND_ANALYSIS.xlsx` | Working model — stock metrics, Sharpe ratios, CAPM returns, portfolio variance |
| `ques cons.pdf` | The analysis questions considered |

### Workbook sheets

- **Sheet1** — raw stock metrics (return, sigma, beta, yield, P/E, ratings)
- **Sheet2** — Sharpe ratios, CAPM returns, and the two-asset portfolio sigma
- **Sheet3** — market assumptions (S&P 500 arithmetic mean, T-bill rate)
