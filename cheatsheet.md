```
╔══════════════════════════════════════════════════════════════════════════════╗
║                    ECO 4000 MIDTERM CHEAT SHEET                            ║
║              COMPLETE DECISION TREE + FORMULA SYSTEM                       ║
║                       Chapters 2, 3, 4                                     ║
╚══════════════════════════════════════════════════════════════════════════════╝


═══════════════════════════════════════════════════════════════════════════════
STEP 0: READ THE QUESTION -- WHICH DOMAIN?
═══════════════════════════════════════════════════════════════════════════════

  ┌─────────────────────────────────────────────────────────────────────┐
  │  What words/symbols appear in the question?                        │
  └────────────────────────┬────────────────────────────────────────────┘
                           │
           ┌───────────────┼───────────────────┐
           │               │                   │
           ▼               ▼                   ▼
  ┌────────────────┐ ┌──────────────┐  ┌──────────────────┐
  │  PROBABILITY   │ │  STATISTICS  │  │  REGRESSION      │
  │  (Chapter 2)   │ │  (Chapter 3) │  │  (Chapter 4)     │
  ├────────────────┤ ├──────────────┤  ├──────────────────┤
  │ P(X=x), E(X), │ │ Y-bar, n, s, │  │ Yi=b0+b1*Xi+ui,  │
  │ Var(X), SD(X), │ │ SE, H0, H1,  │  │ OLS, slope,      │
  │ Cov, Corr,     │ │ t-stat,      │  │ intercept, R^2,  │
  │ N(mu,sigma^2), │ │ p-value, CI, │  │ SER, SSR, TSS,   │
  │ joint P(X,Y),  │ │ alpha, reject│  │ residual, b0, b1 │
  │ conditional,   │ │ fail to rej, │  │ predicted value,  │
  │ Bernoulli,     │ │ sig. level,  │  │ SE(b1), omitted  │
  │ skewness,      │ │ unbiased,    │  │ variable, causal │
  │ kurtosis,      │ │ efficient,   │  │                  │
  │ portfolio      │ │ consistent   │  │                  │
  └───────┬────────┘ └──────┬───────┘  └────────┬─────────┘
          │                 │                    │
          ▼                 ▼                    ▼
      GO TO A           GO TO B             GO TO C



═══════════════════════════════════════════════════════════════════════════════
A. PROBABILITY (Chapter 2)
═══════════════════════════════════════════════════════════════════════════════

  ┌─────────────────────────────────────────────────────────────────────┐
  │  What is the question asking about?                                │
  └────────────────────────┬────────────────────────────────────────────┘
                           │
     ┌──────────┬──────────┼──────────┬──────────┬──────────┐
     │          │          │          │          │          │
     ▼          ▼          ▼          ▼          ▼          ▼
   [A1]       [A2]       [A3]       [A4]       [A5]       [A6]
  Single    Linear     Joint/     Cov/Corr   Normal     Shape
   RV      Transform  Cond/Indep            Distrib   Skew/Kurt


───────────────────────────────────────────────────────────────────────────────
A1. SINGLE RANDOM VARIABLE
───────────────────────────────────────────────────────────────────────────────

  Is it a Bernoulli RV? (only outcomes 0 and 1, parameter p)
  ┌──────────┬──────────────┐
  │  YES     │     NO       │
  ▼          ▼              │
 BERNOULLI  GENERAL         │
 SHORTCUT   DISCRETE        │
                            │
                            │
  BERNOULLI (2 outcomes: 0 and 1, probability p)                
  ┌─────────────────────────────────────────────────────────┐
  │  E(R) = p                                               │
  │  Var(R) = p(1 - p)                                      │
  │  SD(R) = sqrt(p(1-p))                                   │
  └─────────────────────────────────────────────────────────┘

  GENERAL DISCRETE (k outcomes x1,...,xk with probs p1,...,pk)
  ┌─────────────────────────────────────────────────────────┐
  │  VALIDITY CHECK:                                        │
  │    - Each pi in [0, 1]                                  │
  │    - Sum of all pi = 1    ← if not, INVALID distrib     │
  │                                                         │
  │  E(X) = SUM[ xi * pi ]                                 │
  │       = x1*p1 + x2*p2 + ... + xk*pk                    │
  │                                                         │
  │  Var(X) = SUM[ (xi - E(X))^2 * pi ]                    │
  │         = (x1-mu)^2*p1 + (x2-mu)^2*p2 + ...            │
  │                                                         │
  │  SD(X) = sqrt(Var(X))                                   │
  │                                                         │
  │  *** KEY IDENTITY (rearranges to find E(X^2)):          │
  │  Var(X) = E(X^2) - [E(X)]^2                            │
  │  therefore:                                             │
  │  E(X^2) = Var(X) + [E(X)]^2                            │
  │                                                         │
  │  CDF: F(x) = P(X <= x)                                 │
  │  P(a < X <= b) = F(b) - F(a)                           │
  └─────────────────────────────────────────────────────────┘

  GIVEN/FIND NAVIGATION for A1:
  ┌──────────────────────────┬──────────────────────────────┐
  │  GIVEN                   │  FIND                  HOW   │
  ├──────────────────────────┼──────────────────────────────┤
  │  distribution table      │  E(X)        sum xi*pi      │
  │  distribution table      │  Var(X)      sum (xi-mu)^2  │
  │  distribution table      │  SD(X)       sqrt(Var)      │
  │  E(X) and Var(X)         │  E(X^2)      Var + mu^2     │
  │  E(X) and E(X^2)         │  Var(X)      E(X^2) - mu^2  │
  │  p (Bernoulli)           │  E(R)        = p            │
  │  p (Bernoulli)           │  Var(R)      = p(1-p)       │
  │  F(a) and F(b)           │  P(a<X<=b)   F(b) - F(a)   │
  └──────────────────────────┴──────────────────────────────┘


───────────────────────────────────────────────────────────────────────────────
A2. LINEAR TRANSFORMATION  Y = a + b*X
───────────────────────────────────────────────────────────────────────────────

  ┌─────────────────────────────────────────────────────────┐
  │  E(Y)   = a + b * E(X)                                 │
  │  Var(Y) = b^2 * Var(X)       ← "a" disappears!         │
  │  SD(Y)  = |b| * SD(X)                                  │
  └─────────────────────────────────────────────────────────┘

  TRAPS:
  - The constant "a" shifts the mean but does NOT change variance
  - Var uses b SQUARED, not b
  - If b is negative, Var still uses b^2 (positive)

  GIVEN/FIND:
  ┌──────────────────────────┬──────────────────────────────┐
  │  GIVEN                   │  FIND                        │
  ├──────────────────────────┼──────────────────────────────┤
  │  E(X), a, b              │  E(Y) = a + b*E(X)          │
  │  Var(X), b               │  Var(Y) = b^2 * Var(X)      │
  │  E(X), Var(X), a, b      │  E(Y^2) = Var(Y)+[E(Y)]^2  │
  └──────────────────────────┴──────────────────────────────┘


───────────────────────────────────────────────────────────────────────────────
A3. JOINT / MARGINAL / CONDITIONAL / INDEPENDENCE (Two RVs)
───────────────────────────────────────────────────────────────────────────────

  You will see a 2x2 (or larger) table of joint probabilities:

              X=0      X=1
      Y=0   P(0,0)   P(1,0)
      Y=1   P(0,1)   P(1,1)

  ┌─────────────────────────────────────────────────────────┐
  │  MARGINAL = sum across a row or column                  │
  │    P(X=x) = SUM over all y of P(X=x, Y=y)              │
  │    P(Y=y) = SUM over all x of P(X=x, Y=y)              │
  │                                                         │
  │  CONDITIONAL = joint / marginal of the "given" variable │
  │    P(Y=y | X=x) = P(X=x, Y=y) / P(X=x)                │
  │    P(X=x | Y=y) = P(X=x, Y=y) / P(Y=y)                │
  │    *** denominator is marginal of the GIVEN variable    │
  │                                                         │
  │  INDEPENDENCE TEST (check ANY one):                     │
  │    P(Y=y | X=x) = P(Y=y)  for all x,y?                 │
  │        OR                                               │
  │    P(X=x, Y=y) = P(X=x) * P(Y=y)  for all x,y?        │
  │    If YES: independent.  If ANY pair fails: NOT indep.  │
  └─────────────────────────────────────────────────────────┘

  CONDITIONAL EXPECTATION:
  E(Y | X=x) = SUM[ yj * P(Y=yj | X=x) ]

  RECIPE for any joint distribution question:
  1. Write the table
  2. Sum rows → marginals of Y; sum cols → marginals of X
  3. For conditional: divide joint cell by the marginal of GIVEN
  4. For independence: compare conditional to marginal


───────────────────────────────────────────────────────────────────────────────
A4. COVARIANCE / CORRELATION + SUMS OF RVs / PORTFOLIO
───────────────────────────────────────────────────────────────────────────────

  ┌─────────────────────────────────────────────────────────┐
  │  Cov(X,Y) = E[(X-muX)(Y-muY)]                          │
  │  Corr(X,Y) = Cov(X,Y) / (SD(X) * SD(Y))               │
  │                                                         │
  │  PROPERTIES:                                            │
  │    Corr in [-1, +1]  always                             │
  │    Corr(X,Y) = Corr(Y,X)                               │
  │    |Corr| = 1 → perfect LINEAR relationship             │
  │    Corr > 0 → X,Y move same direction                   │
  │    Corr < 0 → X,Y move opposite direction               │
  │    Corr = 0 → no LINEAR relationship (maybe nonlinear!) │
  │    Independent → Cov = 0 (true)                         │
  │    Cov = 0 → Independent (FALSE! only linear gone)      │
  └─────────────────────────────────────────────────────────┘

  GIVEN/FIND NAVIGATION:
  ┌──────────────────────────────┬──────────────────────────────────────┐
  │  GIVEN                       │  FIND                         HOW   │
  ├──────────────────────────────┼──────────────────────────────────────┤
  │  Corr, SD(X), SD(Y)         │  Cov = Corr * SD(X) * SD(Y)        │
  │  Cov, SD(X), SD(Y)          │  Corr = Cov / (SD(X)*SD(Y))        │
  │  joint distrib table        │  Cov = sum (xi-muX)(yj-muY)*P(i,j) │
  └──────────────────────────────┴──────────────────────────────────────┘

  *** GENERAL SUM: Z = a + b*X + c*Y ***
  ┌─────────────────────────────────────────────────────────┐
  │  E(Z) = a + b*E(X) + c*E(Y)                            │
  │                                                         │
  │  Var(Z) = b^2*Var(X) + c^2*Var(Y) + 2*b*c*Cov(X,Y)    │
  │                                                         │
  │  If INDEPENDENT: Cov(X,Y) = 0, so                      │
  │  Var(Z) = b^2*Var(X) + c^2*Var(Y)                      │
  └─────────────────────────────────────────────────────────┘

  *** PORTFOLIO: Rp = w*R1 + (1-w)*R2 ***
  ┌─────────────────────────────────────────────────────────┐
  │  E(Rp)  = w*E(R1) + (1-w)*E(R2)                        │
  │                                                         │
  │  Var(Rp) = w^2*Var(R1) + (1-w)^2*Var(R2)               │
  │            + 2*w*(1-w)*rho*SD(R1)*SD(R2)                │
  │                                                         │
  │  NOTE: Var = SD^2.  If given SD, square it first!       │
  │  NOTE: If rho=0 (uncorrelated), last term vanishes.     │
  │                                                         │
  │  Min-variance weight:                                   │
  │  w* = [Var(R2) - rho*SD1*SD2]                           │
  │       / [Var(R1) + Var(R2) - 2*rho*SD1*SD2]            │
  └─────────────────────────────────────────────────────────┘

  COMMON TRAP: question gives SD, you need Var → SQUARE IT
  COMMON TRAP: "independent" or "uncorrelated" → set Cov = 0


───────────────────────────────────────────────────────────────────────────────
A5. NORMAL DISTRIBUTION
───────────────────────────────────────────────────────────────────────────────

  *** CRITICAL: N(mu, sigma^2) -- second param is VARIANCE ***
  ***           SD = sqrt(variance)                         ***

  STANDARDIZATION (must do this before using Z-table):
  ┌─────────────────────────────────────────────────────────┐
  │  Given X ~ N(mu, sigma^2):                              │
  │                                                         │
  │    Z = (X - mu) / sigma     ← divide by SD not Var!    │
  │                                                         │
  │  Then Z ~ N(0,1) and use the Z-table.                   │
  └─────────────────────────────────────────────────────────┘

  THE Z-TABLE gives: Phi(z) = P(Z <= z)

  PROBABILITY RECIPES:
  ┌─────────────────────────────────────────────────────────────────────┐
  │                                                                     │
  │  TYPE               RECIPE                                          │
  │  ─────────────────  ──────────────────────────────────────────────  │
  │  P(X < c)           Step 1: z = (c - mu)/sigma                     │
  │                     Step 2: look up Phi(z) in table                │
  │                     Answer: Phi(z)                                 │
  │                                                                     │
  │  P(X > c)           Step 1: z = (c - mu)/sigma                     │
  │                     Step 2: look up Phi(z) in table                │
  │                     Answer: 1 - Phi(z)                             │
  │                                                                     │
  │  P(a < X < b)       Step 1: z1 = (a-mu)/sigma, z2 = (b-mu)/sigma  │
  │                     Step 2: look up Phi(z1) and Phi(z2)            │
  │                     Answer: Phi(z2) - Phi(z1)                      │
  │                                                                     │
  │  SYMMETRY TRICKS:                                                   │
  │    P(Z > z) = P(Z < -z)          [mirror image]                    │
  │    P(Z > 0) = P(Z < 0) = 0.50   [half/half at center]             │
  │    P(-z < Z < z) = 2*Phi(z) - 1  [symmetric interval]             │
  │                                                                     │
  │  COMMON Z-VALUES (memorize):                                        │
  │    Phi(1)    = 0.8413     P(|Z|<1) = 0.6827                        │
  │    Phi(1.64) = 0.9495     P(|Z|<1.64) ~ 0.90                       │
  │    Phi(1.96) = 0.9750     P(|Z|<1.96) ~ 0.95                       │
  │    Phi(2)    = 0.9772                                               │
  │    Phi(2.58) = 0.9951     P(|Z|<2.58) ~ 0.99                       │
  │                                                                     │
  └─────────────────────────────────────────────────────────────────────┘

  t-DISTRIBUTION:
  ┌─────────────────────────────────────────────────────────┐
  │  - Heavier/fatter tails than normal                     │
  │  - Parameterized by degrees of freedom (df)             │
  │  - df > 120  ≈  standard normal                         │
  │  - Use t-table when n is SMALL (n < ~30)                │
  │  - Use Z-table when n is LARGE                          │
  └─────────────────────────────────────────────────────────┘


───────────────────────────────────────────────────────────────────────────────
A6. SHAPE: SKEWNESS AND KURTOSIS (conceptual)
───────────────────────────────────────────────────────────────────────────────

  ┌─────────────────────────────────────────────────────────┐
  │  Skewness = E[(X-mu)^3] / sigma^3                       │
  │    = 0  : symmetric                                     │
  │    < 0  : long LEFT tail  (left-skewed)                 │
  │    > 0  : long RIGHT tail (right-skewed)                │
  │                                                         │
  │  Kurtosis = E[(X-mu)^4] / sigma^4                       │
  │    Always >= 0                                          │
  │    Higher value = heavier tails = more extreme events   │
  │    Normal distribution kurtosis = 3                     │
  └─────────────────────────────────────────────────────────┘



═══════════════════════════════════════════════════════════════════════════════
B. STATISTICS (Chapter 3)
═══════════════════════════════════════════════════════════════════════════════

  ┌─────────────────────────────────────────────────────────────────────┐
  │  What is the question asking?                                      │
  └────────────────────────┬────────────────────────────────────────────┘
                           │
        ┌──────────────────┼──────────────┬─────────────────┐
        │                  │              │                 │
        ▼                  ▼              ▼                 ▼
      [B1]               [B2]          [B3]              [B4]
    Conceptual        Compute SE    Hypothesis        Confidence
    (unbiased,        or stats      Testing           Interval
     efficient,       from sample   (t-stat,
     consistent,                    p-value,
     CLT, etc.)                     reject?)


───────────────────────────────────────────────────────────────────────────────
B1. CONCEPTUAL DEFINITIONS (pick the right answer)
───────────────────────────────────────────────────────────────────────────────

  ┌─────────────────────────────────────────────────────────────────────┐
  │  TERM             DEFINITION                                        │
  │  ──────────────── ────────────────────────────────────────────────  │
  │  Unbiased         E(estimator) = true parameter                    │
  │                   Y-bar is unbiased for mu: E(Y-bar) = mu          │
  │                                                                     │
  │  Consistent       Estimator converges to parameter as n → inf       │
  │                                                                     │
  │  Efficient        Among unbiased estimators, has smallest variance  │
  │                   Y-bar beats Y1 because Var(Y-bar)=s^2/n < s^2   │
  │                                                                     │
  │  CLT              For large n, Y-bar ~ N(mu, sigma^2/n)            │
  │                   regardless of population distribution             │
  │                                                                     │
  │  Sampling distrib Y-bar ~ N(mu, sigma^2/n)                         │
  │  of Y-bar         E(Y-bar) = mu,  Var(Y-bar) = sigma^2/n          │
  │                                                                     │
  │  Y1 vs Y-bar      Both unbiased. Y1 has Var = sigma^2.            │
  │                   Y-bar has Var = sigma^2/n. Y-bar wins.           │
  │                                                                     │
  │  n-1 in s^2       Corrects bias from estimating mu with Y-bar     │
  │                   s^2 = SUM(Yi-Ybar)^2 / (n-1)                    │
  │                                                                     │
  │  Least Squares    Y-bar = value m minimizing SUM(Yi - m)^2         │
  │                                                                     │
  │  Significance     P(reject H0 | H0 is true) = Type I error rate    │
  │  level alpha      NOT "probability H0 is true"                     │
  │                                                                     │
  │  Fail to reject   Does NOT prove H0 true                           │
  │                   "Not enough evidence to reject"                   │
  │                                                                     │
  │  95% CI meaning   In repeated sampling, 95% of intervals contain   │
  │                   the true mu. NOT "95% chance mu is in here"       │
  │                                                                     │
  │  When t-table?    Small n (n < ~30). Large n → use Z-table.        │
  └─────────────────────────────────────────────────────────────────────┘


───────────────────────────────────────────────────────────────────────────────
B2. COMPUTE STANDARD ERROR / SAMPLE STATS
───────────────────────────────────────────────────────────────────────────────

  ┌─────────────────────────────────────────────────────────┐
  │  GIVEN: n, s (sample std dev)                           │
  │                                                         │
  │  SE(Y-bar) = s / sqrt(n)                                │
  │                                                         │
  │  If n doubles (e.g. 25 → 100): sqrt goes 5 → 10        │
  │  SE is halved (not quartered, not doubled)              │
  │                                                         │
  │  Sample variance: s^2 = SUM(Yi-Ybar)^2 / (n-1)         │
  │  Sample covariance: sXY = SUM(Xi-Xbar)(Yi-Ybar)/(n-1)  │
  │  Sample correlation: rXY = sXY / (sX * sY)             │
  └─────────────────────────────────────────────────────────┘


───────────────────────────────────────────────────────────────────────────────
B3. HYPOTHESIS TESTING -- THE MASTER WORKFLOW
───────────────────────────────────────────────────────────────────────────────

  This is the most common computation block. ALWAYS these steps:

  ┌─────────────────────────────────────────────────────────────────────┐
  │                                                                     │
  │  ┌──────────────────────────────────────────────────────────────┐   │
  │  │ STEP 1: IDENTIFY what is being tested                       │   │
  │  │                                                              │   │
  │  │  Single mean?                                                │   │
  │  │    Given: Y-bar, s, n, mu_0                                  │   │
  │  │    SE = s / sqrt(n)                                          │   │
  │  │    t = (Y-bar - mu_0) / SE                                   │   │
  │  │                                                              │   │
  │  │  Difference in means?                                        │   │
  │  │    Given: Y-bar1, Y-bar2, s1, s2, n1, n2, d_0 (usually 0)  │   │
  │  │    SE = sqrt(s1^2/n1 + s2^2/n2)                              │   │
  │  │    t = (Y-bar1 - Y-bar2 - d_0) / SE                         │   │
  │  │                                                              │   │
  │  │  Regression coefficient?                                     │   │
  │  │    Given: b1, SE(b1), hypothesized value (usually 0)        │   │
  │  │    t = (b1 - 0) / SE(b1) = b1 / SE(b1)                     │   │
  │  └──────────────────────────────────────────────────────────────┘   │
  │                          │                                          │
  │                          ▼                                          │
  │  ┌──────────────────────────────────────────────────────────────┐   │
  │  │ STEP 2: DETERMINE the type of test                          │   │
  │  │                                                              │   │
  │  │  Look at H1 (the alternative hypothesis):                   │   │
  │  │                                                              │   │
  │  │  H1: mu ≠ mu_0  →  TWO-SIDED                                │   │
  │  │  H1: mu > mu_0  →  ONE-SIDED (right)                        │   │
  │  │  H1: mu < mu_0  →  ONE-SIDED (left)                         │   │
  │  └──────────────────────────────────────────────────────────────┘   │
  │                          │                                          │
  │                          ▼                                          │
  │  ┌──────────────────────────────────────────────────────────────┐   │
  │  │ STEP 3: COMPUTE p-value                                     │   │
  │  │                                                              │   │
  │  │  TWO-SIDED:                                                  │   │
  │  │    p-value = 2 * P(Z > |t|)                                  │   │
  │  │            = 2 * [1 - Phi(|t|)]                              │   │
  │  │    (look up |t| in Z-table, get Phi, subtract from 1, x2)   │   │
  │  │                                                              │   │
  │  │  ONE-SIDED (H1: mu > mu_0):                                  │   │
  │  │    p-value = P(Z > t) = 1 - Phi(t)                           │   │
  │  │                                                              │   │
  │  │  ONE-SIDED (H1: mu < mu_0):                                  │   │
  │  │    p-value = P(Z < t) = Phi(t)                                │   │
  │  │                                                              │   │
  │  └──────────────────────────────────────────────────────────────┘   │
  │                          │                                          │
  │                          ▼                                          │
  │  ┌──────────────────────────────────────────────────────────────┐   │
  │  │ STEP 4: COMPARE p-value to significance level alpha          │   │
  │  │                                                              │   │
  │  │    p-value <= alpha  →  REJECT H0                            │   │
  │  │    p-value >  alpha  →  FAIL TO REJECT H0                   │   │
  │  │                                                              │   │
  │  │  OR use critical values:                                     │   │
  │  │    Two-sided: |t| > cv  →  reject                            │   │
  │  │    One-sided (>): t > cv+  →  reject                         │   │
  │  │    One-sided (<): t < -cv  →  reject                         │   │
  │  └──────────────────────────────────────────────────────────────┘   │
  │                                                                     │
  └─────────────────────────────────────────────────────────────────────┘

  *** CRITICAL VALUES TO MEMORIZE ***
  ┌─────────────────────────────────────────────────────────┐
  │                                                         │
  │  alpha     Two-sided cv     One-sided cv                │
  │  ─────     ────────────     ────────────                │
  │   1%          2.58              2.33                    │
  │   5%          1.96              1.64                    │
  │  10%          1.64              1.28                    │
  │                                                         │
  └─────────────────────────────────────────────────────────┘

  ONE-SIDED REJECTION DIRECTION:
  ┌─────────────────────────────────────────────────────────┐
  │  H1: mu > mu_0  → reject when t is LARGE POSITIVE      │
  │  H1: mu < mu_0  → reject when t is LARGE NEGATIVE      │
  │  H1: mu ≠ mu_0  → reject when |t| is LARGE             │
  └─────────────────────────────────────────────────────────┘


───────────────────────────────────────────────────────────────────────────────
B4. CONFIDENCE INTERVALS
───────────────────────────────────────────────────────────────────────────────

  SINGLE MEAN:
  ┌─────────────────────────────────────────────────────────┐
  │  CI = Y-bar  +/-  z* * SE(Y-bar)                       │
  │                                                         │
  │  where SE = s / sqrt(n) and z* depends on level:        │
  │    90% CI:  z* = 1.64                                   │
  │    95% CI:  z* = 1.96                                   │
  │    99% CI:  z* = 2.58                                   │
  │                                                         │
  │  Result: [Y-bar - z*SE ,  Y-bar + z*SE]                 │
  └─────────────────────────────────────────────────────────┘

  DIFFERENCE IN MEANS:
  ┌─────────────────────────────────────────────────────────┐
  │  CI = (Y-bar1 - Y-bar2)  +/-  z* * SE(Y-bar1-Y-bar2)  │
  │  where SE = sqrt(s1^2/n1 + s2^2/n2)                    │
  └─────────────────────────────────────────────────────────┘

  INTERPRETATION TRAP:
    WRONG: "95% probability mu is in this interval"
    RIGHT: "In repeated sampling, 95% of such intervals contain mu"

  READING A CI:
    If CI is [45, 55], the sample mean = midpoint = (45+55)/2 = 50
    Half-width = 5 = z* * SE, so SE = 5/z*



═══════════════════════════════════════════════════════════════════════════════
C. REGRESSION (Chapter 4)
═══════════════════════════════════════════════════════════════════════════════

  ┌─────────────────────────────────────────────────────────────────────┐
  │  What is the question asking?                                      │
  └────────────────────────┬────────────────────────────────────────────┘
                           │
     ┌──────────┬──────────┼──────────┬──────────┬──────────┐
     │          │          │          │          │          │
     ▼          ▼          ▼          ▼          ▼          ▼
   [C1]       [C2]       [C3]       [C4]       [C5]       [C6]
  Interpret  Compute    Predict    Goodness   Assumptions  Test
  model      b0, b1    Y-hat or    of fit     & OVB       beta
  components from stats  Delta-Y   R^2, SER               t-stat


───────────────────────────────────────────────────────────────────────────────
C1. MODEL COMPONENTS (conceptual / interpretation)
───────────────────────────────────────────────────────────────────────────────

  MODEL:  Yi = beta_0 + beta_1 * Xi + ui

  ┌─────────────────────────────────────────────────────────────────────┐
  │  COMPONENT    WHAT IT IS               WHAT IT MEANS               │
  │  ──────────── ──────────────────────── ──────────────────────────  │
  │  Yi           dependent variable        what we want to explain    │
  │  Xi           independent var/regressor what we use to explain Y   │
  │  beta_0       intercept                 E(Y) when X = 0           │
  │  beta_1       slope                     change in E(Y) per 1-unit │
  │                                         change in X               │
  │  ui           error term                all other factors          │
  │  b0+b1*X      pop. regression function  E(Y|X)                    │
  │  u-hat_i      residual                  Yi - b0 - b1*Xi           │
  │               (uses ESTIMATED coefs)                               │
  │                                                                     │
  │  *** CAUSATION TRAP ***                                             │
  │  b1 measures ASSOCIATION (correlation), NOT causation!              │
  │  "b1 = 2.5" → "one more unit of X is ASSOCIATED with              │
  │   2.5 more units of Y on average"                                  │
  │  NEVER say "causes" unless randomized experiment                    │
  └─────────────────────────────────────────────────────────────────────┘


───────────────────────────────────────────────────────────────────────────────
C2. COMPUTING OLS ESTIMATES b0 and b1
───────────────────────────────────────────────────────────────────────────────

  ┌─────────────────────────────────────────────────────────────────────┐
  │  FORMULA 1 (most common):                                          │
  │    b1 = sXY / sX^2                                                 │
  │    b0 = Y-bar - b1 * X-bar                                         │
  │                                                                     │
  │  FORMULA 2 (if given correlation):                                  │
  │    b1 = rXY * (sY / sX)                                            │
  │    b0 = Y-bar - b1 * X-bar                                         │
  │                                                                     │
  │  *** THESE ARE EQUIVALENT because:                                  │
  │  rXY = sXY / (sX * sY)                                             │
  │  so rXY * sY/sX = sXY/(sX*sY) * sY/sX = sXY/sX^2                  │
  └─────────────────────────────────────────────────────────────────────┘

  GIVEN/FIND NAVIGATION:
  ┌────────────────────────────────────┬───────────────────────────────┐
  │  GIVEN                             │  FIND              HOW       │
  ├────────────────────────────────────┼───────────────────────────────┤
  │  sXY, sX (or sX^2)                │  b1 = sXY / sX^2             │
  │  rXY, sY, sX                      │  b1 = rXY * sY / sX          │
  │  b1, Y-bar, X-bar                 │  b0 = Ybar - b1*Xbar         │
  │  Y-bar, X-bar, sXY, sX            │  both b0 and b1              │
  │                                    │                               │
  │  *** TRAP: given sX (std dev)?     │  sX^2 = (sX)^2               │
  │  square it to get variance!        │                               │
  └────────────────────────────────────┴───────────────────────────────┘

  OLS IS DERIVED FROM: min over b0,b1 of SUM(Yi - b0 - b1*Xi)^2
  (minimizes the sum of squared residuals)


───────────────────────────────────────────────────────────────────────────────
C3. PREDICTION AND PREDICTED CHANGE
───────────────────────────────────────────────────────────────────────────────

  ┌─────────────────────────────────────────────────────────┐
  │  PREDICTED VALUE at X = x:                              │
  │    Y-hat = b0 + b1 * x                                  │
  │                                                         │
  │  PREDICTED CHANGE when X goes from x1 to x2:            │
  │    Delta Y-hat = b1 * (x2 - x1)                         │
  │    (only need b1, not b0!)                              │
  │                                                         │
  │  RESIDUAL for observation i:                            │
  │    u-hat_i = Yi - Y-hat_i = Yi - b0 - b1*Xi             │
  └─────────────────────────────────────────────────────────┘


───────────────────────────────────────────────────────────────────────────────
C4. GOODNESS OF FIT: R^2, SER, SSR, TSS
───────────────────────────────────────────────────────────────────────────────

  *** THE FIVE INTERCONNECTED QUANTITIES ***

  TSS = SUM(Yi - Y-bar)^2           total variation in Y
  SSR = SUM(Yi - Y-hat_i)^2         unexplained variation (residuals)
  R^2 = 1 - SSR/TSS                 fraction explained
  SER = sqrt(SSR / (n-2))           typical residual size, units of Y
  rXY = sample correlation coeff

  ┌─────────────────────────────────────────────────────────────────────┐
  │                                                                     │
  │  MASTER EQUATIONS (any 2 known → solve for others):                 │
  │                                                                     │
  │    R^2 = 1 - SSR/TSS                                                │
  │    SSR = TSS * (1 - R^2)                                            │
  │    TSS = SSR / (1 - R^2)                                            │
  │    SER = sqrt(SSR / (n-2))                                          │
  │    SSR = SER^2 * (n - 2)                                            │
  │    In simple regression: R^2 = rXY^2                                │
  │                                                                     │
  │  GIVEN → FIND ROUTER:                                               │
  │  ┌──────────────────────────┬──────────────────────────────────┐    │
  │  │  GIVEN                   │  FIND                      HOW  │    │
  │  ├──────────────────────────┼──────────────────────────────────┤    │
  │  │  SSR, TSS                │  R^2 = 1 - SSR/TSS              │    │
  │  │  R^2, TSS                │  SSR = TSS*(1-R^2)              │    │
  │  │  R^2, SSR                │  TSS = SSR/(1-R^2)              │    │
  │  │  SER, n                  │  SSR = SER^2 * (n-2)            │    │
  │  │  SSR, n                  │  SER = sqrt(SSR/(n-2))          │    │
  │  │  rXY                     │  R^2 = rXY^2                    │    │
  │  │  SER, n, R^2             │  TSS = SER^2*(n-2)/(1-R^2)     │    │
  │  └──────────────────────────┴──────────────────────────────────┘    │
  │                                                                     │
  │  INTERPRETATIONS:                                                   │
  │    R^2 = 0    X explains NOTHING, b1 = 0                            │
  │    R^2 = 1    perfect fit, all points on line                       │
  │    0<R^2<1    X explains some variation                             │
  │    R^2 = 0.60 means "60% of variation in Y explained by X"         │
  │    SER is in the SAME UNITS as Y (typical prediction error)        │
  │    n-2 in SER because we estimated 2 params (b0, b1)              │
  │                                                                     │
  └─────────────────────────────────────────────────────────────────────┘


───────────────────────────────────────────────────────────────────────────────
C5. OLS ASSUMPTIONS + OMITTED VARIABLE BIAS (conceptual)
───────────────────────────────────────────────────────────────────────────────

  ┌─────────────────────────────────────────────────────────────────────┐
  │  THE THREE ASSUMPTIONS:                                             │
  │                                                                     │
  │  1. E(u|X) = 0   The error has zero mean for any value of X        │
  │     → Violated when: OMITTED VARIABLE correlated with X            │
  │     → Consequence: b1 is BIASED                                    │
  │                                                                     │
  │  2. (Xi,Yi) i.i.d.   Random sample from population                 │
  │     → Violated when: sample is not representative                  │
  │                                                                     │
  │  3. No large outliers                                               │
  │     → Violated when: extreme observations distort estimates        │
  │                                                                     │
  │  If all 3 hold: b0 and b1 are UNBIASED                             │
  │  (E(b0) = beta_0, E(b1) = beta_1)                                  │
  └─────────────────────────────────────────────────────────────────────┘

  OMITTED VARIABLE BIAS DIRECTION:
  ┌─────────────────────────────────────────────────────────────────────┐
  │                                                                     │
  │  If you OMIT a variable W that is:                                  │
  │    (1) correlated with X  AND  (2) affects Y                       │
  │                                                                     │
  │  The bias on b1 goes in the direction of:                           │
  │    (effect of W on Y) * (sign of corr between W and X)             │
  │                                                                     │
  │  EXAMPLE: Test score regressed on class size, omit income           │
  │    Income → test score:     POSITIVE                                │
  │    Income ↔ class size:     NEGATIVE (rich districts have small)    │
  │    Bias direction:          (+) * (-) = NEGATIVE                    │
  │    Since true beta_1 is negative, bias makes it MORE negative       │
  │    = exaggerated / away from zero                                   │
  │                                                                     │
  └─────────────────────────────────────────────────────────────────────┘

  HOMOSKEDASTICITY:
  ┌─────────────────────────────────────────────────────────┐
  │  Var(u_i) = sigma_u^2 for ALL i (constant)             │
  │  (vs heteroskedasticity: variance changes with X)       │
  │                                                         │
  │  Under homoskedasticity:                                │
  │  Var(b1) = sigma_u^2 / (n * sigma_X^2)                 │
  │                                                         │
  │  b1 is MORE PRECISE when:                               │
  │    n is LARGER       (more data)                        │
  │    Var(X) is LARGER  (more spread in X)                 │
  │    Var(u) is SMALLER (less noise)                       │
  └─────────────────────────────────────────────────────────┘


───────────────────────────────────────────────────────────────────────────────
C6. TESTING REGRESSION COEFFICIENTS
───────────────────────────────────────────────────────────────────────────────

  ┌─────────────────────────────────────────────────────────┐
  │  GIVEN: b1, SE(b1)                                      │
  │                                                         │
  │  t = b1 / SE(b1)     (testing H0: beta_1 = 0)          │
  │                                                         │
  │  Then use the SAME hypothesis testing workflow from B3:  │
  │  → compute p-value (two-sided or one-sided)             │
  │  → compare to alpha                                     │
  │  → reject or fail to reject                             │
  │                                                         │
  │  NOTE: SE(b1) is given in parentheses below coefficient │
  │  in regression output tables                            │
  └─────────────────────────────────────────────────────────┘



═══════════════════════════════════════════════════════════════════════════════
GLOBAL DECISION TREE: "I DON'T KNOW WHAT THIS QUESTION IS ASKING"
═══════════════════════════════════════════════════════════════════════════════

  START: Read the question. What information is given?

  ┌─────────────────────────────────────────────────────────────────────┐
  │  I see a probability table with P(X=x) values                      │
  │  → A1: Compute E(X), Var(X), check validity                       │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see "Bernoulli" or only outcomes {0,1} with probability p       │
  │  → A1 Bernoulli: E=p, Var=p(1-p)                                  │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see Y = a + bX with known E(X), Var(X) and asked for E(Y)/Var  │
  │  → A2: Linear transformation rules                                │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see E(X) and Var(X) and asked for E(X^2) (or vice versa)       │
  │  → A1: E(X^2) = Var(X) + [E(X)]^2                                │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see a joint probability table P(X=x, Y=y)                      │
  │  → A3: Marginal (sum row/col), conditional (joint/marginal),      │
  │         independence (conditional = marginal?)                     │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see Corr, SD, Cov and asked to find one from others            │
  │  → A4: Cov = Corr * SD(X) * SD(Y) (rearrange as needed)          │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see Z = a + bX + cY or "portfolio" with weights                │
  │  → A4: E(Z) = a+bEX+cEY,  Var = b^2VX + c^2VY + 2bcCov          │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see N(mu, sigma^2) and asked for P(X < c) or P(X > c)          │
  │  → A5: Standardize Z=(c-mu)/SD, use Z-table                       │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see "skewness" or "kurtosis" or "shape" or "tails"             │
  │  → A6: Skewness(neg=left tail, 0=symm, pos=right tail)            │
  │         Kurtosis(higher=heavier tails)                             │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see "t-distribution" vs "normal" or "degrees of freedom"        │
  │  → A5 bottom: t has fatter tails, df→inf becomes normal,           │
  │    use t-table for small n                                         │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see n, Y-bar, s and asked for SE                                │
  │  → B2: SE = s/sqrt(n)                                             │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see "confidence interval" or "CI"                               │
  │  → B4: CI = Y-bar +/- z* * SE                                     │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see H0, H1, "test", "reject", "p-value", "significance"        │
  │  → B3: Full hypothesis testing workflow                            │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see "unbiased", "efficient", "consistent", "CLT"               │
  │  → B1: Conceptual definitions lookup                               │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see two groups with means/SDs and "compare" or "difference"     │
  │  → B3 (difference) + B4 (difference CI)                            │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see b0, b1, "slope", "intercept", "regression", "OLS"          │
  │  → C1 (interpret) or C2 (compute)                                  │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see summary stats (means, SDs, sXY, rXY) + "estimate slope"    │
  │  → C2: b1 = sXY/sX^2 or rXY*sY/sX, then b0 = Ybar-b1*Xbar       │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see "predicted" or "what score/wage/return at X = ?"            │
  │  → C3: Y-hat = b0 + b1*X, or Delta = b1*(x2-x1)                  │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see R^2, SSR, TSS, SER, n                                      │
  │  → C4: Use master equations to solve for unknowns                  │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see "assumption", "omitted variable", "bias", "E(u|X)=0"       │
  │  → C5: Three assumptions + OVB direction                           │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see "homoskedasticity" or "variance of b1"                      │
  │  → C5 bottom: Var(b1) = sigma_u^2/(n*sigma_X^2)                   │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see b1, SE(b1) and "test H0: beta_1 = 0"                       │
  │  → C6: t = b1/SE(b1), then B3 workflow                            │
  ├─────────────────────────────────────────────────────────────────────┤
  │  I see "causes" or "proves" in an answer choice                    │
  │  → Almost always WRONG. OLS = association, not causation.          │
  │    "Fail to reject" ≠ "H0 is proven true"                         │
  └─────────────────────────────────────────────────────────────────────┘



═══════════════════════════════════════════════════════════════════════════════
QUICK-REFERENCE: NUMBERS TO MEMORIZE
═══════════════════════════════════════════════════════════════════════════════

  Z-TABLE VALUES:
    Phi(-2)   = 0.0228      Phi(2)   = 0.9772
    Phi(-1)   = 0.1587      Phi(1)   = 0.8413
    Phi(-0.5) = 0.3085      Phi(0.5) = 0.6915
    Phi(0)    = 0.5000
    Phi(1.64) = 0.9495      Phi(1.96) = 0.9750
    Phi(2.33) = 0.9901      Phi(2.58) = 0.9951

  CRITICAL VALUES:
    alpha    Two-sided    One-sided
    1%         2.58         2.33
    5%         1.96         1.64
    10%        1.64         1.28

  CI MULTIPLIERS:
    90% → 1.64     95% → 1.96     99% → 2.58

  DENOMINATORS:
    Sample variance:   divide by (n-1)
    SE of Y-bar:       divide s by sqrt(n)
    SER in regression: divide SSR by (n-2), then sqrt

  DIVISION RULES:
    /(n-1)  because estimating 1 parameter (mu with Y-bar)
    /(n-2)  because estimating 2 parameters (b0 and b1)
```
