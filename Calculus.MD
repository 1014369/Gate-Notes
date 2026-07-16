
Calculus and Optimization — Complete Study Guide
Functions of a Single Variable · Limits · Continuity & Differentiability · Taylor Series · Maxima/Minima · Optimization
PART 1: FUNCTIONS OF A SINGLE VARIABLE
1.1 What is a function, really?
A function f: A → B is a rule that assigns to every element x in a set A (the domain) exactly one element f(x) in a set B (the codomain). The set of actual outputs is the range (⊆ codomain).

Why this matters before calculus: almost every idea in calculus (limits, derivatives, integrals) is a statement about how f(x) behaves as x changes. If you're shaky on domain, range, and the shape of standard functions, you'll misapply calculus rules later (e.g., forgetting that 1/x blows up at 0, or that ln(x) needs x>0). So we start here deliberately.

1.2 Classifying functions (know these by sight)
Type	Example	Key feature
Polynomial	x^3 - 2x + 1	Defined everywhere, smooth
Rational	(x+1)/(x-2)	Undefined where denominator = 0
Algebraic (roots)	√(x-1)	Domain restricted by sign under root
Exponential	e^x, a^x	Always positive, never zero
Logarithmic	ln x	Domain x>0, inverse of exponential
Trigonometric	sin x, cos x, tan x	Periodic; tan x undefined at odd multiples of π/2
Piecewise	f(x)=x^2 for x<0, =x for x≥0	Different rule on different intervals — check junctions!
Even/odd: f(-x) = f(x) → even (symmetric about y-axis, e.g. x^2, cos x). f(-x) = -f(x) → odd (symmetric about origin, e.g. x^3, sin x). This matters later — odd functions integrate to 0 over symmetric intervals, even Taylor series of even functions have only even powers, etc.

Monotonicity: f is increasing if x1 < x2 ⟹ f(x1) < f(x2). This connects directly to the sign of f'(x) in Part 6.

Composition (f∘g)(x) = f(g(x)): domain is all x in domain of g such that g(x) is in domain of f. This trips people up constantly — always check the inner function's output lands in the outer function's allowed domain.

Inverse functions f^{-1}: exists only if f is one-to-one (injective). Graphically, f^{-1} is the reflection of f across y = x. Key relation: f(f^{-1}(x)) = x and f^{-1}(f(x)) = x.

1.3 Worked Problems — Functions
Problem 1 (Easy). Find the domain of f(x) = √(4 - x^2).

Solution: Need 4 - x^2 ≥ 0 ⟹ x^2 ≤ 4 ⟹ -2 ≤ x ≤ 2. Domain: [-2, 2].

Problem 2 (Easy). Find the domain of f(x) = 1/(x^2 - 5x + 6).

Solution: Denominator zero when x^2-5x+6=(x-2)(x-3)=0, i.e. x=2,3. Domain: all reals except 2 and 3, i.e. (-∞,2)∪(2,3)∪(3,∞).

Problem 3 (Medium). Find the domain of f(x) = ln(x-1) + √(5-x).

Solution: Need both pieces valid: x - 1 > 0 ⟹ x > 1, and 5 - x ≥ 0 ⟹ x ≤ 5. Intersection: (1, 5].

Problem 4 (Medium). If f(x) = x^2 + 1 and g(x) = √x, find the domain of (g∘f)(x) and (f∘g)(x).

Solution: (g∘f)(x) = g(f(x)) = √(x^2+1). Since x^2+1 ≥ 1 > 0 always, domain = all reals. (f∘g)(x) = f(g(x)) = (√x)^2 + 1 = x+1, but this is only defined where g(x)=√x is defined, i.e. x ≥ 0. Domain = [0, ∞) even though the simplified formula x+1 looks fine everywhere — this is the classic composition trap: simplify after respecting domain restrictions, not before.

Problem 5 (Medium). Determine whether f(x) = x^3 - 4x is even, odd, or neither.

Solution: f(-x) = (-x)^3 - 4(-x) = -x^3 + 4x = -(x^3-4x) = -f(x). Odd function.

Problem 6 (Hard). Find the inverse of f(x) = (2x+3)/(x-1), x ≠ 1, and state its domain.

Solution: Let y = (2x+3)/(x-1). Solve for x: y(x-1) = 2x+3 ⟹ yx - y = 2x + 3 ⟹ yx - 2x = y+3 ⟹ x(y-2) = y+3 ⟹ x = (y+3)/(y-2). So f⁻¹(x) = (x+3)/(x-2), defined for x ≠ 2 (which makes sense: 2 is a value f never attains, since as x→∞, f(x)→2).

Problem 7 (Hard). A function is defined piecewise: f(x) = x^2 + 1 if x < 1 f(x) = 3 - x if x ≥ 1. Is f one-to-one? Sketch reasoning without graphing tools.

Solution: On x<1: f(x)=x^2+1 is decreasing then increasing around x=0, so it's not monotonic on its own — e.g. f(-2)=5, f(0)=1, f(-1)=2 — check if any two x-values (one possibly ≥1) give equal output. At x=1: f(1)=3-1=2. Is there another x<1 with f(x)=2? x^2+1=2 ⟹ x^2=1 ⟹ x=±1. x=-1<1 is valid and gives f(-1)=2=f(1). So f is NOT one-to-one (two different inputs, -1 and 1, give the same output 2) — hence f has no inverse on this full domain. This is a good example of why you must check the whole domain, not just "it looks like it's always increasing."

PART 2: LIMITS
2.1 The intuitive idea
lim_{x→a} f(x) = L means: as x gets arbitrarily close to a (from either side, but not equal to a), f(x) gets arbitrarily close to L. Crucially, the limit does not care what happens exactly at x = a — f(a) might not even exist, or might differ from L. This decoupling is the whole point of limits: they let us describe behavior "near" a point, including points where the function itself is undefined (like 0/0 forms), which is exactly what we need to define the derivative later.

2.2 The formal (ε–δ) definition — and why we need it
lim_{x→a} f(x) = L means: for every ε > 0, there exists δ > 0 such that whenever 0 < |x - a| < δ, we have |f(x) - L| < ε.

Why bother with this rigor? Intuition ("gets close to") is fine for computation but fails for proofs and edge cases (e.g., functions that oscillate infinitely, like sin(1/x) near 0). The ε–δ definition converts "gets close" into a precise inequality game: you (skeptic) pick how close you want the output (ε); I (prover) must find a matching input-window (δ) that guarantees it. This is the bedrock definition everything else (continuity, derivative) is built on.

Worked ε–δ Problem (Hard). Prove lim_{x→3} (2x+1) = 7 using the ε–δ definition.

Solution: Given ε > 0, we want |(2x+1) - 7| < ε whenever 0 < |x-3| < δ. |(2x+1)-7| = |2x - 6| = 2|x-3|. We want 2|x-3| < ε, i.e. |x-3| < ε/2. So choose δ = ε/2. Then whenever 0<|x-3|<δ, we get |(2x+1)-7| = 2|x-3| < 2δ = ε. ✓ Proven.

2.3 Computing limits — the toolbox (and when to use which tool)
Direct substitution — if f is "nice" (polynomial, rational with nonzero denominator, etc.) at a, just plug in. Use this first always — it's fastest, and most limits from continuous functions are just this.
Factor and cancel — for 0/0 forms in rational/polynomial expressions. Works because the cancelled factor is exactly what's "faking" the discontinuity; the limit only cares about points near a, not at a, so cancelling is legal.
Rationalization — multiply by conjugate when square roots create 0/0. Converts a difference of roots into a difference of squares, which often cancels the problematic factor.
Standard trig/exponential limits (memorize):
lim_{x→0} sin(x)/x = 1
lim_{x→0} (1-cos x)/x = 0, and lim_{x→0} (1-cos x)/x^2 = 1/2
lim_{x→0} (e^x - 1)/x = 1
lim_{x→0} ln(1+x)/x = 1
lim_{x→∞} (1 + 1/x)^x = e
L'Hôpital's Rule — for 0/0 or ∞/∞ indeterminate forms: lim f(x)/g(x) = lim f'(x)/g'(x) (provided the latter exists). Why it works: near the point, both numerator and denominator behave like their tangent-line (linear) approximations; comparing their rates of approach to zero (i.e., derivatives) tells you the ratio's true limiting behavior. Only apply it to genuine 0/0 or ∞/∞ — applying it blindly to non-indeterminate forms gives wrong answers.
Limits at infinity — divide numerator & denominator by the highest power of x present.
Squeeze (Sandwich) Theorem — if g(x) ≤ f(x) ≤ h(x) near a and lim g = lim h = L, then lim f = L too. Essential for limits involving bounded oscillating terms like sin(1/x).
2.4 Indeterminate forms — full list
0/0, ∞/∞, 0·∞, ∞-∞, 0^0, 1^∞, ∞^0. Each needs algebraic manipulation (often turning into a fraction) before L'Hôpital applies. For 1^∞, 0^0, ∞^0: take ln, convert to a 0·∞ or 0/0 form, solve, then exponentiate back.

2.5 Worked Problems — Limits (easy → hard)
Problem 1 (Easy — direct substitution). lim_{x→2} (x^2 + 3x - 1).

Solution: Polynomial, just substitute: 4 + 6 - 1 = 9.

Problem 2 (Easy — factor/cancel). lim_{x→3} (x^2-9)/(x-3).

Solution: (x^2-9)/(x-3) = (x-3)(x+3)/(x-3) = x+3 for x≠3. Limit as x→3: 6.

Problem 3 (Easy–Medium). lim_{x→-1} (x^3+1)/(x+1).

Solution: Factor: x^3+1 = (x+1)(x^2-x+1). So expression = x^2-x+1 for x≠-1. At x=-1: 1+1+1 = 3.

Problem 4 (Medium — rationalization). lim_{x→0} (√(x+4) - 2)/x.

Solution: Multiply by conjugate: (√(x+4)-2)(√(x+4)+2) / [x(√(x+4)+2)] = (x+4-4)/[x(√(x+4)+2)] = x/[x(√(x+4)+2)] = 1/(√(x+4)+2). As x→0: 1/(2+2) = 1/4.

Problem 5 (Medium — trig standard limit). lim_{x→0} sin(5x)/x.

Solution: Write as 5 · sin(5x)/(5x). As x→0, 5x→0, so sin(5x)/(5x) → 1. Limit = 5.

Problem 6 (Medium). lim_{x→0} (1-cos 3x)/x^2.

Solution: Using lim (1-cos θ)/θ^2 = 1/2 with θ=3x: (1-cos3x)/(3x)^2 → 1/2, so (1-cos3x)/x^2 = 9·(1-cos3x)/(9x^2) → 9·(1/2) = 9/2.

Problem 7 (Medium — limit at infinity). lim_{x→∞} (3x^2 - 2x + 1)/(5x^2 + x - 4).

Solution: Divide top & bottom by x^2: (3 - 2/x + 1/x^2)/(5 + 1/x - 4/x^2) → 3/5 as x→∞.

Problem 8 (Medium–Hard — L'Hôpital). lim_{x→0} (e^x - 1 - x)/x^2.

Solution: At x=0: (1-1-0)/0 = 0/0. Apply L'Hôpital: lim (e^x - 1)/(2x) → still 0/0 at x=0. Apply again: lim e^x/2 = 1/2. Answer: 1/2.

Problem 9 (Hard — 0·∞ form). lim_{x→0^+} x·ln(x).

Solution: Rewrite as ln(x)/(1/x), which is -∞/∞ as x→0^+. L'Hôpital: lim (1/x)/(-1/x^2) = lim -x = 0. Answer: 0.

Problem 10 (Hard — 1^∞ form). lim_{x→∞} (1 + 3/x)^x.

Solution: Let L = lim (1+3/x)^x. Take ln: ln L = lim x·ln(1+3/x). Let t = 1/x → 0^+: ln L = lim_{t→0} ln(1+3t)/t. This is 0/0; L'Hôpital: lim 3/(1+3t) = 3. So ln L = 3 ⟹ L = e^3.

Problem 11 (Hard — ∞-∞ form). lim_{x→0} (1/sin x - 1/x).

Solution: Combine: (x - sin x)/(x sin x). At x=0: 0/0. L'Hôpital (differentiate top & bottom w.r.t. x): Top: 1 - cos x. Bottom: sin x + x cos x. Still 0/0 at x=0. Apply again: Top: sin x. Bottom: cos x + cos x - x sin x = 2cos x - x sin x. At x=0: 0/(2) = 0. Answer: 0.

Problem 12 (Hard — squeeze theorem). lim_{x→0} x^2 sin(1/x).

Solution: -1 ≤ sin(1/x) ≤ 1 for all x≠0, so -x^2 ≤ x^2 sin(1/x) ≤ x^2. Since lim_{x→0}(-x^2) = lim_{x→0}(x^2) = 0, by Squeeze Theorem, limit = 0. (Direct substitution or L'Hôpital would fail here — sin(1/x) has no limit at 0 — this problem exists precisely to teach when the squeeze theorem is the right and only tool.)

Problem 13 (Very Hard). Evaluate lim_{x→0} (tan x - x)/x^3.

Solution: 0/0 form. L'Hôpital: lim (sec^2 x - 1)/(3x^2). Still 0/0. Note sec^2x - 1 = tan^2 x, so rewrite as tan^2x/(3x^2) = (1/3)(tan x/x)^2 → (1/3)(1)^2 = 1/3. Answer: 1/3. (This shows a useful trick: rewrite mid-way using an identity instead of blindly differentiating again — often shorter and safer.)

PART 3: CONTINUITY
3.1 Definition
f is continuous at x = a if all three conditions hold:

f(a) is defined,
lim_{x→a} f(x) exists (i.e., left-hand limit = right-hand limit),
lim_{x→a} f(x) = f(a).
Why three separate conditions? Each can fail independently, and each failure has a different "shape":

Condition 1 fails → hole with nothing plotted (e.g., f(x)=1/x at x=0, undefined).
Condition 2 fails (left ≠ right limit) → jump discontinuity (e.g., a step function).
Condition 3 fails (limit exists but ≠ f(a)) → removable discontinuity (a single misplaced point — "fixable" by redefining f(a)).
This is why continuity is stronger than "the limit exists" — continuity ties the limit back to the actual function value.

3.2 Types of discontinuity
Removable: limit exists, but ≠ f(a) (or f(a) undefined). Fix: redefine the single point.
Jump: left-hand limit ≠ right-hand limit (both finite). Common in piecewise functions.
Infinite (essential): f(x) → ±∞ near a (vertical asymptote), e.g. 1/x at 0.
Oscillating: function oscillates infinitely fast, no limit exists at all, e.g. sin(1/x) at 0.
3.3 Continuity on an interval & key theorems
f is continuous on [a,b] if continuous at every interior point, and one-sided continuous at the endpoints.

Intermediate Value Theorem (IVT): If f is continuous on [a,b] and N is any value between f(a) and f(b), then there exists c ∈ (a,b) with f(c) = N. Why it matters: this is the theoretical justification for root-finding — if f(a) and f(b) have opposite signs, IVT guarantees a root in between. It underlies bisection-method algorithms and many existence proofs.

Extreme Value Theorem (EVT): If f is continuous on a closed, bounded interval [a,b], then f attains both a maximum and a minimum value on [a,b]. This is the theoretical backbone of Part 6/7 (optimization) — it's why we're guaranteed a global max/min exists to search for, provided the interval is closed and bounded and f is continuous. Drop either "closed" or "continuous" and the guarantee vanishes (e.g., f(x)=1/x on (0,1) is continuous but unbounded — no max exists).

3.4 Worked Problems — Continuity
Problem 1 (Easy). Is f(x) = (x^2-4)/(x-2) continuous at x=2?

Solution: f(2) is undefined (0/0) — condition 1 fails. Not continuous at x=2 (removable discontinuity, since lim_{x→2} f(x) = lim (x+2) = 4 exists but f(2) isn't defined).

Problem 2 (Easy–Medium). Find k so that f(x) = kx + 1 for x ≤ 2, f(x) = x^2 - 1 for x > 2 is continuous at x=2.

Solution: Left-hand limit: k(2)+1 = 2k+1. Right-hand limit: 2^2-1 = 3. For continuity, 2k+1 = 3 ⟹ k=1.

Problem 3 (Medium). Discuss the continuity of f(x) = sin(x)/x for x≠0, f(0) = 1.

Solution: lim_{x→0} sin(x)/x = 1 = f(0). All three conditions hold. Continuous at x=0 (this is the standard "removable discontinuity fixed by definition" example).

Problem 4 (Medium). Show f(x) = x^3 - x - 2 has a root between x=1 and x=2.

Solution: f is a polynomial → continuous everywhere. f(1) = 1-1-2 = -2 < 0. f(2) = 8-2-2 = 4 > 0. Since f(1)<0<f(2) and f is continuous on [1,2], by IVT there exists c∈(1,2) with f(c)=0. ✓

Problem 5 (Hard). Determine all points of discontinuity of f(x) = 1/(x^2-1) for x≠±1, and classify each.

Solution: Denominator zero at x=1, x=-1. Near both, f(x)→±∞ (check signs: as x→1^-, x^2-1→0^- so f→-∞; as x→1^+, f→+∞). Both are infinite (essential) discontinuities, i.e., vertical asymptotes — not removable.

Problem 6 (Hard). For what value of a is f(x) = (sin 2x)/x for x≠0, f(0)=a continuous at 0? Then discuss differentiability there (this bridges into Part 4).

Solution: lim_{x→0} sin(2x)/x = 2·lim sin(2x)/(2x) = 2(1) = 2. So a=2 makes it continuous. (We'll revisit differentiability of this function in Part 4.)

Problem 7 (Very Hard). Let f(x) = x·[x] where [x] is the greatest-integer (floor) function. Discuss continuity at x=2.

Solution: For x slightly less than 2 (e.g., 1.9), [x]=1, so f(x)=x·1=x → 2 as x→2^-... wait compute limit: lim_{x→2^-} x[x]: for x∈[1,2), [x]=1, so f(x)=x, limit as x→2^- = 2. For x∈[2,3), [x]=2, so f(x)=2x, and f(2) = 2·2 = 4; limit as x→2^+ = 2·2=4. Left-hand limit (2) ≠ right-hand limit (4) → jump discontinuity at x=2. Note f(2)=4 matches the right-hand limit, but continuity requires both one-sided limits to agree with each other (and with f(2)) — here they don't, so f is discontinuous at 2 despite being "defined" there.

PART 4: DIFFERENTIABILITY
4.1 Definition of the derivative
f'(a) = lim_{h→0} [f(a+h) - f(a)]/h (equivalently lim_{x→a} [f(x)-f(a)]/(x-a)).

Geometric meaning: the slope of the secant line through (a, f(a)) and (a+h, f(a+h)) as h→0 becomes the slope of the tangent line at a. Physical meaning: instantaneous rate of change (e.g., velocity = derivative of position).

Why we define it as a limit and not just "plug in h=0": plugging h=0 directly gives 0/0 — undefined. The entire reason limits were built up in Part 2 was to make sense of exactly this kind of "instantaneous" quantity, which classical algebra can't handle directly.

4.2 Differentiability ⟹ Continuity (but NOT conversely) — crucial theorem
Claim: If f is differentiable at a, then f is continuous at a.

Proof sketch: f(x) - f(a) = [f(x)-f(a)]/(x-a) · (x-a). Taking lim_{x→a}: RHS → f'(a) · 0 = 0. So lim_{x→a} f(x) = f(a), i.e., continuous. ∎

The converse is FALSE — a function can be continuous but not differentiable. Classic example: f(x)=|x| is continuous everywhere but not differentiable at x=0 (sharp corner — left derivative -1 ≠ right derivative +1). This asymmetry (differentiability is strictly stronger than continuity) is one of the most important structural facts in calculus — always check continuity first when investigating differentiability, since if continuity fails, differentiability automatically fails too (no need to even compute the derivative limit).

4.3 When differentiability fails — three visual signatures
Corner/kink — one-sided derivatives disagree (e.g. |x| at 0).
Vertical tangent — derivative → ±∞ (e.g. f(x) = x^{1/3} at 0).
Discontinuity — automatically non-differentiable (from 4.2).
4.4 Differentiation rules (the "why", briefly)
Power rule: d/dx(x^n) = n x^{n-1} — provable by binomial expansion in the limit definition.
Product rule: (fg)' = f'g + fg' — NOT f'g'! Comes from adding and subtracting a cross term f(x+h)g(x) - f(x+h)g(x) inside the difference quotient.
Quotient rule: (f/g)' = (f'g - fg')/g^2.
Chain rule: d/dx f(g(x)) = f'(g(x))·g'(x) — because an infinitesimal change in x first gets scaled by g'(x) (change in the inner function), then that change gets scaled again by f' evaluated at the new point. This is the single most important rule for composite functions and appears constantly in optimization (Part 7) and Taylor series derivations (Part 5).
4.5 Worked Problems — Differentiability
Problem 1 (Easy). Using the definition, find f'(x) for f(x) = x^2.

Solution: f'(x) = lim_{h→0} [(x+h)^2 - x^2]/h = lim [2xh+h^2]/h = lim (2x+h) = 2x.

Problem 2 (Easy–Medium). Check differentiability of f(x) = |x-3| at x=3.

Solution: Left derivative: for x<3, f(x)=3-x, so f'=-1. Right derivative: for x>3, f(x)=x-3, so f'=1. -1 ≠ 1 → not differentiable at x=3 (corner point). Function is still continuous there (check: lim f(x) = 0 = f(3) ✓).

Problem 3 (Medium). Is f(x) = x^{1/3} differentiable at x=0?

Solution: f'(0) = lim_{h→0} [h^{1/3} - 0]/h = lim h^{-2/3} → ∞. Derivative blows up. Not differentiable at 0 (vertical tangent), even though f is continuous there.

Problem 4 (Medium — revisit Continuity Problem 6). Is f(x) = sin(2x)/x for x≠0, f(0)=2 differentiable at x=0?

Solution: We showed it's continuous at 0. Now: f'(0) = lim_{h→0} [f(h)-f(0)]/h = lim [sin(2h)/h - 2]/h = lim [sin(2h) - 2h]/h^2. This is 0/0; use the earlier-style expansion or L'Hôpital twice: numerator derivative 2cos(2h) - 2, still 0/0 at h=0; derivative again: -4sin(2h), over denominator derivative 2h... let's apply L'Hôpital properly: lim [sin(2h)-2h]/h^2 → L'Hôpital: lim [2cos(2h)-2]/(2h) → still 0/0 → L'Hôpital again: lim [-4sin(2h)]/2 = 0. So f'(0) = 0. Differentiable at 0, with f'(0)=0.

Problem 5 (Hard). Determine a, b such that f(x) = x^2 for x ≤ 1, f(x) = ax+b for x>1 is differentiable at x=1.

Solution: Continuity first (necessary condition): f(1^-) = 1, f(1^+) = a+b. Need a+b=1. Differentiability: left derivative of x^2 at 1 is 2(1)=2. Right derivative of ax+b is a. Need a=2. From a+b=1: b = 1-2 = -1. Answer: a=2, b=-1.

Problem 6 (Hard). Using product & chain rule, differentiate f(x) = x^2 · sin(3x^2+1).

Solution: Let u=x^2, v=sin(3x^2+1). u'=2x. For v: chain rule, v' = cos(3x^2+1)·6x. Product rule: f' = u'v + uv' = 2x·sin(3x^2+1) + x^2·6x·cos(3x^2+1) = 2x sin(3x^2+1) + 6x^3 cos(3x^2+1).

Problem 7 (Very Hard). Show that f(x) = x^2 sin(1/x) for x≠0, f(0)=0 is differentiable at 0, but f' is not continuous at 0. (This demonstrates that differentiability of f does not guarantee continuity of f' — a subtle but important distinction.)

Solution: f'(0) = lim_{h→0} [h^2 sin(1/h) - 0]/h = lim h sin(1/h). Since |sin(1/h)|≤1, by Squeeze Theorem this limit is 0. So f'(0)=0 exists — f is differentiable at 0. For x≠0, using product+chain rule: f'(x) = 2x sin(1/x) + x^2 cos(1/x)·(-1/x^2) = 2x sin(1/x) - cos(1/x). Now check lim_{x→0} f'(x): the term 2x sin(1/x) → 0 (squeeze), but cos(1/x) oscillates between -1 and 1 with no limit as x→0. So lim_{x→0} f'(x) does not exist, while f'(0)=0 is defined. Hence f' is discontinuous at 0 — a genuinely advanced but instructive example: differentiable everywhere, but the derivative function itself isn't continuous.

PART 5: TAYLOR SERIES
5.1 The core idea — why we want polynomial approximations
Polynomials are the easiest functions to compute (just add, multiply). Functions like e^x, sin x, ln x are hard to evaluate exactly by hand. Taylor's idea: near a point x=a, approximate a complicated (but smooth) function by a polynomial that matches the function's value and as many derivatives as possible at a. The more derivatives you match, the better the approximation near a.

5.2 Building it up from scratch
Zeroth-order approximation: just match the value: P_0(x) = f(a). Crude — constant, ignores that f changes.

First-order (linear/tangent line) approximation: also match the slope: P_1(x) = f(a) + f'(a)(x-a). This is exactly the tangent line — and it's why the derivative is useful for approximation, not just for slopes.

Second-order: also match curvature (second derivative): P_2(x) = f(a) + f'(a)(x-a) + f''(a)/2! · (x-a)^2. The 2! shows up because differentiating (x-a)^2 twice gives 2, so dividing by 2! makes the coefficient exactly f''(a) when you differentiate P_2 twice and evaluate at a. This pattern continues.

General Taylor Series (about x=a): f(x) = f(a) + f'(a)(x-a) + f''(a)/2!·(x-a)^2 + f'''(a)/3!·(x-a)^3 + ... = Σ_{n=0}^∞ f^{(n)}(a)/n! · (x-a)^n

Maclaurin series = Taylor series with a=0: f(x) = Σ f^{(n)}(0)/n! · x^n

5.3 Taylor's Theorem with Remainder (why approximation has a guaranteed error bound)
If we stop at degree n, f(x) = P_n(x) + R_n(x), where the Lagrange remainder is R_n(x) = f^{(n+1)}(c)/(n+1)! · (x-a)^{n+1} for some c between a and x.

Why this matters practically: it lets us bound the error of a Taylor approximation without knowing c exactly — just bound |f^{(n+1)}(c)| over the interval, and you get a guaranteed worst-case error. This is essential in numerical analysis (e.g., how many terms of a series do you need for a calculator to compute sin(0.1) accurate to 6 decimal places?).

5.4 Standard Maclaurin Series (memorize these — they recur constantly)
e^x = 1 + x + x^2/2! + x^3/3! + ... = Σ x^n/n! (converges for all x)
sin x = x - x^3/3! + x^5/5! - ... = Σ (-1)^n x^{2n+1}/(2n+1)!
cos x = 1 - x^2/2! + x^4/4! - ... = Σ (-1)^n x^{2n}/(2n)!
ln(1+x) = x - x^2/2 + x^3/3 - ...  (converges for -1 < x ≤ 1)
1/(1-x) = 1 + x + x^2 + x^3 + ... (converges for |x|<1, this is just the geometric series)
(1+x)^k = 1 + kx + k(k-1)/2! x^2 + ... (Binomial series, converges for |x|<1)
Notice: sin x has only odd powers (it's an odd function — see Part 1.2!), cos x has only even powers (even function). This isn't a coincidence — it's a direct consequence of the symmetry properties discussed back in Part 1.

5.5 Worked Problems — Taylor Series
Problem 1 (Easy). Find the first three nonzero terms of the Maclaurin series for f(x) = e^{2x}.

Solution: Substitute 2x into e^u = 1+u+u^2/2!+...: e^{2x} = 1 + 2x + (2x)^2/2 + ... = 1 + 2x + 2x^2 + ....

Problem 2 (Easy–Medium). Find the Taylor series of f(x)=ln x about a=1 up to the x^3 term.

Solution: f(1)=0. f'(x)=1/x, f'(1)=1. f''(x)=-1/x^2, f''(1)=-1. f'''(x)=2/x^3, f'''(1)=2. f(x) ≈ 0 + 1(x-1) + (-1)/2!(x-1)^2 + 2/3!(x-1)^3 = (x-1) - (x-1)^2/2 + (x-1)^3/3.

Problem 3 (Medium). Derive the Maclaurin series for cos x from first principles (compute derivatives directly at 0).

Solution: f(x)=cos x, f(0)=1 f'(x)=-sin x, f'(0)=0 f''(x)=-cos x, f''(0)=-1 f'''(x)=sin x, f'''(0)=0 f''''(x)=cos x, f''''(0)=1 (cycle repeats every 4) Series: 1 + 0 - x^2/2! + 0 + x^4/4! - ... = 1 - x^2/2! + x^4/4! - ... ✓ matches standard result.

Problem 4 (Medium). Use known series to find the Maclaurin series of f(x) = e^x sin x up to the x^3 term.

Solution: e^x ≈ 1+x+x^2/2+x^3/6, sin x ≈ x - x^3/6. Multiply, keeping terms up to x^3: (1+x+x^2/2+x^3/6)(x - x^3/6) = x - x^3/6 + x^2 - x^4/6(ignore, degree>3) + x^3/2 - ... + x^3/6·x(ignore)  Let's do it carefully term by term up to x^3:

1 · x = x
1 · (-x^3/6) = -x^3/6
x · x = x^2
x · (-x^3/6) → degree 4, ignore
(x^2/2) · x = x^3/2
(x^2/2)·(-x^3/6) → degree 5, ignore
(x^3/6) · x → degree 4, ignore
Sum: x + x^2 + (-1/6 + 1/2)x^3 = x + x^2 + (1/3)x^3. Answer: e^x sin x ≈ x + x^2 + x^3/3 (up to cubic term).

Problem 5 (Hard). Use Taylor's theorem with the Lagrange remainder to estimate e^{0.1} using a degree-3 polynomial, and bound the error.

Solution: P_3(x) = 1+x+x^2/2+x^3/6. At x=0.1: P_3(0.1) = 1 + 0.1 + 0.005 + 0.0001667 ≈ 1.1051667. Error bound: R_3(x) = f^{(4)}(c)/4! · x^4 = e^c/24 · (0.1)^4 for some c∈(0,0.1). Since e^c < e^{0.1} < 1.2 (loose bound: e^{0.1}<e^{1}<3, or tighter e^{0.1}<1.2): |R_3| < 1.2/24 · 0.0001 = 0.000005. So our estimate 1.1051667 is accurate to within 5×10^{-6} — matches the true value e^{0.1} ≈ 1.105171 extremely well.

Problem 6 (Hard). Find the Maclaurin series for f(x) = 1/(1+x^2) and use it to derive the series for arctan(x).

Solution: Using geometric series with u=-x^2: 1/(1-u) = 1+u+u^2+..., so 1/(1+x^2) = 1 - x^2 + x^4 - x^6 + ... Since arctan'(x) = 1/(1+x^2), integrate term by term (integration is the reverse of differentiation, valid term-by-term within radius of convergence): arctan(x) = x - x^3/3 + x^5/5 - x^7/7 + ... (using arctan(0)=0 to fix constant of integration).

Problem 7 (Very Hard). Show, using the Lagrange remainder, that the Maclaurin series for sin x converges to sin x for every real x (i.e. the remainder → 0 as n→∞ for any fixed x).

Solution: For f(x)=sin x, every derivative is ±sin x or ±cos x, so |f^{(n+1)}(c)| ≤ 1 for all c, n. Remainder: |R_n(x)| = |f^{(n+1)}(c)|/(n+1)! · |x|^{n+1} ≤ |x|^{n+1}/(n+1)!. For any fixed x, as n→∞, |x|^{n+1}/(n+1)! → 0 (factorial growth dominates any fixed power/exponential — this is a standard fact, provable via ratio test: ratio of consecutive terms |x|/(n+2) → 0). Since R_n(x) → 0 for every real x, the Taylor series converges to sin(x) for all real x — this is why we can write the infinite series with an equals sign, not just "≈", for sine (and by identical argument, cosine and e^x).

PART 6: MAXIMA AND MINIMA
6.1 Why derivatives detect extrema — the core intuition
At a local maximum, the function rises then falls: slope goes from positive → negative, passing through (or being undefined at) zero. At a local minimum, the reverse: slope goes negative → positive. This single observation — extrema occur where the slope changes sign, or fails to exist — is the entire foundation of optimization.

6.2 Critical points
x=c is a critical point of f if f'(c) = 0 or f'(c) does not exist (but c is in the domain of f).

Fermat's Theorem: If f has a local max or min at c, and f'(c) exists, then f'(c)=0. (Proof idea: if f'(c)>0, f is increasing near c, so points slightly right of c are larger — contradicts a max; similarly if f'(c)<0. So f'(c) must be exactly 0.)

Important subtlety: f'(c)=0 does NOT guarantee an extremum — e.g. f(x)=x^3 has f'(0)=0 but x=0 is neither a max nor min (it's an inflection point / "saddle"). Critical points are only candidates — you must test them further.

6.3 First Derivative Test
Check the sign of f' just to the left and right of a critical point c:

+ to - → local maximum at c
- to + → local minimum at c
same sign both sides → not an extremum (e.g., inflection with horizontal tangent, as in x^3)
Why this works: it's a direct restatement of the intuition in 6.1 — sign change of the slope is literally the definition of "turning around."

6.4 Second Derivative Test
If f'(c)=0:

f''(c) > 0 → concave up → local minimum
f''(c) < 0 → concave down → local maximum
f''(c) = 0 → test is inconclusive — must fall back to the first derivative test or check higher derivatives.
Why concavity determines this: f''(c)>0 means the slope f' is increasing through c; since f'(c)=0, that means f' goes from negative (just before) to positive (just after) — exactly the "-to-+" signature of a minimum from 6.3. So the second derivative test is really just a shortcut that infers the sign-change pattern from concavity, without needing to separately evaluate f' on both sides.

6.5 Global (Absolute) Extrema on a Closed Interval
By the Extreme Value Theorem (Part 3.3), a continuous function on [a,b] attains a global max and min. To find them:

Find all critical points inside (a,b).
Evaluate f at those critical points and at both endpoints a, b.
The largest value found is the global max; the smallest is the global min.
Why endpoints matter separately: the derivative test only detects interior turning points — but a closed interval's boundary can itself hold the true global extreme (the function might be monotonically increasing right up to b, making b the max, without f'(b)=0).

6.6 Worked Problems — Maxima and Minima
Problem 1 (Easy). Find and classify the critical points of f(x) = x^2 - 4x + 3.

Solution: f'(x) = 2x-4 = 0 ⟹ x=2. f''(x)=2>0 → local (and global) minimum at x=2, value f(2)=4-8+3=-1.

Problem 2 (Easy–Medium). Find and classify critical points of f(x) = x^3 - 3x.

Solution: f'(x) = 3x^2-3 = 3(x-1)(x+1) = 0 ⟹ x=1, x=-1. f''(x) = 6x. At x=1: f''=6>0 → local min, f(1)=1-3=-2. At x=-1: f''=-6<0 → local max, f(-1)=-1+3=2.

Problem 3 (Medium). Find the absolute max and min of f(x) = x^3 - 3x^2 + 1 on [-1, 3].

Solution: f'(x) = 3x^2-6x = 3x(x-2) = 0 ⟹ x=0, x=2 (both inside [-1,3]). Evaluate at critical points and endpoints: f(-1) = -1-3+1 = -3 f(0) = 1 f(2) = 8-12+1 = -3 f(3) = 27-27+1 = 1 Absolute max = 1 (attained at both x=0 and x=3). Absolute min = -3 (attained at both x=-1 and x=2). Good example showing extrema can be attained at multiple points.

Problem 4 (Medium). Show f(x) = x^3 has a critical point at x=0 that is neither a max nor min.

Solution: f'(x)=3x^2=0 ⟹ x=0. f''(x)=6x, so f''(0)=0 — second derivative test inconclusive. Use first derivative test: f'(x)=3x^2 ≥ 0 for all x (never negative) — sign does NOT change across x=0 (positive on both sides, technically zero only at the point itself). Not an extremum — it's a stationary inflection point.

Problem 5 (Hard). Find all local extrema of f(x) = x^4 - 4x^3.

Solution: f'(x) = 4x^3 - 12x^2 = 4x^2(x-3) = 0 ⟹ x=0, x=3. Test sign of f' around each:

Near x=0: for x slightly negative (say -1): 4(1)(-1-3)=4(1)(-4)=-16<0. For x slightly positive (say 1): 4(1)(1-3)=4(1)(-2)=-8<0. Same sign both sides → x=0 is NOT an extremum (inflection with horizontal tangent).
Near x=3: for x slightly less (say 2): 4(4)(2-3)=4(4)(-1)=-16<0. For x slightly more (say 4): 4(16)(4-3)=64>0. Sign changes - to + → local minimum at x=3, value f(3) = 81-108=-27.
Problem 6 (Hard). Find the local extrema of f(x) = x + 1/x for x≠0.

Solution: f'(x) = 1 - 1/x^2 = 0 ⟹ x^2=1 ⟹ x=±1. f''(x) = 2/x^3. At x=1: f''=2>0 → local min, f(1)=1+1=2. At x=-1: f''=-2<0 → local max, f(-1)=-1-1=-2. (Interesting: the "local max" value -2 is actually less than the "local min" value 2 — perfectly consistent, since these are only local extrema on separate branches of the domain, separated by the discontinuity at x=0; there's no contradiction because global comparison across the two branches isn't meaningful here.)

Problem 7 (Very Hard). Find the absolute maximum of f(x) = x·e^{-x^2} on (-∞, ∞).

Solution: f'(x) = e^{-x^2} + x·e^{-x^2}·(-2x) = e^{-x^2}(1-2x^2) = 0. Since e^{-x^2} never zero, need 1-2x^2=0 ⟹ x^2 = 1/2 ⟹ x = ±1/√2. Check f'' or first-derivative sign, or reason directly: as x→±∞, f(x)→0 (exponential decay dominates). At x=1/√2: f = (1/√2)e^{-1/2} = 1/(√2·√e) = 1/√(2e) ≈ 0.4289. At x=-1/√2, by odd symmetry f=-0.4289 (a local min). Since f→0 at both infinities and the only interior critical points give ±0.4289, the absolute maximum is 1/√(2e) at x = 1/√2, and absolute minimum is -1/√(2e) at x=-1/√2.

PART 7: OPTIMIZATION INVOLVING A SINGLE VARIABLE
7.1 The general strategy (the "recipe")
Real-world optimization problems rarely arrive as a clean function of one variable — you have to build that function. The standard recipe:

Identify the quantity to optimize (call it Q) and write it as a formula, usually in terms of two or more variables initially (e.g., area = length × width).
Find the constraint relating those variables (e.g., a fixed perimeter, a fixed volume, a fixed budget) — this is what lets you eliminate variables.
Substitute the constraint into Q so it becomes a function of a single variable. This is exactly why this topic sits under "functions of a single variable" — the whole point of the constraint is to reduce the problem to one you can attack with Parts 4–6.
Determine the domain of that single variable from the physical context (e.g., lengths must be positive, and often bounded above too) — this connects to Part 1.2 and matters for Part 6.5 (closed-interval extrema).
Differentiate, find critical points, and classify using first/second derivative tests (Part 6).
Check endpoints/boundary behavior if the domain is closed or if the function could be unbounded, and interpret the answer in context (round appropriately, check it makes physical sense).
7.2 Worked Problems — Optimization (easy → hard)
Problem 1 (Easy — classic fence problem). A farmer has 200 m of fencing to enclose a rectangular field. What dimensions maximize the area?

Solution: Let length = x, width = y. Constraint (perimeter): 2x+2y=200 ⟹ y = 100-x. Area: A(x) = x(100-x) = 100x - x^2, domain 0<x<100. A'(x) = 100-2x = 0 ⟹ x=50. A''=-2<0 → max. Then y=100-50=50. The optimal shape is a 50m × 50m square, giving max area 2500 m². (Nice general lesson: for a fixed perimeter, the rectangle of maximum area is always a square.)

Problem 2 (Easy–Medium). Find two positive numbers whose sum is 20 and whose product is maximum.

Solution: Let numbers be x and 20-x, 0<x<20. Product P(x)=x(20-x)=20x-x^2. P'(x)=20-2x=0 ⟹ x=10. P''=-2<0 → max. Numbers: 10 and 10, max product = 100.

Problem 3 (Medium — box with fixed material). An open-top box is to be made from a square sheet of cardboard 12 cm on a side by cutting equal squares of side x from each corner and folding up the sides. Find x that maximizes the box's volume.

Solution: Base side after folding = 12-2x, height = x. V(x) = x(12-2x)^2, domain 0<x<6. Expand or use product rule: V(x) = x(144 - 48x + 4x^2) = 144x - 48x^2 + 4x^3. V'(x) = 144 - 96x + 12x^2 = 12(x^2 - 8x + 12) = 12(x-2)(x-6). Critical points: x=2, x=6. Since domain is (0,6), only x=2 is interior (x=6 gives zero volume, boundary). V''(x) = -96+24x. At x=2: V''=-96+48=-48<0 → max at x=2. Max volume: V(2) = 2(12-4)^2 = 2(64)=128 cm³.

Problem 4 (Medium — closed cylinder, minimize surface area). A cylindrical can must have volume V=500 cm³. Find the radius and height that minimize the total surface area (material used), assuming a closed can (top and bottom included).

Solution: Volume constraint: πr^2h = 500 ⟹ h = 500/(πr^2). Surface area: S = 2πr^2 + 2πrh (two circles + lateral surface). Substitute: S(r) = 2πr^2 + 2πr·500/(πr^2) = 2πr^2 + 1000/r, domain r>0. S'(r) = 4πr - 1000/r^2 = 0 ⟹ 4πr = 1000/r^2 ⟹ r^3 = 1000/(4π) = 250/π. r = (250/π)^{1/3}. Check S''(r) = 4π + 2000/r^3 > 0 always (for r>0) → confirmed minimum. Then h = 500/(πr^2). A nice simplification: with this r, one can show h = 2r (can height equals diameter) — the classical "optimal can" result. Numerically: r ≈ (79.6)^{1/3} ≈ 4.30 cm, h ≈ 8.60 cm.

Problem 5 (Medium–Hard — minimizing distance). Find the point on the parabola y = x^2 closest to the point (0, 3).

Solution: Distance squared (easier to minimize than distance itself, since square root is monotonic — a very common trick): D(x) = x^2 + (x^2-3)^2 [using y=x^2 as the point's y-coordinate, distance from (x, x^2) to (0,3)]. Expand: D(x) = x^2 + x^4 - 6x^2 + 9 = x^4 - 5x^2 + 9. D'(x) = 4x^3 - 10x = 2x(2x^2-5) = 0 ⟹ x=0 or x^2 = 5/2 ⟹ x=±√(5/2). D''(x) = 12x^2 - 10. At x=0: D''=-10<0 → local max (so x=0 is the FARTHEST nearby point, not closest). At x=±√(5/2): D'' = 12(5/2)-10 = 30-10=20>0 → local min. So the closest points are x = ±√(5/2), y = x^2 = 5/2. Closest points: (±√(5/2), 5/2), i.e. (±1.58, 2.5) approximately.

Problem 6 (Hard — cost/revenue optimization). A company's cost to produce x units is C(x) = 0.02x^2 + 4x + 500 (dollars), and each unit sells for a price p(x) = 20 - 0.01x (demand decreases as more units are sold). Find the production level that maximizes profit, and confirm it's a maximum.

Solution: Revenue: R(x) = x·p(x) = 20x - 0.01x^2. Profit: P(x) = R(x)-C(x) = 20x-0.01x^2 - 0.02x^2 - 4x - 500 = -0.03x^2 + 16x - 500. P'(x) = -0.06x + 16 = 0 ⟹ x = 16/0.06 ≈ 266.67. P''(x) = -0.06 < 0 → confirmed maximum. Since production is typically integer, check x=266 and x=267: P(266) = -0.03(266)^2+16(266)-500 = -0.03(70756)+4256-500 = -2122.68+4256-500=1633.32 P(267) = -0.03(71289)+4272-500 = -2138.67+4272-500=1633.33 Both essentially tie (as expected near a smooth max); x ≈ 267 units maximizes profit at about $1633.33.

Problem 7 (Hard — Norman window / composite shape). A Norman window has the shape of a rectangle topped by a semicircle. The perimeter is fixed at 10 m. Find the dimensions that maximize the area of light let in (i.e. maximize total area).

Solution: Let rectangle width = 2r (so semicircle radius = r), rectangle height = h. Perimeter (rectangle's 2 vertical sides + bottom + semicircular arc, NOT the top straight edge since it's replaced by the arc): P = 2h + 2r + πr = 10 ⟹ h = (10 - 2r - πr)/2 = 5 - r - πr/2. Area: A = 2r·h + (1/2)πr^2 = 2r(5 - r - πr/2) + πr^2/2 = 10r - 2r^2 - πr^2 + πr^2/2 = 10r - 2r^2 - πr^2/2. A(r) = 10r - (2 + π/2)r^2, domain r>0 (and h>0 requires r < 10/(2+π)). A'(r) = 10 - 2(2+π/2)r = 10 - (4+π)r = 0 ⟹ r = 10/(4+π). A''(r) = -(4+π) < 0 → maximum confirmed. r = 10/(4+π) ≈ 1.40 m. Then h = 5 - r - πr/2 = 5 - r(1+π/2). Plug in: h ≈ 5 - 1.40(1+1.571) ≈ 5-3.60=1.40 m. Interesting result: h ≈ r — the rectangle's height equals the semicircle's radius at the optimum (a known elegant property of the Norman window problem).

Problem 8 (Very Hard — optimization with a domain-endpoint surprise). A right circular cone is inscribed in a sphere of radius R. Find the height of the cone that maximizes its volume.

Solution: Set up: let the cone's height be h measured from the sphere's "south pole" tangent point through the center. If the cone's apex is at the bottom of the sphere and it opens upward with height h, the base circle lies at height h from the bottom; if the sphere has center at height R (so sphere spans from 0 to 2R), then the base radius r of the cone satisfies (by the geometry of a circle cross-section at height h): r^2 = R^2 - (h-R)^2 = 2Rh - h^2 (this comes from the sphere's equation centered at height R). Cone volume: V = (1/3)πr^2 h = (1/3)π(2Rh-h^2)h = (π/3)(2Rh^2 - h^3), domain 0<h<2R. V'(h) = (π/3)(4Rh - 3h^2) = (π/3)h(4R-3h) = 0 ⟹ h=0 or h = 4R/3. h=0 is a boundary/degenerate case (zero volume). Check h=4R/3 (valid since 0<4R/3<2R): V''(h) = (π/3)(4R - 6h). At h=4R/3: V'' = (π/3)(4R - 8R) = (π/3)(-4R) < 0 → maximum. So the cone of maximum volume inscribed in a sphere of radius R has height h = 4R/3, and correspondingly r^2 = 2R(4R/3) - (4R/3)^2 = 8R^2/3 - 16R^2/9 = 24R^2/9-16R^2/9=8R^2/9, so r = 2R√2/3. Maximum volume: V = (π/3)(2R·(16R^2/9) - 64R^3/27) = (π/3)(32R^3/9 - 64R^3/27) = (π/3)(96R^3/27-64R^3/27)=(π/3)(32R^3/27) = 32πR^3/81. This is a genuinely hard problem because the geometric setup (relating r and h via the sphere) is the hardest part — the calculus at the end is routine once the single-variable function is correctly built. This is the deepest lesson of Part 7: most of the difficulty in optimization lives in Step 1–3 (building the right function of one variable), not in the differentiation itself.

Summary: How These Six Topics Connect
Functions give you the objects to study, and their domain/range rules resurface constantly (e.g., optimization domains, Taylor series radius of convergence).
Limits are the rigorous machinery that lets us talk about "instantaneous" or "boundary" behavior — without them, neither continuity nor the derivative can be properly defined.
Continuity is built directly from limits, and its big theorem (Extreme Value Theorem) is exactly the reason optimization on a closed interval is guaranteed to have a solution.
Differentiability is built from limits too (the difference quotient), is strictly stronger than continuity, and its rules (product/chain) are the day-to-day tools for every derivative you compute afterward.
Taylor series use derivatives at a single point to build increasingly accurate polynomial stand-ins for a function — bridging "local information" (derivatives at one point) to "global behavior" (values everywhere the series converges).
Maxima/Minima use the sign behavior of the first derivative (and the curvature captured by the second) to locate turning points — the mathematical machinery of Part 4 applied to answer "where is this function biggest/smallest?"
Optimization is simply maxima/minima theory applied to a real constructed function, where the hard work is building the one-variable function from a real-world constraint before unleashing the calculus toolkit.
Master these in order, and each subsequent topic will feel like a natural continuation rather than a new, disconnected idea.

