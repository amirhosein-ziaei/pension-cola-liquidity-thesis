# Latest competitor audit: Andonov, Jansen and Rauh, "When Cash Flows Turn Negative"

Audit date: 9 October 2026. Labels used throughout:
**[V]** directly verified from a primary source I opened; **[I]** reasonable inference; **[U]** unresolved.

## 1. Version verification

| Version | What I could access | Evidence | Status |
| - | - | - | - |
| **November 2025** | **Full text, 63 pages, including Online Appendices A–C and Appendix B (FOIA procedure).** Two copies: [Rotman copy](https://www.rotman.utoronto.ca/media/rotman/Jansen_Kristy.pdf) (with author footnote; PDF created 2025-11-18 22:28 UTC; sha256 `a2c4046d…`) and [WSIR copy](https://www.wsir.org/10papers/9.pdf) (anonymized title page; created 2025-11-18 17:09 UTC; body text identical after the title page by `diff`). | Title page: "When Cash Flows Turn Negative: Liquidity-Driven Selling by Pension Funds", "November 2025". | [V] |
| **July 2026** | **Only metadata and a revised abstract. The full text was NOT obtained.** | [Kristy Jansen research page](https://www.kristyjansen.com/research-1) (retrieved 9 Oct 2026) lists the paper as "(July 2026)", working paper, with new presentations (AFA, EFA, LBS Summer Finance Symposium best-paper award, and others). [Andonov research page](http://www.aleksandarandonov.com/research.html) lists it as a 2026 working paper with a **rewritten abstract**. A [Hoover Institution page dated 18 September 2026](https://www.hoover.org/node/394335) posts the same 2026 abstract; its "download" button links only to SSRN. | Date [V] from author page; content [U] |
| SSRN record 5498920 | Blocked. `papers.ssrn.com` abstract and `Delivery.cfm` routes returned HTTP 403 (Cloudflare "Content Blocked") from this host and from WebFetch. `api.ssrn.com`, `doi.org/10.2139/ssrn.5498920` → 403. Wayback Machine (`web.archive.org`) connection reset / refused. Stanford GSB repositories (`gsbpreserve.stanford.edu/view/40725`, `oa.gsb.libnova.com/view/40725`) returned Cloudflare JavaScript challenges (403). | No SSRN "last revised" date, title or page count verified by me. | [U] |

**Title discrepancy.** The request names the SSRN paper "When Cash Flows Turn Negative: Institutional Investors and Asset Sales". Every source I could open (both PDFs, both author pages and Hoover) uses the subtitle "**Liquidity-Driven Selling by Pension Funds**". I could not open the SSRN record to check whether its title differs. [U]

**Publication status.** Both authors list it under *Working Papers*. No journal acceptance was found. [V for author listings; absence of acceptance is a search result, not proof]

**Same-team adjacent paper.** Andonov, Jansen and Rauh, "Natural Buyers? Pension Funds and Treasury Exposure" (September 2026, working paper). According to the abstract on Andonov's page, pension liability structure has little explanatory power for Treasury allocations or maturity choices. The study uses the same security-level holdings. [V abstract only] It is a separate paper and should not be counted as a second cash-flow competitor. It does show that the team is systematically relating liability structure to these holdings.

### What the July 2026 abstract does and does not reveal

The 2026 abstract, taken verbatim from Andonov's page and Hoover, reports three findings:
1. funds with more negative cash flows do not adjust target allocations;
2. they meet cash-flow shocks mainly by selling equities, "**absorbing $0.67 per dollar of shock**", and sell across equities rather than liquid-first;
3. they sell equities even when equity returns are negative.

[I] The $0.67 figure is identical to the November 2025 Table 5, column (4), coefficient on negative residual cash flows (0.673). The core estimate and design were therefore probably retained.
[U] Whether the July 2026 version adds an inflation/COLA analysis, an instrument for benefit payments, a 2024 data year, or new appendices **cannot be determined**. Its abstract no longer mentions the alternatives-heterogeneity result. That omission does not prove the result was removed.

**Consequence: any novelty statement relative to the July 2026 version is UNRESOLVED.** Every detailed claim below refers to the **November 2025** full text.

## 2. What the November 2025 version actually does (page = PDF page)

| Element | What it does | Location |
| - | - | - |
| Sample | 186 U.S. public pension *funds* (retirement-system investment level, aggregating plans managed collectively, e.g., NJ Division of Investment), 2001–2023. 145 come from PPD and 41 are hand-collected local funds. | Sec. 3.1, p. 14 |
| Holdings | Requests to 178 funds yielded 109 deliveries; 59 met the quality criteria. They provide quarterly security-level holdings of equity, fixed income, cash, alternatives (commitments) and derivatives, covering about 47% of assets. Twelve funds required state citizenship. | Sec. 3.2, pp. 17–18; App. B pp. 52–57 |
| Cash flow | %CF = (contributions − benefits − admin) / beginning AUM. | p. 14 |
| "Shock" construction | Per-fund robust detrending of contributions and benefits separately gives %CF Fit and %CF Residual; this uses forward-looking information. Robustness: %CF Predicted/Shock from a rolling t−10…t−1 robust regression. | pp. 14–15; Table A.1 p. 49; Table C.1 p. 58 |
| Where the shock variation comes from | "The variation in %CF Residual comes primarily from substantial deviations from the trend of contribution inflows, while the benefit payments are much more predictable." | p. 16; Figure 1 Panels C–D p. 36 |
| Magnitudes | %CF mean −2.4, SD 3.3; %CF Residual SD 2.8; %CF Shock SD 1.8 (% of assets). | Table 1, p. 38 |
| COLA | One institutional sentence: some COLAs are set by formula and others periodically by the legislature. **No COLA variable, rule coding or COLA-based test.** | Sec. 2.1, p. 10 |
| Inflation | No inflation-surge analysis. The word appears only in "CRSP U.S. Treasury and Inflation Series". | p. 29 |
| Asset-class flows | Flow = (A_j,t − A_j,t−1 × (1+R^BM_j,t)) / TA_t−1. R^BM is the **median return of funds with the same fiscal-year end**. These are inferred net flows from allocations, not observed transactions. | Eq. (2), p. 22 |
| Main result | Per $1 of negative residual cash flow: equity −$0.67 (SE 0.141), alternatives −$0.41 (SE 0.173), cash and fixed income ≈ 0. Fund and year-reporting-month fixed effects; lagged allocation gap; clustered by fund; N = 3,230. | Table 5, p. 42 (text p. 23) |
| Rebalancing separation | Allocation-gap control, time fixed effects and an equity-minus-bond return control (Table C.5, p. 62). Split by relative returns: $0.63 equity sales even when equity underperforms (Table 6, p. 43). | pp. 26–27 |
| Illiquid exposure | Tertiles of lagged alternatives share: high tertile sells $0.51 of equity per $1 negative residual; low tertile is insignificant. Same pattern for risky-asset tertiles. | Table 7, p. 44; text p. 28 |
| Security level | Holdings-based quarterly flows adjusted by security returns, interacted with Amihud or size illiquidity, with security×time fixed effects. Funds with high alternatives shares sell 2.7× more of each stock. Treasuries are not disproportionately sold. | Eq. (4) p. 30; Tables 8–10 pp. 45–47; p. 31 |
| Investment income | Controls for dividends/interest; results unchanged. | Sec. 5.1, pp. 24–26; Tables C.3–C.4 |
| Lines of credit | No evidence that funds use them. | p. 21 |
| Identification | Cash-flow innovations with fixed effects and rebalancing controls. **No instrument, no rule-based or policy shock, no event study.** | Secs. 5–6 |

## 3. Exact overlap with the proposed project (November 2025 text unless stated)

| # | Item | What AJR establish (Nov 2025) | Our addition | Economically meaningful? |
| - | - | - | - | - |
| 1 | Negative cash flows → liquidation | **Fully established**: equity and alternatives sales per $ of negative residual cash flow (Table 5 p. 42). | None at this level. | No. Fully occupied. |
| 2 | Inflation-driven benefit obligations | Not studied (p. 29 is the only "inflation" hit; sample ends 2023). | Inflation surge as the trigger. | Only if it creates usable variation; see `identification_risks.md`. July 2026: [U]. |
| 3 | COLA formulas / indexed liabilities | Mentioned once as institutional background (p. 10). | Rule coding as a treatment. | Same as row 2. July 2026: [U]. |
| 4 | Exogenous or predetermined liability shocks | Statistical residuals. Their shock variation is mainly on the **contribution** side; benefits are "much more predictable" (p. 16). | A **benefit-side** shock that is predetermined conditional on the rule. This is the only genuine conceptual gap. | In principle yes (cleaner than fiscal contribution shocks). In practice it requires a large first stage, which caps make small (see below). |
| 5 | Sales conditional on illiquid exposure | **Established**: alternatives/risky-share tertiles (Table 7 p. 44) and security-level results (Table 9 p. 46). | None, except interacting it with a different shock. | No. Re-estimating the interaction with another shock is not a new result. |
| 6 | Actual security sales versus inferred allocation changes | Asset class: inferred from PPD allocations with median benchmark returns (Eq. 2). Security: holdings-based flows from FOIA data for 59 funds. | **Negative increment.** A public-data thesis would have only the Eq. (2)-type proxy, i.e., strictly less than AJR. | No. This is a weakness relative to the competitor. |
| 7 | Identification via rules, cash-flow innovations or funding shocks | Cash-flow innovations only; rebalancing ruled out by return splits. | Rule-based exposure × inflation. | Meaningful **only** if precise. A wide confidence interval that includes $0.67 adds nothing to AJR. |

## 4. Bottom line on the competitor

- **Verified:** the headline mechanism (pension cash outflows → equity/alternatives sales, stronger with illiquid portfolios, not rebalancing) is occupied by the November 2025 version. The 2026 abstract confirms that it remains the paper's core.
- **Verified gap in Nov 2025:** no COLA rule, inflation-surge or benefit-side exogenous shock.
- **Unresolved:** whether the July 2026 full text fills that gap. The authors hold the holdings data and the 2022–23 years, and a newer same-team paper relates liability structure to holdings. The risk that a revision or referee round adds an inflation/benefit robustness check is real but **unverified**.
- **Novelty gate: UNRESOLVED**, as the instructions require when the latest full text is unavailable. The identification and measurement problems in `identification_risks.md` apply regardless of what the July 2026 version contains.

## 5. Access log

| URL | Result (9 Oct 2026) |
| - | - |
| rotman.utoronto.ca/media/rotman/Jansen_Kristy.pdf | 200, PDF, Nov 2025 |
| wsir.org/10papers/9.pdf | 200, PDF, Nov 2025 (anonymized) |
| kristyjansen.com/research-1 | 200, lists "(July 2026)" |
| aleksandarandonov.com/research.html | 200, 2026 abstract |
| hoover.org/node/394335 | 200, 18 Sep 2026 entry, links to SSRN only |
| inquire-europe.org news item (17 Apr 2026) | 200; seminar summary consistent with Nov 2025 findings; no COLA content |
| papers.ssrn.com (abstract, Delivery.cfm), api.ssrn.com, doi.org/10.2139/ssrn.5498920 | 403 |
| web.archive.org | connection reset; WebFetch refused |
| gsbpreserve.stanford.edu, oa.gsb.libnova.com | 403 (JS challenge) |
| Google Scholar / NBER search for a 2026 PDF | none found |

**Legitimate remaining route:** e-mail the authors to request the July 2026 draft. This is not needed for the Phase 0 decision (see `phase0_decision.md`).
