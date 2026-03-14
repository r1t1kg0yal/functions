# Analyst Brain: Burghardt & Belton (v3 delta)

**Source:** *The Treasury Bond Basis* (3rd ed., 2005)
**Domain:** Treasury Futures Basis / Delivery Options / CTD / Basis Trading / Vol Arb

**Core thesis:** Treasury futures = forward contracts + bundle of real options held by the short. Conversion factor system creates all optionality because it equalizes bonds at only one yield level. Futures price = minimum of CF-adjusted forward prices = option-like payoff.

---

## 1. Basis Decomposition

- **Identity:** Basis = Carry + BNOC (exact, exhaustive, no third channel)
  - Basis = cash price - (CF × futures price)
  - Carry = coupon income - financing cost (deterministic, lockable via term repo)
  - BNOC = market price of short's delivery options (stochastic)
- **Implication:** if carry is locked, all basis uncertainty is in BNOC
- **Positive curve:** carry > 0, basis > BNOC
- **Inverted curve:** carry < 0, basis < BNOC
- **Intervening coupon:** split carry calc; financing cost resets after coupon payment (full price drops by coupon amount)
- **Implied Repo Rate (IRR):** financing rate that makes basis = 0
  - IRR > term RP ⟺ BNOC < theoretical option value ⟺ basis cheap ⟺ futures rich
  - Chain runs both directions; connects all basis metrics

---

## 2. Minimum Envelope

- Futures price = min(CF-adjusted forward prices) across deliverable set
- Geometrically: smooth curve below and tangent to each bond's converted forward price
- Distance from any bond's converted forward to envelope = that bond's BNOC
- **CTD BNOC** = pure delivery option value (at-the-money option)
- **Non-CTD BNOC** = delivery option value + expensiveness premium (in-the-money)
- Only CTD's BNOC directly measures optionality cost

---

## 3. CTD Selection

Two orthogonal rules, operating simultaneously:

- **Duration rule (yield level):**
  - Yields > reference: high-duration bonds CTD (prices fell more than CF implies)
  - Yields < reference: low-duration bonds CTD (prices rose less than CF implies)
  - Yields ≈ reference: multiple contenders, switch option most valuable
- **Yield rule (yield spread):**
  - Among similar-duration bonds: highest-yielding bond is CTD
  - Spread changes can trigger CTD switches without level changes
  - Can override the duration rule

---

## 4. Spread Dampener and Moving Strike

- **Mechanism:** systematic curve flattening as yields rise / steepening as yields fall
- **Effect:** equivalent to moving the crossover yield away from current yield as yields move
- **Result:** switches harder to trigger than parallel-shift models imply
- **Moderate correlation:** reduces switch option value vs. parallel-shift assumption
- **Saturated correlation (±1):** kills switch option entirely → "gamma death"

**Death of Gamma (composed chain):**
1. Spread-yield correlation saturates toward ±1
2. Effective crossover yield moves to unreachable distance
3. Switch option value → 0
4. CTD permanently entrenched
5. Negative convexity zone vanishes
6. BNOC collapses to carry + trivial EOM option
- **Recovery:** requires exogenous shock breaking the correlation regime

---

## 5. Three Delivery Options

Short holds all three; long holds none. Positive aggregate value → futures depressed below CTD forward.

**Quality (switch) option:**
- Right to deliver any bond in the set
- Value depends on: proximity to crossover, yield vol, spread dampener
- Highest value when multiple bonds near CTD status
- Behaves like option on yield level

**End-of-month (EOM) option:**
- After last trading day: invoice price locked, but short chooses delivery bond
- **Critical insight:** selection metric changes from duration to BPV (absolute dollar sensitivity)
- High-coupon bonds (high BPV, low duration) can become CTD post-expiry — reverses normal ordering
- Crossover calculation: threshold bp shift = BNOC difference / BPV difference between adjacent bonds

**Timing option:**
- Choice of delivery day within delivery month
- Positive carry → deliver last day (maximize carry income)
- Negative carry (inverted curve) → deliver early
- Wild card: settlement price set at 2:00 PM, declaration deadline 8:00 PM → intraday moves after fix create delivery opportunities

---

## 6. Basis as Synthetic Options

- Buying basis = buying volatility; selling basis = selling volatility
- Net basis at expiry maps to standard option payoffs:
  - **Low-duration CTD:** call on yields (zero as yields fall, rises as yields rise past switchover)
  - **High-duration CTD:** put on yields (zero as yields rise, rises as yields fall past switchover)
  - **Medium-duration:** straddle (zero in range, rises in either direction)
- Full options toolkit (greeks, vol surfaces) applies to basis positions

**Option-Adjusted Basis (OAB):**
- OAB = observed BNOC - theoretical delivery option value
- OAB > 0: basis rich, futures cheap → sell basis
- OAB < 0: basis cheap, futures rich → buy basis
- Persistent OAB < 0 = structural selling pressure (mortgage hedgers, dealer short-basis)

**Vol arb:**
- When basis market and listed options disagree on implied vol → buy cheap, sell rich
- Limitation: horizon mismatch (basis and options expire at different times) → residual vega risk

---

## 7. Squeeze Mechanics

**Buffer until break:**
- Deliverable supply absorbs open interest until physical constraint binds
- Pre-break: normal options dynamics
- Post-break: market transitions from option-pricing to failure-probability regime

**Squeeze cascade (composed chain):**
1. Bond goes special in repo (borrowing demand > supply)
2. OI exceeds deliverable float of CTD
3. RP rate spirals toward 0% or negative
4. Delivery failure becomes probable
5. BNOC goes negative
6. Calendar spread dislocates

**Negative BNOC:**
- Not free money — prices delivery failure probability
- Implied failure probability = CTD BNOC / (CTD BNOC - 2nd CTD BNOC)

**Paradox of best trade:**
- Most attractive short basis = greatest squeeze risk
- Crowd positioning creates the scarcity it seeks to exploit
- Reflexivity: richening → attracts shorts → borrowing demand → further richening

---

## 8. Trading Mechanics and P/L

**Asymmetric payoff:**
- Selling basis: capped upside (BNOC earned slowly), uncapped downside (realized suddenly)
- Buying basis: inverts this
- Every basis trade = volatility position with this signature

**Hidden frictions:**
- RP/RRP spread: invisible in quoted basis, directly enters P/L
- Specialness can amplify from modest spread to hundreds of bp
- "Real" carry ≠ "screen" carry by this friction

**The tail:**
- At futures expiry: hedge ratio jumps discretely from CF-weighted to 1:1
- Not gradual — mechanical phase change
- Creates unhedged price risk window
- **Rule:** cover the tail as close to final bell as possible

**BNOC vs IRR divergence:**
- Two bonds with identical BNOC but different prices → different IRR
- Higher-priced bond is cheaper to deliver on IRR basis
- BNOC ignores price levels; IRR incorporates them

**Calendar spread mispricing = OAB with opposite sign:**
- Buying a cheap spread ⟺ buying cheap futures ⟺ buying cheap basis

**OTR basis:**
- Short selling OTR basis is always negative carry (OTR trades special in repo)
- Reverse RP income insufficient for coupon cost
- Yield spread move must overcome carry drag

---

## 9. Four Hedge Ratios

- **Conventional:** CF-based. Ignores betas and correlation.
- **Yield-beta adjusted:** conventional × regression slope of cash on futures yields. Reduces average tracking error; unstable across regimes.
- **Yield delta:** option-model sensitivity incorporating CTD switch probability. Most complete theoretically.
- **Minimum variance:** minimizes historical hedge error variance. Empirically driven.

**Key insight:** all four converge only when correlation = 1. At typical correlation (e.g. 0.88), they can differ by 40%.

- Spot DV01 ≈ 50× repo DV01
- Complete hedge requires offsetting both, but repo component small enough to usually ignore

---

## 10. OTR Basis Cycle

**Auction-driven pattern (timeless, repeats each cycle):**
- Post-auction: short hedging demand → OTR goes special in repo → richens on curve
- Pre-next-auction: market prepares for new supply → OTR cheapens relative to old issue

**Trading the cycle:**
- Early in cycle (richening phase): buy OTR basis → profits as OTR-old spread narrows
- Late in cycle (cheapening phase): sell OTR basis → profits as spread widens
- **Constraint:** selling OTR basis is always negative carry (OTR special in repo)

---

## 11. Calendar Spread Trading

**Fair value:** futures fair value = (CTD price - theoretical basis) / CTD factor
- Calendar spread fair value = front month FV - back month FV
- Spread mispricing = OAB with opposite sign

**Positioning around CTD supply shortage:**
1. Sell non-CTD basis: benefits as CTD richens, pulling futures up, narrowing non-CTD bases toward zero
2. Buy CTD outright or buy futures vs non-deliverable bonds/swaps
3. Buy calendar spread: shorts unwilling to deliver roll positions → spread widens
- Non-CTD basis narrowing toward zero = effective supply increase (self-correcting mechanism)

**Execution:** legging in (separate cash + futures trades) vs EFP (packaged spread; less execution risk, potentially worse price)

---

## 12. Synthetic Assets and Yield Enhancement

**Construction:**
- Sell physical bond → invest proceeds in short-term instrument → go long equivalent futures
- Synthetic bond = long futures + cash at repo rate
- Hedge ratio: cash bond DV01 / option-adjusted futures DV01

**When futures are cheap (OAB < 0):**
- Synthetic outperforms physical by the amount of cheapness
- The capital loss on futures is smaller than on the actual bond (because futures were cheap relative to cash)
- Even though repo interest < coupon income, the smaller capital loss more than compensates
- Net effect: systematic yield enhancement

**Cash investment enhancement:**
- Standard: invest cash at Treasury GC repo rate (matches credit profile)
- Enhanced: invest in AAA floating-rate ABS (LIBOR+ return, low credit risk, liquid) → additional spread pickup beyond the cheapness premium
- Combining both effects (futures cheapness + cash enhancement) = the full yield enhancement engine

**Persistence:**
- 10-year futures historically the best enhancement vehicle due to chronic mortgage hedging selling pressure
- Structural flow (mortgage servicers, agencies shorting futures to hedge) keeps 10Y futures cheap
- Vol arbitrageurs = equilibrating force, slowly closing the gap
- But structural flows can maintain cheapness for extended periods → enhancement is a regime, not a blip

**Extension to credit:**
- Combine Treasury futures + high-yield term cash + credit default swaps → synthetic corporate bonds
- CDS adds credit exposure; futures add rate exposure; cash earns the spread
- Creates corporate bond return profile from derivatives

---

## 13. Contract Design and Optionality

**Reference yield determines option structure:**
- CF reference yield is the single design parameter that determines how much optionality the contract has
- At the reference yield: all bonds equally cheap to deliver → maximum switch option value
- Far from the reference yield: one bond dominates → minimal optionality → contract degrades to single-bond forward

**The 6% factor regime change (timeless lesson in contract design):**
- When the reference yield was 8% but market yields were far below, the highest-duration bond was permanently CTD → no switching → zero gamma → basis trading died ("dry spell")
- Reducing the reference yield to 6% (closer to market yields) immediately restored optionality:
  - CTD shifted to bonds with maturities centrally located in the deliverable range
  - Multiple bonds competed for CTD status → switch option value increased
  - Contract reflected a broader subset of the deliverable set (less susceptible to squeezes on a single issue)
- **Implication for any futures contract:** optionality is a design choice. The closer the reference yield to actual market yields, the richer the option structure. When yields drift far from the reference, the contract loses its option character regardless of other market conditions.

**Non-dollar contract design variations:**
- Different countries use different reference yields, notional coupons, deliverable baskets, and delivery mechanics
- Each design choice creates a different option structure:
  - Narrow deliverable basket → more susceptible to squeezes but cleaner hedging
  - Wide basket → less squeeze risk but more basis uncertainty
  - Physical delivery vs cash settlement → affects convergence mechanics
  - Single delivery date vs delivery window → affects timing option value
- Trading basis across different contract designs (cross-market basis RV) requires understanding how each contract's option structure differs

**Rise of notes over bonds:**
- 10-year note futures overtook bond futures in both volume and open interest
- Driven by: more active repo market in intermediate sector, broader deliverable set at 6% factors, mortgage hedging concentrating in the intermediate sector
- 10-year futures chronically cheap due to structural selling by mortgage hedgers → primary vehicle for yield enhancement strategies

---

## 14. Regime Taxonomy

| State | Name | Description | Key Dynamic |
|-------|------|-------------|-------------|
| S1 | Firm CTD / Simple Carry | Yields far from crossover; single bond firmly CTD; BNOC small; basis ≈ carry | Quiescent |
| S2 | Unstable CTD / Options Active | Yields near crossover; multiple contenders; BNOC large; neg convexity active | Spread dampener operating |
| S3 | Gamma Death | Spread-yield correlation saturated; CTD entrenched; BNOC → 0 | Dampener exhaustion |
| S4 | Supply Squeeze | OI > deliverable supply; BNOC negative; calendar spread dislocated | Failure-probability pricing |
| S5 | Inverted Carry / Wild Card | Negative carry; high CFs; intraday vol sufficient for wild card | Timing option dominant |
| S6 | Chronic Cheapness / Golden Age | Structural selling keeps futures below FV; OAB < 0; yield enhancement works | Flow > mean reversion |
| S7 | Single-Bond / Dry Spell | One bond firmly CTD; no realistic switch; contract = single-bond forward | All options deep OTM |

**Transitions:** S1↔S2 (crossover proximity), S2→S3 (correlation saturation), S1/S2→S4 (OI>float), Any→S5 (curve inversion + high vol), S6 (sustained structural flow), S3→S1 (exogenous correlation break)

---

## 14. Historical Episodes

**1986 9-1/4% squeeze** [illustrates: reflexivity + buffer until break]:
- Japanese institutions held most of issue, unwilling to lend in repo
- Reverse RP → 0%, then negative (paying to lend cash to obtain bond)
- Basis widened sharply as delivery failure priced in

**1991-93 death of gamma** [illustrates: dampener exhaustion]:
- Spread-yield correlation saturated at ±1
- Switch option killed; CTD permanently entrenched; basis trading died

**1985-89 golden age** [illustrates: structural flow > mean reversion]:
- Chronic cheapness from mortgage hedging + dealer short-basis
- OAB persistently < 0; reliable yield enhancement from synthetics

**2005 10yr CTD squeeze** [illustrates: buffer until break]:
- OI exceeded deliverable float; BNOC went negative; forced rolls

---

## 15. Spot DV01 vs Repo DV01 — Two Independent Exposures

**Forward price has two independent sensitivities:**
- **Spot DV01:** sensitivity of forward price to spot yield changes → amplified by financing (forward moves more than spot because financing magnifies the price change)
- **Repo DV01:** sensitivity of forward price to term repo rate changes → increase in repo rate raises forward price (reduces carry, narrowing the spread between spot and forward)

**Critical insight:** spot yields and repo rates are largely independent over short horizons
- Spot yields respond to macro/long-term expectations
- Repo rates respond to Fed funds / very short-term policy expectations
- Correlation of weekly changes: R-squared ≈ 0.02 (essentially zero)
- They move together in the "broad sweep" but are independent over hedging horizons

**Hedging implication:**
- A complete hedge must offset BOTH spot and repo DV01 separately
- Spot DV01 ≈ 50× repo DV01 → repo exposure is small but not zero
- Most hedgers ignore repo DV01 in practice (dominated by spot)
- But during repo market dislocations, the repo DV01 can produce unexpected P/L
- **Repo stub risk:** after locking in term repo, residual exposure from repo maturity to futures delivery → must decide whether to hedge this gap or accept the risk

---

## 16. OAB Pricing Discipline

**Consistency checks when pricing delivery options:**
- **Forward price consistency:** each bond's expected forward price (probability-weighted average across scenarios) must equal its actual market forward price (spot minus carry). If not, the model's yield distribution is biased.
- **Options consistency:** the model-implied price of an ATM bond futures call should match (approximately) the market price of the exchange-traded option. If it doesn't, adjust assumed yield volatility up or down until it does. This cross-checks the basis model against the listed options market.
- **Yield spread volatility:** the standard deviation of yield curve slope changes does NOT scale with sqrt(time) because yield changes at different points are positively correlated. Must estimate spread volatility directly for each horizon.
- **Term repo specials:** if the CTD is on special in term repo, the forward price must be adjusted for the lower financing rate. Ignoring specialness in forward pricing → systematic mispricing of the basis.
- **Anticipated new issues:** for 2Y and 5Y contracts, upcoming auctions will add bonds to the deliverable set whose coupons are unknown. Must estimate where they will land on the yield curve and how they will behave under different scenarios.

---

## 17. Doctrines

- "The basis is carry plus option value" — exact, exhaustive, starting point for everything
- "The CTD's BNOC is pure option value; everyone else pays option value plus an expensiveness premium"
- "Buying the basis is buying volatility; selling the basis is selling volatility"
- "Conversion factors are the source of all optionality"
- "Futures price traces the smooth curve below the minimum of converted prices"
- "The most obviously attractive short basis trade carries the greatest squeeze risk"
- "Negative net basis is not free money — it prices delivery failure"
- "The EOM option runs on BPV, not duration"
- "The four hedge ratios converge only at correlation = 1"
- "The RP/reverse RP spread is the hidden tax on every basis trade"
- "Cover the tail as close to the final bell as possible"
- "Selling the OTR basis is always negative carry"
- "Calendar spread mispricing = OAB with opposite sign"
- "Systematic yield spread behavior is a dampener on the switch option — it moves the strike"
- "BNOC rankings can diverge from IRR rankings because BNOC ignores price levels"
- "When two markets disagree on vol, buy cheap and sell rich — but horizon mismatch leaves residual risk"
