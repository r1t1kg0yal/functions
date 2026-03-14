# Analyst Brain: Conks / Stigum / Pozsar (v3 delta)

**Sources:** Stigum *The Money Market* (4th ed.); Pozsar *Global Money Notes* + *Shadow Banking*; Sweeney *Collateral Is King*; Financial System Plumbing Infographics
**Domain:** Repo / Fed Funds / Settlement / Dealer Balance Sheets / Fed Facilities / Shadow Banking / Collateral Velocity

**Core thesis:** Financial system = layered plumbing (settlement systems × balance sheets × intermediation chains). Fed = sole entity combining settlement operator + lender of last resort + rate corridor setter. Binding constraint on liquidity = dealer balance sheet capacity (leverage ratio), not cash or reserves. When plumbing clogs → rates spike, liquidity fragments, Fed intervenes.

---

## 1. Fed's Triple Role and Rate Corridor

- Fed simultaneously: settlement bank (Fedwire) + lender of last resort (DW/SRF/swap lines) + rate corridor operator (administered rates)
- No other institution combines all three
- **Corridor:** floor (RRP) ≤ all dollar money market rates ≤ ceiling (SRF/DW)
- Rate persistently outside corridor = broken plumbing, not policy failure
- **Stigma** makes ceiling soft: emergency facilities exist but usage signals weakness → rates can briefly breach ceiling until desperation overcomes reputation cost

**Global dollar rate hierarchy** (cheapest → most expensive):
RRP → EFFR → SOFR/TGCR/BGCR → IORB → SRF → DW → FX swap-implied → swap line rate
- Every dollar rate in the world sits within this hierarchy
- Rates outside = broken arbitrage or inaccessible facilities

---

## 2. Balance Sheet as Binding Constraint

- **SLR** = binding constraint on dealer repo intermediation
  - Treats ALL assets at full notional — Treasuries, reserves, repos — zero risk-weighting benefit
  - Dealers face flat balance sheet "tax" per dollar of repo regardless of collateral quality
  - Confirmed: COVID SLR exemption → dealer capacity immediately expanded; removal → contracted
- **Netting** = critical variable determining balance sheet cost
  - Requires BOTH conditions simultaneously:
    1. Same counterparty (or CCP novation to single counterparty)
    2. Same settlement date (allowing right of offset)
  - Failing either condition → both legs appear gross → doubles leverage exposure
  - Central clearing solves condition (1) via novation
  - Overnight tenor solves condition (2) via maturity matching
  - Cross-product netting (triparty RP + DVP RRP, previously unnettable) becomes possible when both face CCP
- **Implication:** when balance sheets constrained, dealers shed bilateral/term/non-nettable positions first → those segments see sharpest rate spikes

---

## 3. Repo Market Segmentation

| Segment | Participants | Clearing | Nettable | Balance Sheet Cost |
|---------|-------------|----------|----------|--------------------|
| Triparty | MMFs/GSEs/sec lenders → dealers | Single clearing agent | No | Expensive |
| Interdealer (GCF) | Dealer ↔ dealer | CCP novation | Yes | Cheap |
| Bilateral DVP | Any two parties | None | No | Most expensive |
| Sponsored/Cleared | Non-members via sponsor → CCP | CCP novation | Yes (sponsor side) | Cheap for sponsor |

- Dealers run matched books across segments: borrow triparty (from MMFs, tight rate) → lend DVP bilateral (to HFs, wider rate)
- **Matched book spread** = compensation for: balance sheet consumption + counterparty risk + operational risk + settlement timing mismatch
- Spread blowout = impaired transmission (liquidity exists but can't flow to where needed)
- Basel III made balance sheet cost binding → surge in central clearing adoption

---

## 4. FHLB-FBO-IORB Arbitrage Chain

- **FHLBs:** cannot earn IORB (GSE, wrong master account type) → must lend excess cash in fed funds below IORB
- **FBOs** (foreign banking organizations) are primary borrowers because:
  - Have Fed master accounts (earn IORB)
  - No FDIC insurance assessment (would erode spread)
  - G-SIB surcharge on consolidated global basis (marginal US FF activity = minimal score impact)
  - Structural dollar funding demand from global operations
- **Chain:** FHLBs lend FF below IORB → FBOs borrow → park at Fed earning IORB → pocket spread
- This chain IS what anchors EFFR slightly below IORB
- **FBO park vs deploy:** sets marginal FF rate daily
  - Park all at Fed → EFFR close to IORB minus FHLB spread
  - Deploy into repos/FX swaps → EFFR can tighten toward IORB
  - FBO behavior = invisible hand of EFFR

---

## 5. Settlement Timing

- Settlement infrastructure = rigid, non-overlapping daily timing windows
- **The pivot:** DVP closes → triparty opens (mid-afternoon)
  - Most critical moment: securities + cash repositioned across systems simultaneously
  - Sole triparty agent extends intraday credit during transition → systemic single point of failure
  - Any delay cascades
- Settlement timing, not end-of-day positions, drives real intraday liquidity risk

**Settlement Wednesday (fed funds):**
- Reserve maintenance periods settle biweekly
- Mid-afternoon: securities settlement closes → bank gets balance picture
- Late afternoon: final CHIPS + securities numbers arrive
- Foreign bank flows = wild card after 5 PM (whipsaws clearing bank positions)
- Very large share of daily FF volume trades in last two hours before Fedwire close → structurally volatile, predictable, positionable

---

## 6. Window Dressing and Calendar Periodicity

- Banks optimize regulatory scores at reporting snapshot dates:
  - Shrink repo books, shift bilateral → cleared, reduce interbank lending, build HQLA buffers
  - Between snapshots: re-expand
- **Predictable distortions:** repo rate spikes, Fed facility usage rises, bid-asks widen, intermediation capacity shrinks
- **Severity gradient:** year-end > quarter-end > month-end
- Foreign bank reporting dates = additional distortion layer
- G-SIB surcharge (year-end snapshot, 5 categories) = most intense shrinkage incentive
- **Tradeable:** experienced participants position for these calendar effects

---

## 7. QT Drain Sequencing

- QT mechanically shrinks Fed balance sheet (assets = liabilities)
- Three candidate liabilities to absorb drain: reserves, RRP facility, TGA
- **"What drains" = THE critical QT variable:**
  - RRP drains (MMFs buy T-bills instead of parking at Fed) → painless, excess liquidity redirected
  - Reserves drain (banks buy) → contractionary, intermediation capacity shrinks
  - TGA drains (Treasury spends down) → temporarily adds reserves back
- **Sequencing:** RRP drains first → then reserves
  - "Free" phase: excess liquidity redirection (RRP declining)
  - "Painful" phase: actual reserve scarcity (some banks hit limits)
  - Transition: when RRP approaches zero
- **MMF allocation** = critical transmission mechanism (bill vs repo vs RRP based on relative yield)

---

## 8. Shadow Money and Collateral Velocity

- **Shadow money** = outstanding × market price × (1 - haircut) for any collateral class
  - = quantity of "instant cash" embedded in holding that collateral
  - Three factors (value, haircut, velocity) are **multiplicative** → small moves compound
- **Collateral velocity** (rehypothecation churn) multiplies effective shadow money stock
  - Controlled by ~10-14 large dealers globally
  - Velocity contraction = invisible monetary shock (doesn't appear in any traditional aggregate)
- **Haircut procyclicality:**
  - Booms: haircuts compress (easy terms, confidence high)
  - Crises: haircuts spike (tight terms, confidence evaporating)
  - Haircut cycle LEADS credit cycle
  - More sensitive leading indicator than interest rates
- **Shadow banks** (MMFs, sec lenders, repo dealers, HFs, finance cos, structured vehicles):
  - Perform bank-like maturity/liquidity transformation without deposit insurance
  - "Run" = MMFs refuse to roll repo + CP buyers disappear + sec lenders recall collateral
  - Fed progressively extended backstops (PDCF, MMLF, CPFF, SRF) because too interconnected to fail

---

## 9. Specials, Fails, and Front-End Mechanics

**Specials:**
- Issue trades "special" when borrowing demand drives its repo rate below GC rate
- Holder earns lending fee = (GC rate - specials rate) × notional × (days/360)
- Triggers: on-the-run (heavy shorting), CTD for futures (basis trade demand), settlement needs
- Brokers source specials from regional banks/S&Ls (not dealer-to-dealer) — this is the value-add
- Extreme demand → specials rate can go negative (borrower pays to obtain the issue)

**Fails:**
- Fail = seller doesn't deliver on settlement date
- Fails charge = max(0, target rate - 3%)
- Near-zero rates → fails charge = 0 → fails become costless
- **Implication:** ZIRP makes on-the-run specials more extreme → specials-GC spread widens → owning OTR = revenue source

**Bill-repo spread:**
- Bills consistently yield below repo
- Reason: captive demand — many investors (state/local govts, regulated funds) cannot do repo
- Structural anomaly; persists and widens during flight-to-safety

**Curve regime → instrument choice:**
- Flat/inverted: o/n repo competes with / beats bills → PM sells bills, invests in repo (self-reinforcing)
- Steep: term repo locks in rate; bills attractive for rolldown

---

## 10. Matched Book, Tail Trade, Structural Long Bias

**Matched book:**
- = central transmission mechanism of repo market
- Dealers bridge segmented markets that cannot transact directly
- Spread compensates for balance sheet + counterparty + ops risk
- **Real money comes from mismatching it:** deliberate maturity mismatch = pure short-rate risk without market risk on collateral
- This is why the matched book is a profit center, not just plumbing

**Tail trade:**
- Financing a long position with shorter-term repo creates unfinanced residual ("tail")
- Carry earned over N days modifies effective purchase yield of M-day tail by (carry × N/M)
- Entire dealer P/L depends on tail's value at refinancing date
- **"The tail IS the trade"**

**Structural dealer long bias:**
- Shorting requires BOTH buyer AND source (reverse in or borrow)
- Only govies/agencies homogeneous enough to short in size
- At equal conviction, dealers short less than they go long
- → persistent long bid at front end (structural, not signal)

---

## 11. Market Microstructure

**Individualized quotes:**
- Fed funds broker quotes customized by counterparty line usage
- Broker knows each bank's lines better than the banks themselves
- "The quote will be one thing to Citi if they've been buying all day and another to Morgan if they've been selling"
- Offering may exist but not be available to specific buyer (line filled) → broker says "none"

**Pattern market:**
- Many names don't change posture much — constantly one-directional
- Good broker anticipates customer behavior, pre-positions offers before request arrives
- Information about flow precedes the flow itself

**Subject vs firm bids:**
- Subject/under reference = broker must reconfirm before executing
- Fed open market operations → all bids become subject until renewed (brief uncertainty window)

**Day-count arbitrages:**
- Agency 30/360 convention creates anomalies:
  - July 31 = non-day (no interest accrues)
  - February 29 exists in non-leap years
  - February 30 exists (fictional day)
  - Feb 28 → Mar 1 = 3 days of accrual in 1 calendar day → directly tradeable arb
- Dealer quote sheets often do NOT adjust for cross-instrument day-count differences → edge for correct computation

---

## 12. RV Trade Financing Mechanics

**How a leveraged Treasury RV trade is financed:**
- **Long leg:** enter repo → receive cash from dealer → buy Treasury in cash market → pledge back to dealer as collateral
  - Fund is long, financed at RP lending rate
- **Short leg:** enter reverse repo → lend cash to dealer → receive Treasury as collateral → sell in cash market
  - Fund is short, earning RRP rate on cash
- **Dealer role:** packages as "netted package," earns spread between RP lending rate and RRP borrowing rate
  - Dealer spread = cost of leverage for the RV trade

**Leverage mechanics:**
- Maximum leverage = 1 / haircut
- Zero-haircut (common in Treasury repo) → theoretically unlimited leverage
- 2% haircut per leg → $4M margin supports $200M gross exposure = 50x

**P/L decomposition:**
- Total P/L = MTM gain on long + MTM gain on short - net financing cost
- Net financing cost = (RP rate on long - RRP rate on short) × notional × (days/360)
- Trade profitable when convergence > net financing cost
- Repo-reverse spread (dealer's take) = hurdle rate

---

## 13. Daily Settlement Timeline

**Morning sequence:**
- 6:00 AM: trade execution begins
- 7:00-8:30 AM: main execution window (new repos + unwinds of expiring repos)
- 8:30 AM: Fedwire opens → DVP settlement begins
- 8:30 AM-10:00 AM: bulk of repo activity; dealers resolve overdrafts
  - BNY charges per-minute fees for negative clearing balances after 8:30 AM clock starts
- By 10:00 AM: most repo activity complete

**Midday:**
- 12:45-1:15 PM: Fed RRP window (cash lenders park excess at Fed, absorbing imbalances)
- 1:30-1:45 PM: Fed SRF window (dealers/banks borrow from Fed against collateral)

**Afternoon (the critical transition):**
- 3:30 PM: DVP settlement CLOSES and triparty settlement BEGINS simultaneously
  - This is "the pivot" — the single most critical moment in the daily cycle
  - Pre-settlement: dealers allocate collateral from DTCC accounts to BNY longbox; cash lenders transfer deposits to BNY triparty accounts
- 3:30-6:00 PM: BNY triparty settlement platform active
  - New triparty trades settle
  - Securities and cash move between triparty lender and borrower accounts within BNY
  - Fed clearing accounts adjusted based on net flows (SRF repos minus Fed RRPs)
- 6:00 PM: repo day ends
- 7:00 PM: Fedwire extended hours close

**The matched book runs across ALL segments simultaneously:**
- A single dealer operates NCCBR bilateral, Sponsored DVP, Sponsored GCF, CCIT cleared, and Triparty books at the same time
- All segments settle through BNY clearing accounts → BNY is the nexus where all flows converge
- This is why BNY operational failure would cascade instantly across every segment

---

## 14. Trade Expression Through Repo and Funding

**Carry trade structure in repo:**
- Long bond financed at term repo = locked carry for the repo term
- The "tail" after the repo matures = unfinanced residual whose value depends on the prevailing short rate at refinancing
- Term repo eliminates carry uncertainty for N days; the trade is actually a bet on what happens during the remaining M-N days
- Effective purchase yield of the tail = original yield modified by (carry × N/M)

**Curve trade financing:**
- Steepener (long long end, short front end): front-end short generates cash → fund long-end long
  - If front end is special: reverse repo income on the short is below GC → reduces net carry
  - If curve is steep: positive net carry from yield differential minus financing differential
- Flattener (opposite): negative carry in steep curve (paying high yield, earning low yield)
- Carry efficiency of curve trades depends on repo rates at each maturity point, not just bond yields

**Specials as a separate P/L stream:**
- Owning a bond that goes special in repo = earning an additional lending fee independent of bond P/L
- Lending fee = (GC rate - specials rate) × notional × (days/360)
- For OTR bonds: specialness is predictable (auction cycle) and persistent → owning OTR = carry trade + specials income stream
- Basis traders must separate specials carry from bond carry — the "real" carry of a basis position includes both

**Financing arbitrages between segments:**
- Same collateral can trade at different repo rates across segments (triparty vs DVP bilateral vs GCF)
- Funding the same position in different segments has different balance sheet cost
- Segment arbitrage: borrow in cheap segment, lend in expensive segment, earn the spread
- Quarter-end: segment rate differentials spike → arb opportunities widen but balance sheet scarcer

**Repo term structure trades:**
- Term repo rate vs overnight rate reflects market's expectation of overnight rate path
- If you expect rates to stay lower than term implies: lock in term repo → earn the term premium
- If you expect rates to rise faster than term implies: stay rolling overnight → avoid overpaying
- The term repo vs overnight decision IS a rates view, embedded inside every leveraged position

**Window dressing as trade expression:**
- Predictable quarter/year-end distortions create systematic opportunities:
  - Buy repo rate spikes (lend cash at elevated rates) pre-quarter-end
  - Sell the dip in repo rates (borrow at depressed rates) post-quarter-end
  - Position for spread widening between nettable and unnettable segments at reporting dates
  - Calendar spread in futures: sell front-month near quarter-end (as shorts roll to avoid delivery in constrained environment)

---

## 15. Dealer P/L Sources and Market Structure

**Dealer P/L decomposition (8 sources, different risk/size profiles):**
1. **Bid-ask spread:** low risk, steady base income from market-making
2. **Customer servicing fees:** near-zero risk, moderate flow
3. **Directional position profits:** high risk, lumpy, volatile — proprietary views on rates
4. **Carry (coupon minus repo):** medium risk, curve-dependent — long positions earn positive carry in steep curves
5. **Proprietary products:** medium risk, structural — structured notes, exotics
6. **Matched book mismatching:** medium risk, rate-dependent — deliberate maturity gaps as pure rate speculation
7. **Arbitrage (RV, basis):** low-to-medium risk, opportunistic — cross-instrument mispricings
8. **Trade ideas to retail:** zero risk, relationship-driven — research/ideas generate flow and commissions

**Treasury secondary market structure:**
- D2C (~50% of volume): RFQ model (Tradeweb, Bloomberg, MarketAxess) — dealers quote bid/ask to clients
- IDB (~50% of volume): CLOB model (BrokerTec, Nasdaq/eSpeed) — anonymous electronic matching
- PTFs (principal trading firms: XTX, Virtu, Jump) ≈ 60% of IDB volume
- D2C and IDB are linked through dealer inventory: client flow in D2C hedged in IDB, and vice versa

**GCF netting mechanics:**
- 3:05 PM: FICC matches, nets, and novates all GCF trades → collapses gross to net per dealer
- This netting event is critical for inter-dealer balance sheet efficiency
- Determines how much balance sheet capacity is freed for the afternoon triparty settlement

---

## 16. FHLB Discount Note Cycle and MMF Allocation

**FHLB discount note funding cycle (hidden plumbing):**
1. FHLB issues overnight discount note → dealer buys
2. Dealer places DN with MMF (MMF buys as investment)
3. FHLB receives cash → lends via fed funds to FBO
4. FBO deploys into repos/reserves (earns IORB or repo spread)
5. Next day: unwind, repeat
- This continuous issuance cycle IS the "FHLB window" that funds the FHLB→FBO→IORB arbitrage chain
- MMFs are the ultimate cash source; FHLBs are the intermediary; FBOs are the deployers

**MMF allocation as trade framework:**
- MMFs are rate-maximizing allocators (~$6T in assets)
- Their allocation decision between repos, T-bills, agency DNs, CP, and Fed RRP determines where system liquidity resides
- **Decision tree:**
  - T-bill yield > repo rate + threshold → buy bills (exit RRP, reduce repo lending)
  - Private repo rate > RRP rate + threshold → lend in private repo (exit RRP)
  - Private repo ≈ RRP → park at Fed (risk-free)
  - CP/DN yields attractive → diversify into credit
- **Behavioral patterns:**
  - Normal: spread across repos, bills, some RRP
  - QT progressing: rotate from RRP → bills (as bill supply rises from Treasury reissuance)
  - Quarter-end: shift to RRP (dealers shrink → can't absorb MMF cash → park at Fed)
  - Stress: flight to RRP or MMF redemptions → cash hoarding
  - Rate cut expectations: front-run by buying longer bills → reduces excess liquidity in overnight

---

## 17. Regime Taxonomy

| State | Name | Key Dynamic |
|-------|------|-------------|
| S1 | Ample Reserves | RRP high, reserves abundant, rates in narrow corridor band |
| S2 | Transitional Drain | RRP declining under QT, rates drifting toward upper corridor |
| S3 | Scarce Reserves | RRP ≈ 0, reserves unevenly distributed, repo rates spike above IORB |
| S4 | Quarter/Year-End | Predictable calendar distortion: rate spike, balance sheet shrinkage |
| S5 | Offshore Dollar Shortage | FX swap rates spike above swap line rate, CBs activate lines |
| S6 | Shadow Cash Stress | MMF redemptions, repo freeze, CP seizure; Fed emergency facilities |

**Transitions:** S1→S2 (QT begins), S2→S3 (RRP→0, uneven reserve distribution), Any→S4 (reporting dates, reverts after), Any→S5 (global dollar shortage), Any→S6 (shadow bank run), S6→S1 (Fed emergency + confidence restored)

---

## 14. Historical Episodes

**Sept 2019 SOFR spike** [S2→S3 transition]:
- Secured rates spiked above IORB → proved reserve scarcity
- Transition from ample to scarce can be abrupt and localized (aggregate adequate, distribution not)

**March 2020 ETF discounts** [AP bridge fragility]:
- APs couldn't fund arb positions when repo seized → ETF discounts blew out
- ETF liquidity = derivative of repo/CP plumbing health

**COVID SLR exemption** [balance sheet constraint confirmed]:
- Temporary exclusion of reserves/Tsys from SLR → dealer capacity immediately expanded
- Removal → capacity contracted. QED: SLR is the binding constraint.

---

## 15. Doctrines

- "Balance sheet is the scarce resource, not cash"
- "Nettable is cheap; unnettable is expensive"
- "3:30 PM is the pivot"
- "RRP is the buffer"
- "Stigma makes the ceiling soft"
- "FBOs are the invisible hand of EFFR"
- "The answer lies in the shadows" — haircuts > rates as leading indicator
- "The real money in a matched book comes from mismatching it"
- "The tail IS the trade"
- "Trading is much like a poker game" — bluffing, line management, information asymmetry, timing
- "MMFs are the swing allocator"
- "QT drains the path of least resistance"
- "Window dressing is predictable" — and tradeable
- "Central clearing is the future"
- "Shadow banks are fragile intermediaries"
- "Effective money = traditional aggregates + shadow money"
- "Dealer quote sheets often do not adjust for day-count differences" — edge for correct computation
