


# Probability & Statistics — Complete Formula Reference with Worked Examples
 
---
 
## 1. Counting
 
### 1.1 Permutations
**ⁿPᵣ = n! / (n − r)!**
- n = total distinct items, r = items chosen & arranged, order **matters**
**Example (1.1):** A password uses 4 different letters chosen from the 26-letter alphabet, and the order of letters matters (e.g., "ABCD" ≠ "DCBA"). How many such passwords exist?
Step 1 — Identify n=26, r=4, and that order matters → permutation.
Step 2 — ²⁶P₄ = 26!/(26−4)! = 26×25×24×23 = 358,800.
**Answer: 358,800 possible passwords.**
 
### 1.2 Combinations
**ⁿCᵣ = n! / [r!(n − r)!]**
- Same symbols, but order does **not** matter
**Example (1.2):** From a class of 15 students, a teacher must choose 4 students to form an unranked study group (no roles assigned). How many different groups are possible?
Step 1 — n=15, r=4, order doesn't matter (a group is a group regardless of who's "listed first") → combination.
Step 2 — ¹⁵C₄ = 15!/(4!·11!) = (15×14×13×12)/(4×3×2×1) = 32,760/24 = 1,365.
**Answer: 1,365 possible groups.**
 
### Integrated Problem (Section 1)
**Problem:** A company has 12 qualified engineers. Management must (a) choose a 5-person project team, then (b) from within that team, assign three distinct roles — Team Lead, Deputy Lead, Reporting Officer — to three different people. How many total ways can (a) and (b) be done together?
 
**Step 1 (combination — choosing the team, order irrelevant):**
¹²C₅ = 12!/(5!·7!) = 95,040/120 = **792** ways to pick the team.
 
**Step 2 (permutation — assigning 3 distinct roles from the 5 chosen, order matters):**
⁵P₃ = 5!/(5−3)! = 120/2 = **60** ways to assign roles.
 
**Step 3 (multiplication principle):**
Total = 792 × 60 = **47,520** total ways.
 
This shows the two formulas working in sequence: combination to form an unordered pool, permutation to assign distinct labeled positions within it.
 
---
 
## 2. Probability
 
### Formulas
- **2.1 Axioms:** P(E)≥0; P(S)=1; if mutually exclusive, P(A₁∪A₂∪…)=ΣP(Aᵢ)
- **2.2 Sample Space (S):** set of all possible outcomes
- **2.3 Event (E):** any subset of S
- **2.4 Independent Events:** P(A∩B) = P(A)·P(B)
- **2.5 Mutually Exclusive Events:** P(A∪B) = P(A) + P(B), since A∩B=∅
- **2.6 Marginal Probability:** P(A) = Σⱼ P(A∩Bⱼ)
- **2.7 Conditional Probability:** P(A|B) = P(A∩B)/P(B)
- **2.8 Joint Probability:** P(A∩B)
- **2.9 Bayes' Theorem:** P(A|B) = [P(B|A)·P(A)] / P(B)
**Example (2.1–2.3, Axioms/Sample Space/Events):** Roll a fair die. S = {1,2,3,4,5,6}. Let E = "roll an even number" = {2,4,6}.
Step 1 — Each outcome has probability 1/6 ≥ 0 (Axiom 1 satisfied).
Step 2 — P(S) = 6×(1/6) = 1 (Axiom 2 satisfied).
Step 3 — P(E) = 3×(1/6) = 1/2. **Answer: P(E) = 0.5**, and this event is a valid subset of the sample space obeying all three axioms.
 
**Example (2.4, Independent Events):** A fair coin is tossed and a fair die is rolled at the same time. Find P(coin shows Heads AND die shows 5).
Step 1 — These two experiments don't affect each other → independent. P(Heads)=1/2, P(die=5)=1/6.
Step 2 — P(A∩B) = P(A)·P(B) = (1/2)(1/6) = **1/12 ≈ 0.0833**.
 
**Example (2.5, Mutually Exclusive Events):** A card is drawn from a standard 52-card deck. Find P(card is a King OR a Queen).
Step 1 — A card can't be both a King and a Queen at once → mutually exclusive. P(King)=4/52, P(Queen)=4/52.
Step 2 — P(A∪B) = P(A)+P(B) = 4/52 + 4/52 = 8/52 = **2/13 ≈ 0.1538**.
 
**Example (2.6–2.8, Marginal & Joint Probability):** In a survey of 200 people, 120 own a car (C), 80 own a bike (Bk), and 50 own both. Find the marginal probability P(C) and the joint probability P(C∩Bk).
Step 1 — Marginal: P(C) = 120/200 = **0.60**.
Step 2 — Joint: P(C∩Bk) = 50/200 = **0.25**.
These are two different quantities: marginal ignores the other variable entirely; joint requires both to occur together.
 
### Integrated Problem (Section 2 — Bayes' Theorem)
**Problem:** A factory uses two machines. Machine A makes 60% of bolts, Machine B makes 40%. 5% of Machine A's bolts are defective; 8% of Machine B's are defective. A random bolt is defective — what's the probability it came from Machine B?
 
**Step 1 — Define events:** A = "from Machine A", B = "from Machine B" (mutually exclusive, exhaustive → partition S). D = "defective."
 
**Step 2 — Given (marginal & conditional):** P(A)=0.60, P(B)=0.40, P(D|A)=0.05, P(D|B)=0.08.
 
**Step 3 — Joint probabilities:** P(D∩A) = 0.05×0.60 = 0.030. P(D∩B) = 0.08×0.40 = 0.032.
 
**Step 4 — Marginal P(D) via law of total probability (uses Axiom 3, mutually exclusive parts):**
P(D) = 0.030 + 0.032 = **0.062**
 
**Step 5 — Bayes' Theorem:**
P(B|D) = P(D|B)P(B)/P(D) = 0.032/0.062 ≈ **0.516**
 
**Interpretation:** Although Machine B makes fewer bolts, ~51.6% of *defective* bolts come from it — because its defect rate is higher. This threads together marginal, joint, conditional, and Bayes' formulas in one flow.
 
---
 
## 3. Expectation and Measures of Dispersion
 
### Formulas
- **3.3 Mean:** μ = E[X] = Σxᵢp(xᵢ); sample x̄ = Σxᵢ/n
- **3.4 Median:** middle value of ordered data
- **3.5 Mode:** most frequent value
- **3.6 Standard Deviation:** σ = √[Σ(xᵢ−μ)²p(xᵢ)]
- **3.1 Conditional Expectation:** E[X|Y=y] = Σₓ x·P(X=x|Y=y)
- **3.2 Conditional Variance:** Var(X|Y=y) = E[X²|Y=y] − (E[X|Y=y])²
- **3.8 Covariance:** Cov(X,Y) = E[XY] − E[X]E[Y]
- **3.7 Correlation:** ρ = Cov(X,Y)/(σₓσᵧ)
**Example (3.4–3.5, Median & Mode):** A shop records daily sales (₹'000) over 9 days: 12, 15, 12, 18, 20, 12, 16, 15, 22.
Step 1 — Order the data: 12,12,12,15,15,16,18,20,22 (n=9).
Step 2 — **Median** = middle (5th) value = **15** (since n is odd, median is the single middle term after sorting).
Step 3 — **Mode** = most frequent value = **12** (appears 3 times, more than any other value).
This shows median and mode can differ from each other and from the mean — mean here = (12+12+12+15+15+16+18+20+22)/9 = 142/9 ≈ 15.78, distinct from both median (15) and mode (12).
 
### Integrated Problem (Section 3 — Joint Table: Mean, Variance, Covariance, Correlation, Conditional Expectation & Variance)
**Problem:** An ice cream shop's joint probabilities of Weather (X: Sunny=1, Rainy=0) and Sales (Y: High=10, Low=4):
 
| | Y=High(10) | Y=Low(4) |
|---|---|---|
| X=Sunny(1) | 0.35 | 0.15 |
| X=Rainy(0) | 0.10 | 0.40 |
 
Find E[X], E[Y], Cov(X,Y), ρ, E[Y|X=1], and Var(Y|X=1).
 
**Step 1 — Marginals:** P(X=1)=0.50, P(X=0)=0.50; P(Y=10)=0.45, P(Y=4)=0.55.
 
**Step 2 — Means:** E[X] = (1)(0.5)+(0)(0.5) = **0.50**. E[Y] = (10)(0.45)+(4)(0.55) = **6.70**.
 
**Step 3 — E[XY]:** = (10)(0.35)+(4)(0.15)+0+0 = 3.5+0.6 = **4.10**.
 
**Step 4 — Covariance:** Cov(X,Y) = 4.10 − (0.50)(6.70) = **0.75** (positive → sunny days go with higher sales).
 
**Step 5 — Std devs:** Var(X)=0.5−0.25=0.25→σₓ=0.5. Var(Y)=E[Y²]−E[Y]²; E[Y²]=(100)(0.45)+(16)(0.55)=53.8; Var(Y)=53.8−44.89=8.91→σᵧ≈2.985.
 
**Step 6 — Correlation:** ρ = 0.75/(0.5×2.985) ≈ **0.503** (moderate positive correlation).
 
**Step 7 — Conditional distribution given X=1:** P(Y=10|X=1)=0.35/0.50=0.70; P(Y=4|X=1)=0.15/0.50=0.30.
**Conditional Expectation:** E[Y|X=1] = (10)(0.70)+(4)(0.30) = **8.20**.
 
**Step 8 — Conditional Variance:** E[Y²|X=1] = (100)(0.70)+(16)(0.30) = 70+4.8 = 74.8.
Var(Y|X=1) = E[Y²|X=1] − (E[Y|X=1])² = 74.8 − (8.2)² = 74.8 − 67.24 = **7.56**, so SD(Y|X=1) ≈ 2.75.
 
**Interpretation:** Sunny days raise expected sales from 6.70 (overall) to 8.20 (conditional), and the conditional variance (7.56) shows the spread of sales *specifically on sunny days*, distinct from the unconditional variance (8.91) — demonstrating why conditioning changes both the center and spread of a distribution.
 
---
 
## 4. Random Variables
 
### Formulas
- **4.1 Random Variable:** function mapping outcomes in S to real numbers
- **4.2 Discrete RV:** takes countable values
- **4.3 PMF:** P(X=x)=p(x), p(x)≥0, Σₓp(x)=1
### Integrated Problem (Section 4)
**Problem:** Two fair dice are rolled. Let X = sum of the two dice. (a) Build the PMF. (b) Verify it. (c) Find P(X≥9).
 
**Step 1 — Sample space:** 36 equally likely ordered pairs, each probability 1/36.
 
**Step 2 — PMF table (counting favorable pairs per sum):**
 
| X | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 | 11 | 12 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| p(x) | 1/36 | 2/36 | 3/36 | 4/36 | 5/36 | 6/36 | 5/36 | 4/36 | 3/36 | 2/36 | 1/36 |
 
**Step 3 — Verify:** Σp(x) = 36/36 = **1 ✓**
 
**Step 4 — P(X≥9):** = 4/36+3/36+2/36+1/36 = 10/36 = **5/18 ≈ 0.278**
 
**Interpretation:** ~27.8% chance the sum is 9 or more — built directly from raw counting up through the normalized PMF.
 
---
 
## 5. Discrete Probability Distributions
 
### Formulas
- **5.1 Discrete Uniform:** P(X=x)=1/n; Mean=(a+b)/2; Variance=(n²−1)/12
- **5.2 Bernoulli:** P(X=x)=pˣ(1−p)^(1−x), x∈{0,1}; Mean=p; Variance=p(1−p)
- **5.3 Binomial:** P(X=k)=ⁿCₖpᵏ(1−p)ⁿ⁻ᵏ; Mean=np; Variance=np(1−p)
**Example (5.1, Discrete Uniform):** A fair 6-sided die is rolled once. Find P(X=4), the mean, and the variance of X.
Step 1 — All 6 outcomes equally likely → discrete uniform with n=6, values 1 to 6. P(X=4) = 1/6 ≈ **0.1667**.
Step 2 — Mean = (a+b)/2 = (1+6)/2 = **3.5**.
Step 3 — Variance = (n²−1)/12 = (36−1)/12 = 35/12 ≈ **2.917**.
This shows all outcomes carry equal probability, so mean is just the midpoint of the range.
 
**Example (5.2, Bernoulli):** A single free-throw attempt succeeds with probability p=0.7. Let X=1 if made, X=0 if missed. Find P(X=1), P(X=0), mean and variance.
Step 1 — P(X=1) = p = **0.7**; P(X=0) = 1−p = **0.3** (directly from the Bernoulli PMF with x=1 and x=0).
Step 2 — Mean = p = **0.7**. Variance = p(1−p) = 0.7×0.3 = **0.21**.
A Bernoulli variable is just a single binomial trial (n=1) — this sets up the binomial formula used next.
 
### Integrated Problem (Section 5 — Binomial)
**Problem:** A drug has a 75% success rate (p=0.75). Given to 8 independent patients: (a) P(exactly 6 respond)? (b) P(at least 6 respond)? (c) Mean & SD of successes.
 
**Step 1 — Confirm binomial conditions:** n=8 fixed trials, independent, two outcomes, constant p=0.75 (q=0.25).
 
**Step 2 (a):** P(X=6) = ⁸C₆(0.75)⁶(0.25)² = 28×0.177979×0.0625 ≈ **0.3115**
 
**Step 3 (b):** P(X=7)=⁸C₇(0.75)⁷(0.25)¹≈0.26697; P(X=8)=⁸C₈(0.75)⁸≈0.10011.
P(X≥6) = 0.3115+0.26697+0.10011 ≈ **0.6786**
 
**Step 4 (c):** Mean = np = 8×0.75 = **6**. Variance = np(1−p) = 8×0.75×0.25 = 1.5 → SD ≈ **1.225**
 
**Interpretation:** Expected successes = 6, but exact-6 probability is only ~31%, while "6 or more" happens ~68% of the time — the binomial mean tells you the center, not the certainty.
 
---
 
## 6. Continuous Random Variables
 
### Formulas
- **6.1 Continuous RV:** takes any value in an interval; P(X=exact value)=0
- **6.2 PDF f(x):** f(x)≥0; ∫₋∞^∞f(x)dx=1; P(a≤X≤b)=∫ₐᵇf(x)dx
### Integrated Problem (Section 6)
**Problem:** Browsing time X (minutes) has PDF f(x)=k(4x−x²), 0≤x≤4. (a) Find k. (b) Find P(1≤X≤3).
 
**Step 1 — Normalize to find k:** ∫₀⁴(4x−x²)dx = [2x²−x³/3]₀⁴ = 32−64/3 = 32/3.
k×(32/3)=1 → **k = 3/32**
 
**Step 2 — Verify non-negativity:** 4x−x²=x(4−x)≥0 on [0,4] ✓, so f(x)≥0 everywhere.
 
**Step 3 — P(1≤X≤3):** = (3/32)∫₁³(4x−x²)dx = (3/32)[2x²−x³/3]₁³ = (3/32)(9−5/3) = (3/32)(22/3) = **0.6875**
 
**Interpretation:** ~68.75% of customers browse between 1–3 minutes; k had to be solved for first using the normalization axiom before any probability could be computed.
 
---
 
## 7. Continuous Probability Distributions
 
*(Note: Poisson is technically discrete, kept here per your outline.)*
 
### Formulas
- **7.1 Uniform (continuous):** f(x)=1/(b−a); Mean=(a+b)/2; Variance=(b−a)²/12
- **7.2 Exponential:** f(x)=λe^(−λx); Mean=1/λ; Variance=1/λ²; CDF F(x)=1−e^(−λx)
- **7.3 Poisson:** P(X=k)=e^(−λ)λᵏ/k!; Mean=Variance=λ
- **7.4 Normal:** f(x)=[1/(σ√(2π))]e^[−(x−μ)²/(2σ²)]
- **7.5 Standard Normal:** Z=(X−μ)/σ
- **7.6 t-Distribution:** t=(x̄−μ)/(s/√n), df=n−1
- **7.7 Chi-Squared:** χ²=Σ(Oᵢ−Eᵢ)²/Eᵢ, df depends on test
**Example (7.1, Continuous Uniform):** Buses arrive uniformly at random between 0 and 20 minutes after the hour. Find P(you wait between 5 and 12 minutes), and the mean & variance of arrival time.
Step 1 — f(x) = 1/(20−0) = 1/20 for 0≤x≤20.
Step 2 — P(5≤X≤12) = (12−5)×(1/20) = 7/20 = **0.35**.
Step 3 — Mean = (0+20)/2 = **10 min**. Variance = (20−0)²/12 = 400/12 ≈ **33.33**.
 
**Example (7.2, Exponential):** A call center's time between calls follows an exponential distribution with mean 5 minutes. Find λ, and P(next call arrives within 2 minutes).
Step 1 — Mean = 1/λ = 5 → **λ = 0.2** calls/min.
Step 2 — P(X≤2) = F(2) = 1−e^(−0.2×2) = 1−e^(−0.4) = 1−0.6703 = **0.3297**.
**Answer: ~33% chance the next call comes within 2 minutes.**
 
**Example (7.3, Poisson):** A website receives an average of λ=4 visitors per minute. Find P(exactly 6 visitors in a given minute).
Step 1 — P(X=6) = e^(−4)(4⁶)/6! = (0.018316)(4096)/720 = 75.02/720 ≈ **0.1042**.
**Answer: ~10.4% chance of exactly 6 visitors in that minute.**
 
**Example (7.6, t-Distribution):** A small sample of n=10 machine parts has sample mean x̄=52mm, sample SD s=3mm. Test against a claimed population mean μ=50mm by computing the t-statistic (df=9).
Step 1 — t = (x̄−μ)/(s/√n) = (52−50)/(3/√10) = 2/(3/3.1623) = 2/0.9487 ≈ **2.108**
Step 2 — With df=9, this t-value would be compared to a critical t from tables (used later in Section 10.2's full test) — here we've shown how the raw t-statistic itself is computed from sample data, which is the core building block of the t-test.
 
**Example (7.7, Chi-Squared, conceptual building block):** If Z₁, Z₂, Z₃ are independent standard normal variables with values 1.2, −0.8, 0.5, compute χ² = Z₁²+Z₂²+Z₃² (a chi-squared variable with df=3).
Step 1 — χ² = (1.2)² + (−0.8)² + (0.5)² = 1.44 + 0.64 + 0.25 = **2.33**
This illustrates the definition of a chi-squared random variable (sum of squared independent standard normals); the goodness-of-fit *formula* Σ(O−E)²/E is a specific application, worked fully in Section 10.3.
 
### Integrated Problem (Section 7 — Normal Distribution)
**Problem:** Adult male heights ~ Normal(μ=170cm, σ=7cm). (a) P(height > 180cm)? (b) Height at the 90th percentile?
 
**Step 1 (a):** Z = (180−170)/7 ≈ **1.4286**. From tables, P(Z≤1.43)≈0.9236 → P(Z>1.43) = **0.0764** (7.64%).
 
**Step 2 (b):** 90th percentile Z-score ≈ **1.2816**. X = μ+Zσ = 170+(1.2816)(7) ≈ **178.97cm**.
 
**Interpretation:** ~7.64% of men exceed 180cm; 90% of men are shorter than ~179cm — showing standardization used in both directions (value→probability, and probability→value).
 
---
 
## 8. Distribution Functions
 
### Formulas
- **8.1 CDF:** discrete F(x)=Σₜ≤ₓp(t); continuous F(x)=∫₋∞ˣf(t)dt, f(x)=F'(x)
- **8.2 Conditional PDF:** f(x|y) = f(x,y)/fᵧ(y)
**Example (8.2, Conditional PDF):** Joint PDF f(x,y) = x+y for 0≤x≤1, 0≤y≤1. Find the marginal fᵧ(y) and the conditional PDF f(x|y=0.5).
Step 1 — Marginal: fᵧ(y) = ∫₀¹(x+y)dx = [x²/2+xy]₀¹ = 1/2+y.
Step 2 — At y=0.5: fᵧ(0.5) = 0.5+0.5 = **1.0**.
Step 3 — Conditional PDF: f(x|y=0.5) = f(x,0.5)/fᵧ(0.5) = (x+0.5)/1.0 = **x+0.5**, for 0≤x≤1.
Step 4 — Verify it integrates to 1: ∫₀¹(x+0.5)dx = [x²/2+0.5x]₀¹ = 0.5+0.5 = **1 ✓**
This confirms f(x|y=0.5) is itself a valid PDF, obtained by "slicing" the joint PDF at y=0.5 and rescaling by the marginal.
 
### Integrated Problem (Section 8 — CDF)
**Problem:** Using f(x)=(3/32)(4x−x²), 0≤x≤4 (from Section 6): (a) Derive F(x). (b) Find the median.
 
**Step 1 — Integrate:** F(x) = (3/32)[2x²−x³/3] = (3x²)/16 − x³/32, 0≤x≤4.
 
**Step 2 — Check F(4)=1:** 3(16)/16 − 64/32 = 3−2 = **1 ✓**
 
**Step 3 — Solve F(m)=0.5:** (3m²)/16 − m³/32 = 0.5 → 6m²−m³=16 → m³−6m²+16=0.
Testing m=2: 8−24+16=0 ✓. Factoring: (m−2)(m²−4m−8)=0; other roots ≈5.46, −1.46 (outside [0,4]).
**Median = 2 minutes.**
 
**Interpretation:** The CDF was built by integrating the PDF, verified against known normalization, then inverted to solve for a percentile — the median.
 
---
 
## 9. Sampling Theory
 
### Formulas
- **9.1 CLT:** x̄ ~ Approx. Normal(μ, σ²/n) for large n; Standard Error SE = σ/√n
- **9.2 Confidence Interval:** CI = x̄ ± z(α/2)·(σ/√n) [σ known]; or x̄ ± t(α/2,n−1)·(s/√n) [σ unknown]
### Integrated Problem (Section 9)
**Problem:** Bulb lifetimes have population σ=50 hrs. Sample of n=64 gives x̄=1200 hrs. (a) Describe the sampling distribution via CLT. (b) Build a 95% CI for μ.
 
**Step 1 (CLT):** Since n=64≥30, x̄ ~ Normal(μ, 50²/64) = Normal(μ, 39.0625), regardless of the individual bulbs' original distribution shape.
 
**Step 2 (SE):** SE = 50/√64 = **6.25 hrs**
 
**Step 3 (critical value):** 95% CI → α=0.05 → z(0.025) = **1.96**
 
**Step 4 (CI):** Margin = 1.96×6.25 = 12.25. CI = 1200±12.25 = **(1187.75, 1212.25) hrs**
 
**Interpretation:** We're 95% confident the true mean bulb lifetime lies in this range — CLT justified using the normal approximation, then the SE and z-critical value built the interval.
 
---
 
## 10. Hypothesis Testing
 
### Formulas
- **10.1 z-Test:** z = (x̄−μ₀)/(σ/√n)
- **10.2 t-Test:** t = (x̄−μ₀)/(s/√n), df=n−1
- **10.3 Chi-Squared Test:** χ² = Σ(Oᵢ−Eᵢ)²/Eᵢ
**Example (10.2, t-Test):** A tire manufacturer claims average tire life μ₀=60,000 km. A sample of n=10 tires gives x̄=58,500 km, s=2,000 km. Test at α=0.05 (two-tailed) whether the true mean differs from the claim.
Step 1 — Hypotheses: H₀: μ=60,000; H₁: μ≠60,000 (two-tailed, since we're testing "differs," not a specific direction).
Step 2 — Since population σ is unknown and n=10 is small, use the **t-test**, df = n−1 = 9.
Step 3 — t = (58,500−60,000)/(2,000/√10) = (−1,500)/(632.46) ≈ **−2.372**
Step 4 — Critical t for two-tailed α=0.05, df=9 (from t-tables): **t_crit = ±2.262**
Step 5 — Since |−2.372| = 2.372 > 2.262, it falls in the rejection region.
**Decision: Reject H₀** — there's significant evidence the true mean tire life differs from 60,000 km (it appears lower).
 
**Example (10.3, Chi-Squared Test — goodness-of-fit):** A die is rolled 60 times; observed frequencies are: 8,9,12,11,7,13 for faces 1–6. Test at α=0.05 whether the die is fair.
Step 1 — H₀: die is fair (each face has probability 1/6); H₁: die is not fair.
Step 2 — Expected frequency under H₀ for each face: E = 60×(1/6) = **10** for every face.
Step 3 — Compute χ² = Σ(O−E)²/E:
(8−10)²/10 + (9−10)²/10 + (12−10)²/10 + (11−10)²/10 + (7−10)²/10 + (13−10)²/10
= 4/10 + 1/10 + 4/10 + 1/10 + 9/10 + 9/10 = (4+1+4+1+9+9)/10 = 28/10 = **2.8**
Step 4 — df = k−1 = 6−1 = 5. Critical χ² value at α=0.05, df=5 (from chi-squared tables): **χ²_crit ≈ 11.07**
Step 5 — Since 2.8 < 11.07, we do **not** reject H₀.
**Decision: Fail to reject H₀** — there isn't enough evidence to say the die is unfair; the observed deviations are consistent with random chance.
 
### Integrated Problem (Section 10 — z-Test)
**Problem:** Cereal boxes claim mean μ₀=500g, known σ=15g. Sample n=36 gives x̄=495g. Test at α=0.05 whether true mean is *less than* 500g.
 
**Step 1 — Hypotheses:** H₀: μ=500; H₁: μ<500 (one-tailed, since suspicion is specifically underfilling).
 
**Step 2 — Test choice:** σ known, n large → **z-test**.
 
**Step 3 — Statistic:** z = (495−500)/(15/√36) = −5/2.5 = **−2.0**
 
**Step 4 — Critical value:** one-tailed α=0.05 → z_crit = **−1.645**
 
**Step 5 — Decision:** −2.0 < −1.645 → **Reject H₀**. Cross-check via p-value: P(Z≤−2.0) ≈ **0.0228** < 0.05, confirming rejection.
 
**Interpretation:** Significant evidence the true mean weight is below the claimed 500g — the sample mean of 495g is unlikely under H₀ (only ~2.28% chance of seeing this or lower by chance alone).
 
---
 
## Quick Symbol Glossary
 
| Symbol | Meaning |
|---|---|
| n | sample size / total items |
| r, k | number chosen / number of successes |
| p, q | probability of success / failure (q = 1−p) |
| μ | population mean |
| σ | population standard deviation; σ² = variance |
| x̄ | sample mean |
| s | sample standard deviation |
| λ | rate parameter (Poisson/Exponential) |
| Z | standard normal variable |
| f(x) | probability density function (continuous) |
| p(x) | probability mass function (discrete) |
| F(x) | cumulative distribution function |
| df | degrees of freedom |
| α | significance level |
| ρ | correlation coefficient |
 

