# Phase 0 decision: G-P1 (COLA rules → pension liquidity → asset sales)

## Decision: **NO-GO** for the question as stated

The decision does **not** rest on the unresolved novelty gate. It rests on Gates 3–4: with public data, the proposed design cannot realistically answer its stated question, whatever the July 2026 competitor version contains.

## Gate table

| Gate | Status | Basis |
| - | - | - |
| 1 Novelty vs closest papers | **UNRESOLVED** | The November 2025 full text of Andonov–Jansen–Rauh (AJR) occupies the mechanism (cash outflows → equity/alternatives sales; stronger with illiquid portfolios; not rebalancing). It has **no** COLA, inflation-surge or benefit-side exogenous shock (pp. 10, 16, 29; Tables 5, 7). The July 2026 revision is confirmed by the author page, but its full text was not obtainable: SSRN 403, archives blocked. Its abstract retains the $0.67 headline. The only possible increment is the identifying shock, not the mechanism. |
| 2 Public-data accessibility | **PASS WITH MATERIAL RISK** | The PPD API is open and worked. However, the COLA rule table is a 2012/2014 snapshot last updated in 2017; COLA dollars are reported for 5 plans; there are no transaction fields. Iran access and terms are unverified. |
| 3 Measurement of the mechanism | **FAIL** (public data, thesis horizon) | Treatment: rule in force per tier, eligible benefit base and plan→pool mapping must all be hand-built. Outcome: only an allocation-residual proxy for sales, noisiest in FY2022–23, and strictly weaker than the competitor's FOIA holdings. Actual sales are not observed. |
| 4 Identification credibility | **FAIL** | (i) Power: binding caps compress the COLA-induced outflow to roughly 0.1–0.4% of assets in cross-system SD. Scaling AJR's own precision, the minimum detectable effect is ≈ $3–30 per $1, against a plausible $0.4–0.7 (`identification_risks.md` §2). (ii) Exposure is a legislated generosity choice correlated with institutions that also shape portfolios; there is one national shock and few uncapped-rule states. (iii) COLA rules change often (NASRA; Fitzpatrick–Goda), so "predetermined" must be proven plan by plan. |
| 5 Six to seven months | **FAIL** | Rule-history, tier-weight, pool-map and purchase/sale reconstruction for ~100+ systems is archival work of several months before any test. FOIA holdings are not obtainable on this horizon. |

No weighted score is used. Gates 3 and 4 are each individually fatal for the stated question.

## Why CONDITIONAL is not appropriate

CONDITIONAL requires that one specific unresolved issue, once settled, would justify data construction. Even if the July 2026 version contains nothing on COLAs (the best case for novelty), Gates 3–5 still fail. Reading the July 2026 text cannot rescue the design. It can only add a duplication risk.

## What would have to be true to reopen it (not recommended now)

All of the following:
- The July 2026 text shows no COLA or inflation-surge analysis.
- Security-level holdings or reported purchase/sale data become available for a substantial set of pools.
- A source of benefit-side variation is found that is at least comparable in magnitude to AJR's residual cash-flow variation (≥1% of assets in cross-sectional SD), plausibly exogenous, and not a legislated generosity parameter.

None of these is in sight.

## Explicitly not done

I have not redesigned the question. The first-stage-only variant (COLA rules → 2022–24 benefit growth) is a different, weaker pension-accounting question. It would need its own novelty review and should not be substituted silently.

## Evidence index

- Competitor and version verification: `latest_competitor_audit.md`
- Literature: `literature_overlap_matrix.md`
- Identification and power: `identification_risks.md`
- Data: `data_feasibility_precheck.md`
