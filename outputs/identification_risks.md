# Identification risks for the COLA → benefit outflow → liquid-asset sales design

[V] verified fact with source · [I] inference or calculation by me · [U] unresolved

## 1. The design in one line

Sales_{s,t} = β · (rule-implied COLA outflow_{s,t}) + fixed effects + controls, where the rule-implied outflow = pre-surge COLA rule × realized CPI × eligible benefit base, for an investment system s over fiscal years around 2021–24. The heterogeneity of interest is β × pre-surge illiquid share. This is a shift-share design with **one common national shock** (CPI) and cross-sectional exposure (the rule).

## 2. The decisive problem: the shock is small relative to the outcome noise

### 2a. Size of the treatment

- Benefits ≈ **7.3% of net assets** at the median plan in FY2019 (IQR 5.9–9.8%). PPD income statement, 247 plans, first row per plan [V, `data_feasibility_precheck.md`].
- Caps compress the treatment. According to NASRA (June 2026, p. 5), inflation since early 2021 "has exceeded the automatic COLA caps in place for most public pension plans that have a cap" [V]. CRR (Aug 2022): CPI-linked plans guarantee about 85% of CPI up to a 3.5% maximum on average, and fewer than 10% of automatic CPI-linked plans provide complete protection [V, page]. In the PPD rule table, the modal cap among CPI-linked records is **3%** (233 records); only **11 of 152 plans** have any record that looks uncapped and CPI-linked [V, my profile of the 2012/2014 snapshot].
- Realized averages: Equable reports an average public-pension COLA of **2.02% in 2023** [V, page] and **about 1.8% in 2022** [search-result snippet of an Equable fact sheet; the PDF returned 403, so this figure is not verified by me]. Across plans, the realized COLA barely moved from its usual ~2% during the surge [I].
- Differential COLA increment versus a ~2% pre-surge baseline, in % of benefits [I]:
  - fixed-rate plans: ≈ 0
  - 2%-cap plans: ≈ 0
  - 3%-cap plans: ≈ +1 pp
  - 5%-cap plans: ≈ +3 pp
  - uncapped full-CPI plans: ≈ +5–6 pp at the 2022 peak
  - ad hoc grants: endogenous
- Translated into assets [I]: the cross-system SD of the COLA-induced outflow is roughly **0.1–0.4% of assets per year**. The upper end allows for compounding of the level by 2024 and generous eligibility; eligibility dilution and contribution offsets push it lower.

### 2b. What the competitor's own precision implies

AJR estimate the equity response to negative residual cash flow at 0.673 with SE 0.141, using N = 3,230 fund-years (Table 5 col. 4, p. 42). %CF Residual has SD 2.8% of assets and %CF Shock 1.8% (Table 1, p. 38) [V]. Scaling the standard error as SE ∝ σ_ε / (σ_x √N) and **assuming the same residual flow noise** (optimistic: 2022 flows are unusually noisy, see §3.8) [I]:

| Scenario | σ_x competitor (negative part) | σ_x G-P1 | N system-years | Implied SE | Minimum detectable effect (80% power, 5%) |
| - | - | - | - | - | - |
| Optimistic | 1.5 | 0.4 | 900 | ≈ 1.0 | ≈ $2.8 per $1 |
| Central | 2.0 | 0.2 | 600 | ≈ 3.3 | ≈ $9 per $1 |
| Pessimistic | 2.8 | 0.1 | 450 | ≈ 10.6 | ≈ $30 per $1 |

The plausible effect, taken from AJR, is $0.4–0.7 per $1. **Even the optimistic case cannot distinguish $0.67 from zero, or from $1.50.** A 2SLS version that first maps rules to benefits only loses further power. The calculation is a rough scaling, not a formal power analysis, but the gap is a factor of 4 to 40. Reasonable changes in assumptions do not close it.

**Implication:** with annual, public, asset-class-level data, the design cannot answer its stated question (do COLA outflows *induce sales*, and more so with illiquid exposure). A heterogeneity test (β × illiquid share) needs more power still.

## 3. Assumption-by-assumption review

| # | Threat | Why it matters here | What would be required | Status |
| - | - | - | - | - |
| 3.1 | Predetermined rules vs endogenous generosity | Generous COLAs correlate with non-Social-Security coverage (NASRA p. 1: nearly half of retired teachers), union and fiscal institutions, plan maturity and funding discipline. These can also shape alternatives shares and contribution behaviour. Exposure × 2022 is then exposure-correlated characteristics × the 2022 market and rate shock. | Show balance of exposure against funding, maturity, alternatives share, contribution discipline and SS coverage. Show event-study pre-trends in **benefits and flows**. Show placebo "inflation" years. | High risk |
| 3.2 | Rules are not actually fixed | NASRA (p. 4): 17 states changed COLAs affecting current retirees since 2009; ad hoc COLAs were granted after the surge (AL, GA, NH, OK, TX named). Fitzpatrick–Goda: COLA changes affected on average 45% of workers per year, 2005–18. Funded-ratio-contingent COLAs (9 PPD plans) respond to returns. | Rule in force on a dated pre-2021 legal document per tier. Exclude or separately model ad hoc and contingent COLAs. | Measurable but laborious |
| 3.3 | Eligibility weights | COLAs apply only to eligible retirees: waiting periods, minimum ages, years-in-retirement, benefit-base limits (e.g., MA: first $13,000; NASRA p. 3). 380 of 1,384 PPD rule records carry age/retirement-period/date conditions and 215 carry benefit-base limits [V]. Retiree counts and benefits by tier are rarely in PPD. | Retiree benefit base by tier and eligibility status from actuarial valuations (pre-2021) for every plan. | [U]; the largest construction cost |
| 3.4 | Timing and implementation lags | CPI reference windows (calendar, Q3–Q3, June–June) and effective dates differ; fiscal years end in June or December. 2022 inflation reaches many plans' FY2023 benefits. Annual flows blur this. | Plan-specific reference-period mapping; fiscal-year alignment. | Feasible but noisy |
| 3.5 | Inflation × caps | With binding caps, most CPI-linked plans behave like fixed-rate plans at their cap. The effective treatment collapses to **one legislated parameter (the cap)**, which is exactly the generosity choice in 3.1. | Variation from plans whose pass-through was not capped. Only ~11 such PPD plans, clustered in few states. | High risk; too few independent groups |
| 3.6 | Contributions and fiscal offsets | Inflation raises payroll, and so contributions as a percentage of payroll. Higher COLA experience raises actuarially determined contributions with a 1–2 year lag. State revenue windfalls in 2021–22 may have funded supplemental contributions [I; not verified state by state]. In AJR, residual cash-flow variation comes **mainly from contributions** (p. 16). | Measure net cash-flow effects, not benefits alone. Contribution responses must be shown to be small or modelled. | High risk |
| 3.7 | Plan vs investment-pool aggregation | Rules sit at the tier/plan level; trading decisions sit at the pool level. AJR aggregate to the fund level (p. 14). Multi-plan pools average heterogeneous rules and shrink variation further. PPD has `system_id`, but a "system" is not necessarily the investing entity. | Hand-built plan→pool map with asset shares. | Feasible, reduces power |
| 3.8 | Valuation vs transactions | Public data give only Eq. (2)-type flows (allocation change minus a benchmark or median return). Error = (own − benchmark return) × holdings. In FY2022–23 asset-class returns were dispersed and private marks lagged public markets, so measurement error is largest exactly in the treatment years. PPD has **no** purchase/sale fields [V, variable dictionary]. | Statement-of-changes data (purchases/sales) from annual reports, validated, or holdings. | FAIL with PPD alone; [U] for annual-report reconstruction |
| 3.9 | Pre-existing illiquid shares | The 2022 "denominator effect" (stale private marks after public losses) mechanically raised alternatives shares and triggered secondaries and rebalancing (Abuzov–Andonov–Lerner). Using a pre-2021 share avoids mechanical contamination but not the differential 2022 response. | Freeze at FY2020; control for the 2022 overallocation gap; still confounded with 3.1. | High risk |
| 3.10 | One national shock, limited independent variation | A single inflation episode means identification comes entirely from cross-sectional exposure. With state clustering, there are roughly 40–50 clusters and few uncapped-rule states. Fixed effects cannot remove exposure-correlated responses to the same 2022 macro shock. | Exogeneity of exposure conditional on observables; leave-one-state-out; randomization inference over exposures. | Structural limitation |

## 4. Conditions for credible identification (all required)

1. A dated pre-2021 rule per tier, plus eligible benefit base per tier, aggregated to the investing pool.
2. A strong, transparent first stage: rule-implied COLA dollars predict actual benefit growth almost one-for-one, with correct timing.
3. Exposure is balanced against funding, maturity, alternatives share and contribution discipline, or the differences are shown not to predict 2022 flow responses (pre-period placebo).
4. Contribution offsets are measured, so the treatment is net cash flow.
5. Outcome flows are built from reported purchases/sales or holdings, not allocation residuals.
6. **Enough treatment variance to bound β more tightly than AJR already do. §2 indicates this condition fails with public data.**

Fixed effects, extra controls or "COLA as an IV" do not satisfy conditions 3, 5 or 6 automatically. An IV built from the cap is the generosity variable itself.

## 5. What could be identified

The **first stage alone** (pre-surge COLA rules → 2022–24 benefit growth) is plausibly identifiable, because benefits are smooth (AJR p. 16). It is a pension-accounting result about inflation pass-through to retirees and plan cash flows. It is **a different and much weaker finance question**. Substituting it for G-P1 would be a silent redesign and would need its own novelty adjudication.
