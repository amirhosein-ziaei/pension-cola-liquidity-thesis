# Data feasibility pre-check (documentation level only)

Checked 9 October 2026 via the [PPD API](https://publicplansdata.org/public-plans-database/api/). Only the variable dictionary, the `LastUpdate` listing, the small COLA rule table (1,384 records) and one four-variable income-statement extract were retrieved. No panel was built and no estimation was run.

**RAW** = retrieved and parsed by me · **DOC** = documented by the provider · **ADJ** = reported in the adjudication report, not re-checked · **UNVERIFIED** = not established.

## 1. Facts that change the assessment

1. **The PPD COLA rule table is a frozen snapshot, not a rule history.** `LastUpdate` shows `pensioncolabenefit` last updated **2017-10-18** and `pensionprovisions` **2014-11-14** [RAW]. All 1,384 rule records have `fy_start` ∈ {2012, 2014} and `fy_end` = 9999 [RAW]. The table cannot show the rule in force in 2021–23, and it cannot show changes made between 2014 and 2021. It is "pre-inflation" only in the sense that it is old. Every rule must be re-verified against a dated legal or plan document.
2. **COLA dollars are almost never separately reported.** `expense_COLABenefits` is non-zero for **5 plans (30 plan-years)** in FY2018–24 [RAW]. The adjudication report found 35 rows in its query [ADJ]. The first stage must therefore use total benefits.
3. **PPD has no transaction fields.** Of 1,106 variables, none records purchases, sales or acquisitions of investments. The only "flow" field is `NetFlows_smooth` (actuarial smoothing) [RAW, variable dictionary]. Asset-class sales can only be inferred from `*_Actl` allocation shares and `*_Rtrn` returns.
4. **Rule detail is incomplete for computing COLA dollars.** `COLA_Compounded` is missing in 1,156 of 1,384 records. 380 records carry age, retirement-period or retirement-date eligibility conditions, and 215 carry benefit-base limits [RAW]. Neither condition can be applied without retiree distributions by tier.
5. **Tier and group structure is pervasive.** 1,295 of 1,384 rule records carry a `TierID` [RAW]. The FY2018–24 income-statement extract has 2,163 rows for 253 plans: 1,771 aggregate plan-year rows plus 392 tier/group rows [RAW]. The adjudication's wider query returned 3,640 rows for the same 1,771 keys [ADJ]. Summing rows naively double-counts.
6. **Sign convention.** All 1,737 non-missing `expense_TotBenefits` rows are negative [RAW]. Benefits ≈ 7.3% of net assets at the median plan in FY2019 (IQR 5.9–9.8%, n = 247) [RAW].

## 2. Requirement-by-requirement status

| Requirement | Needed? | Source | Status | Consequence |
| - | - | - | - | - |
| Plan-year financials (assets, benefits, contributions) | Yes | PPD `pensionincomestatement`, `pensionsystemdata` (updated Sep 2026) | **RAW**, partial coverage (ADJ: 733 rows / 140 plans with the full selected financial + allocation combination, FY2018–24) | Usable with sign, unit and fiscal-year validation |
| Historical COLA rules in force pre-2021 | Yes (core treatment) | PPD snapshot is 2012/2014; statutes, plan documents, actuarial valuations | **UNVERIFIED** for 2021–23; PPD snapshot stale | Hand-collection with dated documents for every plan |
| Retiree eligibility and benefit weights by tier | Yes | Actuarial valuations / ACFR statistical sections; not in PPD by tier | **UNVERIFIED** | Without them, the "rule exposure" is a plan-wide generosity dummy, which is the confound |
| Actual benefit payments | Yes (first stage) | PPD `expense_TotBenefits` | **RAW** (total only); COLA component for 5 plans | First stage on total benefits; COLA share must be inferred |
| Employer and employee contributions | Yes (offsets) | PPD `contrib_*` | **RAW** field exists; completeness not profiled | Needed to measure net cash flow |
| Liquid and illiquid exposures | Yes | PPD `*_Actl`, `*_Trgt` | **RAW** fields; known classification problems (AJR p. 16, following Begenau–Liang–Siriwardane) | Must freeze at FY2020 and apply AJR-style cleaning |
| Security purchases/sales or validated net-acquisition proxy | Yes (outcome) | Not in PPD. Annual-report "statement of changes" / investment-section purchase-sale totals (availability varies); FOIA holdings (AJR: 59 usable of 178 requested; 12 require state citizenship, p. 17) | **UNVERIFIED** (annual reports); FOIA **infeasible** within 6–7 months from Iran | The public proxy is weaker than the competitor's data and noisiest in FY2022–23 |
| Plan ↔ pooled investment system links | Yes | PPD `system_id`, `pensionretirementsystembasics`; pool structure from annual reports | **DOC**; plan→investing-pool equivalence UNVERIFIED | Hand-built map required |

## 3. Access notes

- The PPD API worked from this host without login (JSON). Terms of use and ordinary access from Iran are **UNVERIFIED**.
- The rule table and dictionary are small; a full panel would also be modest in size. **Volume is not the bottleneck. Hand-collection of rules, eligibility weights, pool maps and purchase/sale data is.**

## 4. Fatal-barrier screen

| Barrier | Verdict |
| - | - |
| Treatment (COLA dollars by investing pool) measurable from public data without archival work | **No.** Stale rules, no tier weights, COLA dollars missing. Months of archival work. |
| Outcome (actual sales) measurable from public data | **Only as an allocation-residual proxy** (same as AJR Eq. 2, without their holdings validation). |
| Data access per se | PASS WITH MATERIAL RISK (public and reachable here; Iran access and terms unverified). |

Local artifacts (scratchpad, not committed): `cola.json` (sha256 `5759b968…`), `colaexp.json` (`8a10f216…`), `vars.json` (`9e097d55…`).
