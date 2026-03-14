# Analyst Brain: Siddhartha Jha (v3 delta)

**Source:** *Interest Rate Markets: A Practical Approach to Fixed Income* (2011)
**Domain:** Carry Trades / Relative Value / Swap Spreads / Hedging / Treasury Basis / Conditional Trades / Vol

**Core thesis:** Trading rates = understanding mechanical relationships between instruments, not forecasting direction. Carry, rolldown, convexity, mortgage flows, basis mechanics, and options conditionality determine who wins and who loses. Express views with maximum specificity and conditionality. Key risk dimensions (curve, vol, spread, financing) move independently and can dominate P/L even when direction is correct.

---

## 1. Carry Trade Mechanics

**P/L decomposition:** P/L = carry (net income from holding) + mark-to-market (price change)
- Ideal carry trade: maximize carry term, minimize MTM term
- Carry trades work best when MTM vol is low → income dominates P/L

**Carry-to-volatility ratio:**
- = (carry + rolldown, annualized) / (yield vol, annualized)
- THE comparison metric across instruments, tenors, and trade structures
- Higher ratio = carry earned more efficiently relative to MTM uncertainty

**Carry vs rolldown:**
- Carry (coupon minus financing) = lockable via term repo
- Rolldown (price/yield gain from aging) = NOT lockable; depends on curve shape persisting
- For futures/forwards: entire "carry" is rolldown (no coupon income)
- Practical distinction matters less than it appears — both aim for steady return while controlling vol

**Weighted carry trades:**
- Outright carry trades expose to broad market moves that overwhelm carry
- Curve/butterfly combinations maintain high carry but reduce vol through offsetting exposures
- **Weighting method:** regress daily changes of one leg against the other; beta = weight that removes vol differential
- Weighted trade's vol = std dev of weighted spread's daily changes (much lower than either leg)
- Weighted trade often has higher carry/vol ratio than outright despite lower absolute carry

**Carry-efficient directional trades:**
- When directional view has negative carry → find correlated trade with less negative carry
- Correlation × beta = effective exposure
- Example: weighted 2s/5s flattener as carry-efficient short 2Y substitute (high correlation, much less negative carry)

---

## 2. Carry Trade Crowding

**The cycle (timeless, repeats):**
1. Calm markets → carry looks attractive (low historical vol)
2. Herding into the same trades → positions saturate
3. Small spark (data, hedging flow, policy signal) scares some participants
4. Successive exit waves → vol spikes → carry/vol collapses
5. Months of carry erased in days

**Detection signals:**
- **Asymmetric price response:** muted moves on favorable news + outsized on unfavorable = crowded long (no marginal buyer left but plenty of potential sellers)
- **Cross-market correlation:** when unrelated trades across asset classes become abnormally correlated (e.g., front-end rates carry and FX carry pairs) → same global flow pool chasing same trades → unwind in one = warning for all
- **Position data:** weekly futures positioning; rapid accumulation toward historical extremes = necessary (not sufficient) crowding signal

**Historical illustration — 2009 front-end carry unwind:**
- Fed on hold near zero → obvious 2Y carry trade
- Positioning built up visibly over months in futures data
- May/June catalyst (faint optimism + mortgage hedging buildup)
- Yields surged; carry traders exited in waves; months of carry erased
- Being right on fundamentals (Fed did stay on hold) does not protect against positioning dynamics

---

## 3. Relative Value

**Dislocation attractiveness:**
- = (current level - long-run average) / vol of the spread
- 30bp dislocation in 5bp vol spread = compelling
- 30bp dislocation in 100bp vol spread = noise

**The 50:50 butterfly problem:**
- 50:50 wing weight embeds hidden factor exposures (body yield level + wing curve slope)
- These hidden factors can dominate the butterfly → "RV trade" is actually a disguised directional bet
- **Fix:** multiple regression — regress 50:50 butterfly against body yield AND wing curve simultaneously
  - Partial betas reveal hidden factor sensitivities
  - Residual = pure relative value component
  - Trade the residual, not the raw butterfly
- **Reason equal weighting fails:** implicitly assumes equal sector volatility. When Fed on hold, 2Y far less volatile than 10Y → 50:50 gives 10Y too much weight

**Curve-and-level-neutral butterfly weights:**
- From multiple regression with beta1 (body yield) and beta2 (wing curve):
  - 2Y wing weight = (0.5 + beta2) / (1 - beta1)
  - 10Y wing weight = (0.5 - beta2) / (1 - beta1)
- Shortcut: regress body yield directly against both wing yields; coefficients = risk weights
- **These are DV01 weights, not notional weights**

**DV01 to notional conversion:**
1. Start from body notional → compute total body DV01
2. Apply wing risk weight as % of body DV01
3. Divide by wing's per-million DV01 → wing notional
- Common mistake: treating regression weights as notional weights (grossly mismatches legs because DV01/notional varies enormously across maturities)

**Mean reversion failure = exit signal:**
- If dislocation refuses to revert for extended period → underlying fundamentals may have changed → long-run average itself has moved
- Persistent non-reversion = evidence to exit, not patience signal

---

## 4. Swap Spread Mechanics

**Setup:**
- Swap spread = swap yield - Treasury yield at matched maturity
- Two principles: (1) match swap maturity exactly to bond maturity (reduce curve exposure), (2) equalize DV01 of both legs (reduce rate-level exposure)
- Notionals differ because bond and swap DV01/unit notional differ (coupon differences)
- With DV01 matched: profit only if spread changes, not if rates move in parallel

**Matched-maturity vs headline:**
- Headline: 5Y swap yield minus 5Y Treasury (but bond may have been issued months ago)
- Matched-maturity: swap maturity exactly matches bond maturity
- In steep curves: maturity mismatch between headline and matched creates meaningful noise → use matched

**Swap spreads as fiscal view:**
- More efficient than shorting outright Treasuries for deficit expression
- Swap leg removes pure rate-level noise
- Structural deficit (persists beyond cycle) → multi-year narrowing effect
- Cyclical deficit (reverses with recovery) → limited impact

---

## 5. Swap Spread Driver Rotation

**Key insight:** same spread, completely different dominant factors depending on regime. Drivers rotate, not additive:

| Driver | When Dominant | Spread Effect |
|--------|--------------|---------------|
| Bank credit | Crisis (systemic stress) | Widening (overwhelming) |
| Mortgage hedging | Day-to-day, normal markets | Widening in selloffs, narrowing in rallies |
| Duration extension | After sustained low rates → rate rise | Intense widening lasting months |
| Treasury supply / deficit | Slow-moving, structural | Narrowing (more Treasury supply cheapens Tsys) |
| Pension demand | Long end, multi-decade | Narrowing (structural receiving; drove 30Y negative) |
| Corporate issuance | Seasonal (Sept, Jan) | Narrowing (issuer receives fixed in swap) |
| Liquidity | Transition periods | Narrowing when liquidity increasing |

**Mortgage extension feedback loop (dominant short-term):**
1. Rates fall → refi boom → flood of new long-duration mortgages
2. Rates rise → prepayments slow → duration extends
3. Mortgage holders forced to sell duration (pay in swaps)
4. Paying pressure widens spreads
5. Can persist for months in intense form
- Reverse in rallies: duration shortens → hedgers receive in swaps → narrowing pressure
- Makes spreads directional with yields even though spreads aren't inherently rate-level product

**30Y negative spreads:**
- Not credit signal (government vs bank risk)
- Demographics: pension fund demand for long-dated fixed income to match liabilities
- Swaps preferred over Treasuries: unlimited size, no auction dependence
- Structural, multi-decade phenomenon

**Tactical pattern:**
- Heavy Treasury supply (auctions approaching) → spreads tend to narrow
- Post-auction → narrowing often reverses
- Corporate issuance seasonal: Sept + Jan narrowing from hedging flow

---

## 6. Treasury Futures Basis

**Net basis at expiry = option payoff:**
- Low-duration CTD: call on yields (zero as yields fall, rises as yields rise past switchover)
- High-duration CTD: put on yields (zero as yields rise, rises as yields fall past switchover)
- Medium-duration: straddle (zero in range, rises in either direction)

**Positions:**
- Short futures holds delivery option
- Long basis (buy bond, sell futures) = long volatility (retains optionality)
- Short basis (sell bond, buy futures) = short volatility (gives up optionality)
- At last delivery date: futures must converge to CTD converted forward, else arb

---

## 7. Conditional Trades

**Purpose:** take curve/spread view only in specific rate scenarios, expire worthless in others

**Conditional steepener (canonical example):**
- Sell payer swaptions on short end + buy payer swaptions on long end (same expiry)
- Rates fall → both expire worthless (conditional protection)
- Rates rise → both exercised → investor enters DV01-neutral steepener

**Weighting:**
- DV01-weight option notionals so exercise produces zero P/L for parallel shift
- Required notional ratio = long-end DV01 × notional / short-end DV01

**Premium neutrality:**
- "At the forwards" = zero net premium (conditional trade initiates at current forward curve)
- "Worse than forwards" = paying premium → strikes adjusted → entry point worse than current market
- **Rule:** if worse than forwards, just do the outright trade (option premium buys insurance against scenario you believe in)

**Expiry choice:**
- <3 months typical (hold to exercise design)
- Curve directionality with yields can be volatile over longer horizons

**Implied vol comparison:**
- Bought leg has higher implied vol → premium goes out (net cost)
- Sold leg has higher implied vol → premium comes in (net receipt)

**Conditional spread trades:**
- Same framework applies to swap spreads conditional on yield direction
- Mortgage-driven widening in selloffs → conditional widener using payer swaptions isolates mortgage view from rally risk

---

## 8. Hedging as Risk Conversion

**Core principle:** hedging converts more volatile risk (outright rates) into less volatile risk (spread/basis)
- Not risk elimination — risk transformation
- Worth doing only if outright exposure vol >> resulting spread/basis vol

**Three criteria for hedge instrument selection (in priority order):**
1. **Tracking error:** how closely hedge instrument moves with asset. Dominates in stress. During calm, differences are small.
2. **Relative value:** relevant when tracking error between instruments is similar. Widening swap spreads → swaps are better hedges (they underperform WITH assets). Narrowing → Treasuries better. Creates tactical rotation opportunity.
3. **Carry:** different hedge tenors/instruments carry differently. In steep curves, optimizing carry across nearby maturities is worth doing when tracking error impact is small.

**Treasury hedges fail in flight-to-quality:**
- Crisis → investors flee to Treasuries → Treasury yields fall
- Risky bond loses (spread widens) AND Treasury short loses (Treasury rallies)
- Both legs lose simultaneously
- **Swap hedges perform better in stress** because swaps underperform alongside credit assets
- **Caveat:** swap spread response to crisis is not one-directional:
  - Initial: credit concerns widen spreads (swap hedges work)
  - If rates fall enough: mortgage receiving narrows spreads (can reverse advantage)
  - Sustained crisis (2008): credit concerns dominate
  - Contained scare: mortgage flow can dominate quickly

**Yield betas:**
- Assets don't move 1:1 with hedge instruments even after DV01 matching
- Yield beta = regression slope of asset yield changes on hedge yield changes
- Hedge notional = (asset DV01 / hedge DV01) × asset notional × yield beta
- At yield beta 0.8: raw DV01 ratio overhedges by 25%
- **Unstable across regimes** — beta estimated in calm may be wrong during stress when hedge matters most

**Futures hedge — CTD complication:**
- Common approximation: DV01 = CTD DV01 / conversion factor (assumes constant CTD)
- Fails when CTD switch probability is nonzero → effective DV01 changes discontinuously
- Option-adjusted hedge ratio more accurate but requires model
- 2008 lesson: massive hedging demand cheapened 10Y futures far beyond normal; usual RV guidelines broke

---

## 9. Butterfly Weight Derivation

**Problem:** 50:50 butterfly ≠ pure RV (hidden factor exposures)

**Solution (regression-based):**
1. Regress 50:50 butterfly against body yield + wing curve → partial betas (beta1, beta2)
2. Neutral weights:
   - 2Y wing = (0.5 + beta2) / (1 - beta1)
   - 10Y wing = (0.5 - beta2) / (1 - beta1)
3. Or: regress body yield directly against both wing yields → coefficients = risk weights

**DV01 → notional conversion:**
- Body: set base notional → compute body DV01
- Wing: apply risk weight % of body DV01 → divide by wing per-million DV01 → wing notional

---

## 10. Vol Quoting: Normal vs Lognormal

- **Black-Scholes** is a premium-to-vol converter, not a pricing model
  - Analogous to duration converting prices to yields — provides common comparison unit (implied vol)
  - Assumptions known to be wrong; utility is in the transformation
- **Lognormal (Black model):** vol in % per year. Appropriate for equities/commodities.
- **Normal (Bachelier model):** vol in absolute bp per year. Appropriate for rates.
  - Rates move in absolute terms (Fed hikes 25bp regardless of level) not percentage terms
- **Conversion:** normal bp vol ≈ lognormal % vol × forward rate
  - If forward 10Y = 4% and lognormal vol = 20% → normal vol = 80bp/yr
  - Daily bp vol = annual / sqrt(251) ≈ annual / 15.84
- **Divergence near extremes:**
  - Near-zero rates: lognormal vol explodes (small absolute moves = enormous % moves); normal stays well-behaved
  - High rates: normal vol understates %-move risk
  - Wrong convention → severe mispricing, especially in unusual rate environments

---

## 11. Gamma/Theta Mechanics and Delta Hedging

**Core P/L relationship (ex-delta, ex-vega):**
- Option P/L ≈ f(realized vol - implied vol)
- Long option: profitable when realized vol > implied vol
- Short option: profitable when realized vol < implied vol
- Implied vol = breakeven: the level of underlying movement needed for gamma P/L to overcome theta decay

**Theta = cost of gamma spread over time:**
- Gamma P/L = ½ × gamma × (move)²
- Theta P/L = theta × days
- Gamma and theta profiles have identical shapes across strikes — not coincidence
- ATM options: highest gamma AND highest theta

**Delta hedging as vol monetization:**
- Remove delta exposure by offsetting with underlying → isolates gamma/theta/vega
- Long option + delta hedge: constantly buying low, selling high (beneficial mechanics)
- Short option + delta hedge: constantly buying high, selling low (painful mechanics)
- With delta hedged and implied vol unchanged: P/L = gamma P/L + theta P/L = f(realized - implied)

**Delta hedge frequency optimization:**
- **Mean-reverting market:** high short-window vol, low long-window vol
  - Long option: hedge frequently → captures high realized vol on short timeframes
  - Short option: hedge infrequently → avoids buying high and selling low repeatedly
- **Trending market:** low short-window vol, high long-window vol
  - Long option: hedge infrequently → captures larger cumulative moves
  - Short option: hedge frequently → limits the damage from directional trend
- In practice: impossible to know regime in advance → use guidelines (fixed intervals or delta threshold triggers) with regime-aware adjustments

**Market conventions:**
- "Trading gamma" = trading short-dated options (gamma dominates P/L near expiry)
- "Trading vega" = trading long-dated options (vega dominates P/L with time to expiry)
- Not mutually exclusive — just reflects which Greek dominates P/L

**Skew and hidden delta:**
- Black-Scholes assumes constant vol across strikes; reality: out-of-the-money puts often have higher implied vol than ATM
- As underlying moves, the implied vol corresponding to the new strike changes → creates extra vega P/L beyond pure BS delta
- Standard delta underestimates true sensitivity when skew is present

**Embedded options in rates products:**
- Mortgage holder = short a call on rates (homeowner can refinance if rates fall)
- Callable bond holder = short a receiver swaption
- Two hedging approaches:
  1. **Dynamic hedging:** continuously adjust rate hedge as delta changes (= delta hedging the embedded option = "convexity hedging")
  2. **Static option hedge:** match gamma of embedded option using swaptions → reduces need for dynamic hedging but costs premium upfront
- Option hedge = long vol position; dynamic hedge = short vol position (pays theta in the form of buy-high-sell-low rebalancing)
- Trade-off: option hedge costs premium but provides certainty; dynamic hedge is cheaper in calm but unbounded cost in volatility spikes

**Swaption conventions (rates-specific):**
- Receiver swaption = right to enter receiving swap = positions for lower rates (equivalent to call on rates)
- Payer swaption = right to enter payer swap = positions for higher rates (equivalent to put on rates)
- Notation: expiry × tail (e.g., 1Y × 10Y = 1-year option on 10-year swap)
- Multilook (caps/floors): chain of caplets, each independently checking rate at quarterly intervals
- Singlelook (swaptions): one check at expiry
- Midcurve options: expire soon but settle on forward contract → cheap way to trade forward rate views

---

## 12. Vol Spread Trades and Structuring

**Vol spread trades** express relative views on implied or realized vol between different parts of the surface, analogous to curve trades in rate space.

**Two types:**
- **Tail switch:** same expiry, different underlying rates (e.g., buy 6M×2Y, sell 6M×10Y)
- **Expiry switch:** same underlying rate, different expiries (e.g., buy 6M×10Y, sell 3Y×10Y)

**Weighting — vega-neutral vs gamma-neutral:**
- **Vega-neutral:** equate total vega of both legs → P/L immune to parallel shifts in implied vol → trades the implied vol spread between the two legs
- **Gamma-neutral:** equate total gamma of both legs → P/L immune to parallel shifts in realized vol → trades the realized vol spread
- For tail switches (same expiry): gamma-neutral ≈ vega-neutral (gamma and vega scale similarly)
- For expiry switches (different expiry): the two produce very different trades:
  - Short-dated options: high gamma, low vega
  - Long-dated options: low gamma, high vega
  - Vega-neutral expiry switch: overweights short-dated leg (to match vega) → leaves trade long gamma
  - Gamma-neutral expiry switch: overweights long-dated leg (to match gamma) → leaves trade short vega
- **Rule:** when setting up any switch, track ALL risk parameters — neutralizing one can leave large unintended exposure on the other

**Structural supply and demand for vol (who is structurally long/short):**
- **Demand (structurally short vol, needs to buy):**
  - Mortgage GSE portfolios: short prepayment option → buy long-expiry, intermediate-tail swaptions (e.g., 3Y×10Y)
  - Mortgage servicers: short vol via prepayment sensitivity → buy short-expiry, intermediate-tail options → affects front-end of vol surface
  - Both sources concentrate in 5-10Y underlying rates → intermediate vol structurally supported
- **Supply (structurally long vol, sells into market):**
  - Callable debt issuers: issuing callable = long a call option on rates → sell swaptions to offset
  - Trust preferred notes (20Y-perpetual, 5-10NC): issuers sold 5Y×30Y type swaptions → depressed long-end vol when issuance heavy
  - Exotics desks: depends on structured note flows currently popular; LIBOR range accrual notes → dealer long caps → sells caps → depresses cap vol vs swaption vol
- **Implication:** vol surface shape is not just about rate expectations — it's about structural flows from mortgages, issuance, and exotics at specific expiry/tail points

**Caps vs swaptions — structural difference:**
- Cap vol ≈ average volatility of underlying forward rates (portfolio of independently-evaluated caplets)
- Swaption vol ≈ volatility of the average of forward rates (single option on swap rate)
- Difference = correlation between forward rates
- In practice, primary P/L driver of cap/swaption spread: shape of vol surface along short-tail vs long-tail and short-expiry vs long-expiry dimensions

**Yield curve spread options (YCSOs):**
- Option on the spread between two yields (e.g., 3M×2s/10s call struck at 150bp)
- Curve call = steepener with asymmetry; curve put = flattener with asymmetry
- Multilook version = curve cap (looks quarterly)
- **Key difference from swaptions:** YCSO payoff is linear in yield spread (no convexity) → delta hedge uses swaps (which have convexity) → requires convexity adjustment to the strike, same principle as ED futures convexity bias
- Convexity adjustment depends on vol of underlying rates

**Forward volatility:**
- Premium paid at inception; swaption activates at future date at ATM level (floating strike)
- Floating strike → pure exposure to implied vol → no delta hedging needed
- Clean way to trade vol expectations but currently high transaction costs

**Path dependency of delta-hedged P/L:**
- Even with perfect delta hedging, P/L depends on the path underlying takes, not just total realized vol
- Greeks change as underlying moves: gamma at the original strike ≠ gamma at +100bp from strike
- If underlying drifts slowly to +100bp, then becomes volatile there → gamma is lower → less profitable than if same vol occurred near the original strike
- Wider range of strikes partially mitigates path dependency but cannot eliminate it

**Risk reversals:**
- 25-delta risk reversal = 25-delta call IV minus 25-delta put IV
- Selling the put and buying the call: gamma flips sign as underlying moves (short gamma near call strike, long gamma near put strike)
- In rates: risk reversal direction depends on rate level (near zero → steep positive skew; high rates → more symmetric)

---

## 13. Swap Equivalences and Atomic Decomposition

**FRA = single-set swap; swap = strip of FRAs:**
- A forward rate agreement is economically a swap with a single reset period
- A swap is a chain of FRAs at successive reset dates
- Similarly: a swap is a strip of Eurodollar futures (adjusted for convexity bias)
- This equivalence means swap rates can be built bottom-up from either FRA strips or ED strips

**Implication for trade construction:**
- To modify a swap position for a single reset period without unwinding: overlay a FRA
- Example: you're paying fixed and receiving LIBOR in a swap. You suddenly expect a rate drop at the next reset. Do a FRA that locks in the next LIBOR reset → you've reversed the swap for one period without touching the rest.
- Strip of FRAs = full swap reversal. Single FRA = surgical modification of one reset.

**Atomic decomposition of rate products:**
- Caplet = option on a single forward rate
- Cap = strip of caplets (multilook)
- Swaption = option on a swap rate (singlelook)
- The distinction between "option on the average of forwards" (swaption) and "average of options on forwards" (cap) is the correlation between forward rates

**Bermudan swaptions — dynamic option character:**
- Multiple exercise dates → optimal exercise shifts with rate levels
- Rates decline (receiver Bermudan): exercise date moves closer → effectively shorter-expiry option → gamma rises, vega falls
- Rates rise (receiver Bermudan): exercise date moves further → effectively longer-expiry option → vega rises, gamma falls
- Creates unique risk profile: the greeks themselves are directional with the underlying
- Used primarily to hedge callable bonds (which have exercise at set intervals, not continuously)

**Range accrual notes — vol implications:**
- Pay coupon if underlying stays in range → dealer is long a cap at upper boundary, long a floor at lower
- After issuance: dealer hedges by selling caps → depresses cap vol relative to swaption vol
- Tracking structured note issuance is essential for understanding cap-swaption vol spread

---

## 14. Historical Episodes

**2009 front-end carry unwind** [crowding cycle]:
- Fed on hold → obvious 2Y carry; positioning built over months
- May/June: faint optimism + mortgage buildup broke calm → months of carry erased in days
- Right on fundamentals ≠ protected from positioning dynamics

**Summer 2003 mortgage extension** [duration extension feedback]:
- Refi boom at multi-decade lows → flood of long-duration mortgages
- Rates rose → forced paying in swaps → 10Y spread +40bp over one summer
- Lasted months; monitoring refi indices anticipates buildup

**30Y negative spreads (2008+)** [demographics > credit]:
- Pension fund demand structural → first time swap < Treasury at long end
- Not a credit signal; liability-matching behavior over decades

**2007-08 crisis spread widening** [driver rotation to extreme]:
- 2Y spreads: 30bp stable → >150bp
- Bank credit fear overwhelmed all other factors
- Multi-factor analysis becomes irrelevant during systemic events

---

## 12. Doctrines

- "Carry is known; volatility is uncertain" — carry/risk ratio is the metric, not carry alone
- "High carry often = high risk" — crowding is inevitable
- "If it looks obvious, too many people are already in it"
- "Muted response to good news, outsized to bad = crowded trade"
- "Express views with maximum specificity and conditionality"
- "If worse than forwards, just do the outright trade"
- "50:50 butterflies embed hidden factor exposure"
- "If mean reversion fails for long, the mean has moved"
- "Swap spreads isolate fiscal views better than outright Treasuries"
- "Mortgage hedging is the dominant short-term swap spread driver"
- "The same spread responds to completely different drivers in different regimes"
- "Rolldown cannot be locked in; carry can"
- "Weighted trades can have higher carry/vol than outright, despite lower absolute carry"
- "Cross-market carry correlation is a crowding signal"
- "For every negative-carry directional view, a carry-efficient alternative exists"
- "Hedging converts outright risk to basis risk — make sure basis vol << outright vol"
- "Treasury hedges fail in flight-to-quality; swaps track credit better in stress"
- "Yield betas are unstable across regimes"
- "Risk weights are DV01 weights, not notional weights"
- "Black-Scholes is a vol-premium converter, not a pricing model"
- "Normal vol for rates, lognormal for equities — and the distinction matters near zero"
