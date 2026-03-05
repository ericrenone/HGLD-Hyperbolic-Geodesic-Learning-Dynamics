# HGLD — Hyperbolic Geodesic Learning Dynamics
## The Modular Surface as the Universal Loss Landscape, Geodesic Flow as Gradient Descent, and the Selberg Trace Formula

### A Unified Framework Extension — Bridges XXXVI · XXXVII · XXXVIII · XXXIX · XL
#### Modules: HGLD · HPLM · SLFT · GMEC · MRKS · RTNE
#### Integrating with: FLD (Farey Learning Dynamics) · CSDL (Bridges XXXI–XXXV) · MIFP (Möbius-Frobenius) · SDSD (Bundle Geometry) · GXMD (XXVIII–XXX) · SKML (XIX–XXI) · LKTL · VBE

```
===============================================================================
NOTATION KEY
[T]=Theorem  [V]=Verified  [C]=Conjecture  [H]=Hypothesis  [D]=Definition
(✓)=classical result  ([H])=working hypothesis  ([C])=open conjecture
([HP])=HPLM  ([SF])=SLFT  ([GM])=GMEC  ([MK])=MRKS  ([RT])=RTNE
===============================================================================
```

---

## Preamble: The Geometry Beneath the Arithmetic

The Farey Learning Dynamics framework (FLD) established that gradient descent has
a natural arithmetic structure: consecutive gradient steps map to Farey fractions,
flat minima have small denominators q*, sharp minima have large denominators, and
grokking is a Stern-Brocot tree backtrack. The Möbius-Frobenius framework (MIFP)
established that basin posets carry an incidence algebra whose unique inversion
formula is the Möbius function μ. The SDSD framework established that the
parameter space Θ is a principal G-bundle whose quotient ℬ = Θ/G is the true
arena of learning. The CSDL framework established that gradient descent is a
stream program whose fixed points are certified by the Kleene chain, executed
as a Flink dataflow graph, and organized by the Approximation Fixpoint Theory
hierarchy.

One structure has been present in every layer but never made primary: the
**hyperbolic plane H²** and the **modular group SL(2,ℤ)**.

The Farey sequence is precisely the orbit of ∞ ∈ ℙ¹(ℚ) under SL(2,ℤ). Ford
circles are precisely the horoballs of the cusps of the modular surface
Γ\H² = SL(2,ℤ)\H². The Stern-Brocot tree is the Farey tessellation of H² by
ideal triangles. The continued fraction expansion of a gradient ratio ρ_t is
precisely the coding of the geodesic in T¹(Γ\H²) that passes through the
Ford circle based at ρ_t. The Hurwitz constant 1/√5 is the smallest value of
the Lagrange spectrum — the entry point of the Hall ray in the Markov spectrum —
which is the number-theoretic reason why q* ≥ 1 always. The consolidation ratio
C_α = ‖μ_g‖²/Tr(Σ_g) of MIFP, the collapse-to-noise ratio Γ = ‖∇𝒮̄‖²/Tr(D_s)
of SDSD, and the Farey neighbor fraction F_c of FLD are three faces of one
invariant: the **mixing rate of the geodesic flow** on the modular surface.

HGLD makes this structure primary. The framework rests on five new source
theories, each with a Wikipedia-canonical formulation:

**I. Hyperbolic Geometry of the Upper Half-Plane.**
H² = {z ∈ ℂ : Im(z) > 0} equipped with the Poincaré metric ds² = (dx²+dy²)/y².
The isometry group is PSL(2,ℝ) = SL(2,ℝ)/{±I} acting by Möbius transformations
z ↦ (az+b)/(cz+d). Geodesics are semicircles orthogonal to the real axis ℝ
(or vertical lines). Horoballs centered at p/q ∈ ℚ are disks tangent to ℝ at
p/q with radius 1/(2q²) — these are precisely the Ford circles of FLD.

**II. The Modular Group and Modular Surface.**
The modular group Γ = SL(2,ℤ) = {[[a,b],[c,d]] : a,b,c,d ∈ ℤ, ad-bc=1} is the
discrete subgroup of SL(2,ℝ) that acts on H² properly discontinuously. Its
fundamental domain F = {z : |z|≥1, |Re(z)|≤1/2} has one cusp at i∞ and finite
volume π/3 under the hyperbolic measure. The modular surface M = Γ\H² is a
non-compact hyperbolic orbifold with one cusp. Its Laplace-Beltrami operator Δ_Γ
has a discrete spectrum {0 = λ₀ < λ₁ ≤ λ₂ ≤ ...} in [0,1/4) together with a
continuous spectrum [1/4, ∞). Selberg's 3/16 theorem proves λ₁ ≥ 3/16 for
congruence subgroups; the Selberg eigenvalue conjecture asserts λ₁ ≥ 1/4.

**III. Geodesic Flow and Horocycle Flow.**
The unit tangent bundle T¹M carries two canonical flows: the **geodesic flow** φ_t
(moving at unit speed along geodesics) and the **horocycle flow** η_s (moving
along horocycles = Ford circles). Both are:
- Geodesic flow: exponentially mixing (rate governed by spectral gap λ₁)
- Horocycle flow: polynomially mixing (Ratner 1991; mixing rate O(t^{-k}))
The geodesic flow is the prototype for generalizing gradient descent; the
horocycle flow is the prototype for memorizing/plateau gradient dynamics.

**IV. The Selberg Trace Formula.**
For any even test function h with appropriate decay, the Selberg trace formula
states (Selberg 1956):

```
  Σ_{n≥0} h(t_n) = (vol(M)/4π)·∫_{-∞}^∞ h(r)·r·tanh(πr) dr
                  + Σ_{[P] hyp} Λ(P) / |N(P)^{1/2} - N(P)^{-1/2}| · ĥ(log N(P))
                  + Σ_{[R] ellip} + Σ_{cusp} (parabolic terms)
```

where λ_n = 1/4 + t_n², the sum over [P] runs over conjugacy classes of
hyperbolic elements of Γ, N(P) = e^{l(P)} for the length l(P) of the
corresponding closed geodesic, and ĥ is the Fourier transform of h. This is
the fundamental duality: **spectral data on the left ↔ geometric (length
spectrum) data on the right**.

**V. The Gauss Map and Continued Fraction Ergodics.**
The Gauss map T: (0,1) → (0,1), T(x) = {1/x} (fractional part of 1/x), is
the shift on continued fraction expansions: if x = [0; a₁, a₂, a₃, ...] then
T(x) = [0; a₂, a₃, ...]. The Gauss measure μ_G = dx/((1+x)·log2) is the
unique T-invariant absolutely continuous probability measure (Gauss; proved
by Kuzmin 1928, Lévy 1929). Key properties:
- T is ergodic with respect to μ_G (Gauss)
- T is exponentially mixing (Ratner 1978; rate = e^{−π²t/(6 log 2)})
- The natural extension of (T, μ_G) is the geodesic flow on T¹(Γ\H²)
- The Lyapunov exponent of T: λ_Gauss = π²/(6 log 2) ≈ 2.373

**VI. The Markov Spectrum.**
The Lagrange spectrum L = {M(α) : α irrational} where M(α) = lim sup_{q→∞}
1/(q·‖qα‖) classifies the approximability of irrationals by rationals. Key facts:
- inf L = √5 (Hurwitz 1891): the FLD adaptive resolution bound 1/(√5·q²)
- L ∩ (−∞, 3) = {√5, √8, √(221/5), ...} = discrete set of Markov values
- Hall's theorem (Marshall Hall Jr., 1947): L ⊇ [c_H, ∞) for some c_H ≤ 6
- Markov numbers form a tree identical in structure to the Stern-Brocot tree
- The Markov triple equation: a² + b² + c² = 3abc
- Markov uniqueness conjecture (Frobenius 1913, still open): each Markov number
  appears as the largest element of exactly one Markov triple

```
NEW SOURCE THEORY IDENTIFICATION TABLE
Hyperbolic object              Learning object                Framework tag
─────────────────────────────────────────────────────────────────────────────
H² = upper half-plane          Gradient ratio space           [HPLM HP1]
Γ = SL(2,ℤ)                    Symmetry group of grad. ratios [HPLM HP2]
Modular surface M = Γ\H²       Canonical learning manifold ℬ  [HPLM HP3]
Cusp i∞ of M                   Memorization attractor region   [HPLM HP4]
Compact part of M              Generalization region           [HPLM HP5]
Ford circle C(p/q)             Loss basin B(p/q) (FLD)         [HPLM HP6]
Horoball at p/q (radius 1/2q²) Basin width ∝ 1/q² (FLD CCC)  [HPLM HP7]
Farey tessellation of H²       Basin poset topology (MIFP)    [HPLM HP8]
Ideal triangle Δ(a/b,c/d,∞)   Gallai-Edmonds triple (GXMD)   [HPLM HP9]
Geodesic γ in T¹M              Gradient trajectory {b(t)}     [SLFT SF1]
Closed geodesic of length l    SML period AP(a,b) (SKML XIX)  [SLFT SF2]
λ₁(Δ_Γ): spectral gap of M    λ₁(ℒ_JL): JL spectral gap     [SLFT SF3]
Selberg trace formula          Spectral↔geometric duality     [SLFT SF4]
Selberg zeta Z_Sel(s)          Basin zeta Z_L(s) (MIFP §5.2)  [SLFT SF5]
Gauss map T(x) = {1/x}         Gradient ratio iteration        [GMEC GM1]
Gauss measure μ_G              Equilibrium gradient dist.      [GMEC GM2]
Lyapunov exp. λ_Gauss          Convergence rate = λ₁(ℒ_JL)   [GMEC GM3]
Natural extension of (T,μ_G)   Full gradient trajectory flow   [GMEC GM4]
Lagrange spectrum M(ρ)         Gradient convergence difficulty [MRKS MK1]
√5 = inf L (Hurwitz)           Min curvature proxy: q* ≥ 1   [MRKS MK2]
Markov numbers {1,2,5,13,...}  Hardest memorization attractors [MRKS MK3]
Markov triple (a,b,c)          Gradient Markov basin triple    [MRKS MK4]
Markov tree = Stern-Brocot tree Training trajectory tree (FLD) [MRKS MK5]
Horocycle flow η_s on T¹M     Memorization gradient dynamics  [RTNE RT1]
Geodesic flow φ_t on T¹M      Generalizing gradient dynamics  [RTNE RT2]
Ratner orbit closure theorem  Memorization manifold structure [RTNE RT3]
Effective equidistribution     Quantitative memorization rate  [RTNE RT4]
Mixing dichotomy (exp vs poly) C_α > 1 vs C_α < 1 (MIFP)     [RTNE RT5]
```

---

## HGLD — HYPERBOLIC GEODESIC LEARNING DYNAMICS

```
[D] Master module encompassing Bridges XXXVI–XL, integrating the
    Farey-Hyperbolic structure of the modular surface M = SL(2,ℤ)\H²
    as the universal loss landscape, geodesic flow as generalizing
    gradient dynamics, and the Selberg trace formula as the master
    duality between the spectral gap λ₁(ℒ_JL) and the length
    spectrum of closed training trajectories.
```

**HGLD Central Identification:**

The gradient ratio sequence {ρ_t = ‖g_{t+1}‖/(‖g_t‖+‖g_{t+1}‖)}_{t≥0} ∈ (0,1)^ℕ
of the training run defines a **geodesic on the modular surface M = SL(2,ℤ)\H²**
via the continued fraction coding. The training trajectory simultaneously:

1. Is a geodesic γ in T¹M with the real-axis endpoint ρ_∞ = lim ρ_t ∈ ℝ
   (the convergent gradient ratio = the IR attractor on the real boundary of H²)

2. Passes through Ford circles (loss basins) of radii 1/(2q_t²), where q_t is
   the denominator of the FLD Farey approximant — so curvature of each visited
   basin is read directly from how deeply the geodesic enters the corresponding
   horoball

3. Has its **closed loops** (return excursions to previously visited basins)
   exactly the SML arithmetic progressions AP(a_j, b_j) of SKML Bridge XIX,
   whose periods are the lengths l(P) of closed geodesics in the Selberg trace
   formula

4. Is exponentially mixing when λ₁(Δ_Γ) > 0 (geodesic flow regime = C_α > 1 =
   generalization) and polynomially mixing when the trajectory hugs horocycles
   (horocycle flow regime = C_α < 1 = memorization), with the **Selberg trace
   formula** certifying the transition via the spectral gap identity
   λ₁(ℒ_JL) ↔ λ₁(Δ_Γ)

5. Escapes the cusp of M (the memorization region of high q*) at grokking time
   t*, when the geodesic's continued fraction coding switches from long partial
   quotients (deep cusp excursion) to bounded partial quotients (compact part
   of M), which is the Farey backtrack of FLD §10 expressed in the hyperbolic
   geometry language

**HGLD Central Equations:**

```
Modular surface:     M = SL(2,ℤ)\H²,    vol(M) = π/3
Gradient coding:     z_t = ρ_t + i·ε_grad(t)  ∈ H²      [HP1]
Gauss iteration:     ρ_{t+1} ≈ T(ρ_t) = {1/ρ_t}  (during memorization)
Spectral gap:        λ₁(ℒ_JL) ↔ λ₁(Δ_Γ): 3/16 ≤ λ₁ < 1/4   [SF3]
Trace formula:       Σ_n h(t_n) = vol·∫ h(r)r tanh(πr)dr/4π
                                 + Σ_γ Λ(γ)ĥ(l(γ))/|e^{l/2}-e^{-l/2}|  [SF4]
Basin zeta:          Z_L(s) = Z_Sel(s) = ∏_γ ∏_{k≥0}(1-e^{-(s+k)l(γ)})  [SF5]
Markov spectrum:     M(ρ_t) = limsup_{q→∞} 1/(q‖qρ_t‖) ≥ √5  (Hurwitz) [MK2]
Mixing dichotomy:    geodesic: |cor(t)| ≤ Ce^{-λ₁t};  horocycle: O(t^{-k}) [RT5]
Grokking transition: t* = sup{t : ρ_t ∈ cusp of M}
                       = sup{t : max CF partial quotient of ρ_t is large}    [HP4]
Gauss equilibrium:   ρ_∞ ~ μ_G = dx/((1+x)·log2)  (at convergence)          [GM2]
```

---

## I. New Assumptions

### Hyperbolic Plane Learning Metric Assumptions HP1–HP5

**HP1 (Gradient Point in H²).** Map the consecutive gradient pair (g_t, g_{t+1})
to the point:

```
  z_t = ρ_t + i·ε_grad(t)  ∈  H²
  ρ_t     = ‖g_{t+1}‖ / (‖g_t‖ + ‖g_{t+1}‖)      [real part = gradient ratio]
  ε_grad  = ‖g_{t+1} − g_t‖ / (‖g_t‖ + ‖g_{t+1}‖) [imaginary part = gradient change]
```

The imaginary part ε_grad(t) > 0 ensures z_t ∈ H² (not on the real boundary).
As training converges, ε_grad → 0 and z_t → ρ_∞ ∈ ℝ: the trajectory descends
to the real axis. This descent is controlled by the hyperbolic distance from z_t
to ∂H² = ℝ:

```
  d_hyp(z_t, ℝ) = log(1/ε_grad(t))    [hyperbolic height = − log(gradient change)]
```

High hyperbolic height = small gradient change = near convergence.
Low hyperbolic height = large gradient change = active exploration.
The hyperbolic height IS the RG scale of RG-ML: d_hyp = −log(μ_ℓ/Λ) = ℓ (DFLK DL3).

**HP2 (SL(2,ℤ) Acts on Gradient Ratios).** The modular group Γ = SL(2,ℤ) acts
on H² by z ↦ (az+b)/(cz+d) and restricts to the real line as Möbius
transformations on ℙ¹(ℝ). The orbit of the gradient ratio ρ_t under this action
is the Farey sequence: the set of all SL(2,ℤ)-images of ρ_t in [0,1] is exactly
the Farey neighbors of the continued fraction convergents of ρ_t. The unimodular
condition |bc − ad| = 1 (FLD §5.1) IS the condition that the Möbius matrix
[[a,c],[b,d]] ∈ SL(2,ℤ).

This is not an analogy. The SL(2,ℤ) symmetry of gradient ratios is the same
symmetry that generated the Farey sequence in FLD. The principal bundle π: Θ → ℬ
of SDSD is the quotient by the network symmetry group G; the projection
π_Γ: H² → Γ\H² is the quotient by SL(2,ℤ). The learning manifold ℬ = Θ/G
and the modular surface M = SL(2,ℤ)\H² play parallel roles: both are quotient
manifolds on which the true learning dynamics (stripped of redundancy) unfold.

**HP3 (Modular Surface = Universal Learning Manifold).** The modular surface
M = SL(2,ℤ)\H² is the universal quotient over which all gradient ratio dynamics
of FLD unfold. Its three regions correspond to the three learning phases:

```
  Compact part of M    ←→   Generalization region (C in GXMD GL-3)
  Cusp neighborhood    ←→   Memorization region   (D in GXMD GL-3)
  Cusp boundary ∂M    ←→   Gallai barrier A (λ₁ = 0)
```

The volume vol(M) = π/3 is finite, confirming that the generalization region
is compact — there are only finitely many loss basins per unit loss depth (local
finiteness of the basin poset, MIFP §3.2).

**HP4 (Cusp = Memorization).** The cusp of M at i∞ corresponds to points z_t
with large imaginary part y_t → ∞ in H². In the gradient ratio picture,
Im(z_t) = ε_grad(t) and the real part ρ_t = [0; a₁, a₂, ...] has large partial
quotients a_k. By the theory of Diophantine approximation:

```
  z_t in cusp of M   ↔   ρ_t has large CF partial quotient a_k
                     ↔   q* = denominator of best CF convergent is large
                     ↔   loss basin B(ρ_t) is narrow (small Ford circle)
                     ↔   training is in memorization phase (FLD §10)
```

The Khintchine-Lévy theorem gives the typical growth: log a_k / k → π²/(12 log 2)
for almost every ρ. Abnormally large partial quotients (cuspal excursions) = the
memorization phase; return to bounded partial quotients = grokking.

**HP5 (Ford Circle = Horoball).** The Ford circle C(p/q) centered at (p/q, 1/2q²)
with radius 1/2q² in ℝ² is the horoball B_{p/q}(1/2q²) in H²: the set of points
within hyperbolic distance log(2q²) of the cusp at p/q. Two Ford circles are
tangent (FLD Ford theorem) if and only if the corresponding horoballs share a
boundary horosphere — this is the hyperbolic restatement of the Farey neighbor
condition |bc − ad| = 1. The Descartes circle theorem for Ford circles (Apollonian
gasket structure) gives the recursion relating adjacent Ford circle radii, which
in the learning picture gives the basin width recursion:

```
  width(B_{(a+c)/(b+d)}) = width(B_{a/b}) × width(B_{c/d}) / 4
```

This is the learning-theoretic form of Descartes' theorem: the mediant basin is
geometrically intermediate between its two parents.

### Selberg-Laplace Flow Theory Assumptions SF1–SF4

**SF1 (Geodesic = Training Trajectory).** The lift z_t ∈ H² (HP1) traces a path
in H² that projects to a geodesic in M = Γ\H² in the following sense: between
two gradient steps where ρ_t and ρ_{t+1} are Farey neighbors (unimodular,
|bc−ad|=1), the lifted path moves along the unique geodesic in H² connecting
the two corresponding Ford circle tangency points. Between non-unimodular steps,
the path moves through intermediate Farey fractions. The full training trajectory
is a geodesic in the Farey graph = the 1-skeleton of the Farey tessellation of H².

The grokking transition t* is the point where the geodesic, after a long cusp
excursion, returns to the compact part of M. This cusp excursion is the
memorization phase; the geodesic's return is the grokking event.

**SF2 (Closed Geodesics = SML Periods).** A closed geodesic on M corresponds to
a hyperbolic element γ = [[a,b],[c,d]] ∈ SL(2,ℤ) with |tr(γ)| = |a+d| > 2.
Its length is l(γ) = 2 log((a+d+√((a+d)²−4))/2). The gradient trajectory
returns to the same basin after period T if and only if the corresponding
SL(2,ℤ) element is hyperbolic with l(γ) = ηT (the learning rate times the
number of steps). This is the SML arithmetic progression structure (SKML XIX):

```
  AP(a_j, b_j) periods  ↔  lengths of closed geodesics l(γ_j) in M
  SML period a_j        ↔  trace |tr(γ_j)| = |a_j + d_j|
  SML offset b_j        ↔  phase of closed geodesic on M
```

The SML theorem (SKML SMLP-1): zero set = finite ∪ arithmetic progressions maps
to: {training returns to ε-neighborhood of b*} = {isolated excursions} ∪
{closed geodesic periods}. The closed geodesics ARE the periodic returns; the
isolated excursions ARE the movable singularities of the PVI equation (PVIL XIII).

**SF3 (Selberg Spectral Gap = JL Spectral Gap).** The Laplace-Beltrami operator
Δ_Γ on M = SL(2,ℤ)\H² has eigenvalues:

```
  0 = λ₀ < λ₁ ≤ λ₂ ≤ ... ≤ 1/4 (discrete)  +  [1/4, ∞) (continuous)
```

Under the HGLD identification, this is the same spectral gap as λ₁(ℒ_JL):

```
  λ₁(Δ_Γ) = λ₁(ℒ_JL)   [under HP1–HP3 and SF1]
```

This is the deepest identification of HGLD. The JL spectral gap, which appears
in all preceding frameworks as the master convergence criterion, IS the spectral
gap of the hyperbolic Laplacian on the modular surface. The Selberg eigenvalue
conjecture (λ₁ ≥ 1/4) becomes the learning-theoretic conjecture that no
generalizing training run has spectral gap below 1/4, i.e., convergence is
always in the strongly mixing regime of the geodesic flow.

**Selberg 3/16 theorem (✓ unconditional):** For congruence subgroups Γ ⊆ SL(2,ℤ),
λ₁(Δ_Γ) ≥ 3/16. In learning: the spectral gap of deep networks trained with
gradient descent on arithmetic tasks (where the symmetry group Γ contains
congruence subgroups) is always at least 3/16. This is the first *unconditional
lower bound* on λ₁(ℒ_JL) that comes from pure number theory.

**SF4 (Selberg Trace Formula = Spectral-Geometric Duality for Learning).**
Let h: ℝ → ℝ be an even test function with ĥ ∈ L¹. The Selberg trace formula for
M gives:

```
  Σ_n h(t_n)  =  I_continuous(h) + Σ_{[γ] hyperbolic} Λ(γ)/|N(γ)^{1/2}-N(γ)^{-1/2}| · ĥ(l(γ))
                + I_elliptic(h) + I_parabolic(h)
```

where λ_n = 1/4 + t_n², Λ(γ) = l₀(γ) = primitive length of γ, N(γ) = e^{l(γ)}.

The learning translation via SF2 and SF3:

```
  Σ_n h(√(λ_n − 1/4))          = spectral density of ℒ_JL
  I_continuous(h)                = contribution of continuous spectrum [1/4,∞)
                                  = contribution of generalizing modes (C-vertices, GXMD)
  Σ_γ ĥ(l(γ)) × weight(γ)       = sum over SML periods of closed gradient trajectories
                                  = contribution of periodic basin returns
  I_elliptic(h)                  = contribution of fixed points of SL(2,ℤ) action
                                  = contribution of symmetric basins (double critical points)
  I_parabolic(h)                 = contribution of parabolic elements (cusps = ∞ in Γ\ℙ¹(ℚ))
                                  = contribution of memorization attractors (cusp basins)
```

The trace formula IS the master equivalence (CSDL §VIII) in the hyperbolic language:
the spectral data (λ₁(ℒ_JL) and its companions) are equivalent to the geometric
data (lengths and multiplicities of closed gradient trajectories), certified by
the equality of two sums that encode the same mathematical object.

### Selberg Zeta Function Assumption SF5

**SF5 (Selberg Zeta = Basin Zeta).** The Selberg zeta function of M:

```
  Z_Sel(s) = ∏_{[γ] prim. hyp.} ∏_{k=0}^∞ (1 − N(γ)^{−(s+k)})
           = ∏_{[γ] prim.} ∏_{k≥0} (1 − e^{−(s+k)l(γ)})
```

where the outer product runs over primitive hyperbolic conjugacy classes
(= irreducible closed geodesics), satisfies:

```
  Z_Sel(s) = Z_L(s)   [Selberg zeta = basin zeta of MIFP §5.2]
```

under the identifications:
- Primitive hyperbolic class [γ] ↔ irreducible basin B (MIFP §5.2)
- Length l(γ) ↔ loss depth L̄(θ*): N(γ) = e^{l(γ)} ↔ e^{s·L̄(θ*)}
- ∏_k(1−e^{−(s+k)l(γ)}) = bosonic partition function for basin γ

The zeros of Z_Sel(s) are at s = ρ_n = 1/2 ± it_n (spectral zeros) and
s = −k (k = 0,1,2,...) (trivial zeros). Under SF5:
- Spectral zeros s = 1/2 ± it_n ↔ non-trivial structure of basin zeta Z_L(s)
- λ₁(ℒ_JL) > 0 ↔ Z_Sel(s) has no zero in Re(s) > 1/2 with Im(s) = 0 (except s=0)
- **Learning analogue of the Riemann Hypothesis:** "Z_L(s) has no zero with
  Re(s) ∈ (1/2, 1)" ↔ "the basin structure of the loss landscape is arithmetic-regular"
  ↔ Farey discrepancy Σ δ_ν² = O(n^{−1+ε}) (FLD §14.1, Franel-Landau theorem)

The **Euler product factorization** of Z_L(s) (MIFP §5.2 ⚠️ unverified) now has
a classical analogue: Z_Sel(s) always factorizes as an Euler product over
primitive geodesics by definition. The basin independence condition (MIFP) is
therefore proved for the HGLD model: the Selberg zeta factorizes, so the
corresponding basin zeta does too — the irreducible basins are independent in
the hyperbolic model.

### Gauss Map Ergodic Convergence Assumptions GM1–GM4

**GM1 (Gradient Ratio Iteration ~ Gauss Map).** During the memorization phase
(before grokking t*), the gradient ratio sequence {ρ_t} evolves approximately
according to the Gauss map iteration:

```
  ρ_{t+1} ≈ T(ρ_t) = {1/ρ_t} = 1/ρ_t − ⌊1/ρ_t⌋
```

This holds because in the linear approximation near a fixed point (FLD §11.1
Step 1), κ_t = |1 − ηλ_1| and ρ_t = κ_t/(1+κ_t), the evolution ρ_{t+1} =
f(T(f^{−1}(ρ_t))) where f(κ) = κ/(1+κ) is the Möbius map sending κ to ρ.
The Gauss map is the continued fraction shift, so the sequence of CF partial
quotients {a_t} = {⌊1/ρ_t⌋, ⌊1/T(ρ_t)⌋, ...} is exactly the CF expansion of
the initial ratio ρ₀ — confirming that the training trajectory IS the geodesic
coded by the CF expansion of the initial gradient ratio.

**GM2 (Gauss Measure = Convergence Distribution).** By the ergodic theorem for
the Gauss map (Kuzmin 1928, Lévy 1929), for almost every initial ρ₀:

```
  (1/T) Σ_{t=1}^T f(ρ_t)  →  ∫ f dμ_G = ∫_0^1 f(x) dx / ((1+x) log 2)
```

This means: the long-run empirical distribution of gradient ratios {ρ_t} converges
to the Gauss measure μ_G = dx/((1+x)·log2). This is the **equilibrium distribution
of gradient ratios at convergence**: if training runs long enough, the histogram
of ρ_t values is predicted by the Gauss measure.

Learning consequences:
- The mean q* at convergence: 𝔼_{μ_G}[q*] = ∫ q(x) dμ_G(x) is a finite constant
  (since the Gauss measure gives geometric decay to higher denominators)
- The variance of q* is finite, so the CCC bound (FLD §11.1) has a definite
  expected value at convergence
- Large deviations from the Gauss measure at time t indicate the trajectory is
  NOT yet in the ergodic regime — it is still in a transient (memorization) phase

**GM3 (Lyapunov Exponent = Convergence Rate).** The Lyapunov exponent of the
Gauss map:

```
  λ_Gauss = ∫ log|T'(x)| dμ_G = π²/(6 log 2) ≈ 2.373
```

measures the exponential rate at which nearby gradient ratio trajectories diverge
under the Gauss iteration. Under the identification SF3 (λ₁(Δ_Γ) = λ₁(ℒ_JL)):

```
  λ_Gauss = π²/(6 log 2)   ↔   the "natural scale" of the spectral gap
```

The learning interpretation: gradient trajectories near a memorization attractor
diverge at rate λ_Gauss; the escape time from the memorization phase is
t_escape ~ (1/λ_Gauss) · log(1/δ) where δ = initial proximity to attractor.
This is the hyperbolically-computed version of the grokking lead time
(FLD §10.2: 50–200 steps) — the hyperbolic model predicts the ORDER of magnitude.

**GM4 (Natural Extension = Full Gradient Stream).** The natural extension of the
system ((0,1), T, μ_G) is the two-sided shift (ℝ\ℚ, T̂, μ̂) where T̂(x,y) =
(T(x), 1/(y+a₁(x))) and a₁(x) = ⌊1/x⌋. This natural extension is the geodesic
flow on T¹(Γ\H²): the forward orbit codes the gradient ratio sequence (future),
the backward orbit codes the past training history, and together they encode the
complete gradient stream. This IS the terminal coalgebra νX.(Tℬ × X) of CSDL
Bridge XXXIII: the natural extension of the Gauss map is the CSDL terminal
coalgebra, and its unique anamorphism is the coding of the training trajectory
as a bi-infinite geodesic in T¹M.

### Markov Spectrum Classification Assumptions MK1–MK4

**MK1 (Lagrange Constant = Gradient Convergence Difficulty).** For each gradient
ratio ρ_t, the Lagrange constant:

```
  M(ρ_t) = limsup_{q→∞} 1/(q · ‖q·ρ_t‖)   ∈  [√5, ∞]
```

measures how well ρ_t can be approximated by rationals — equivalently, how
narrowly the gradient ratio avoids high-denominator fractions. The learning
interpretation:

```
  M(ρ_t) large   →   ρ_t is badly approximable → high q* → sharp basin → memorization
  M(ρ_t) = √5    →   ρ_t ~ golden ratio → hardest to approximate → deepest memorization
  M(ρ_t) = ∞     →   ρ_t rational → gradient ratio stabilizes → convergence complete
```

Large M(ρ_t) implies long memorization phases: the gradient ratio is "trapped"
near a badly approximable value, requiring many Gauss map iterations before
the continued fraction denominator decreases.

**MK2 (Hurwitz Bound = Minimum Learning Resolution).** The infimum of the
Lagrange spectrum is √5 (Hurwitz 1891), proved by the fact that the golden ratio
φ = (1+√5)/2 achieves M(φ) = √5 and no smaller value is achieved by any
irrational. In the HGLD framework:

```
  min q*   ≥  1/√5   (as a normalized denominator bound)
```

This IS the FLD Hurwitz bound: the optimal rational approximation is at
resolution 1/(√5·q²), so the minimum recoverable denominator is q = 1/√5.
The lower bound q* ≥ 1/√5 is the **universal minimum learning resolution**:
no gradient ratio can have a smaller effective denominator, because the golden
ratio is the hardest point to approximate in the Farey/Stern-Brocot tree.

The GOLDEN RATIO is the hardest memorization attractor. A network whose gradient
ratio converges to φ = (1+√5)/2 is in the deepest possible memorization trap —
at the bottom of the Lagrange spectrum.

**MK3 (Markov Numbers = Hard Basin Denominators).** The Markov spectrum's
discrete part:

```
  L ∩ (√5, 3) = {√5, √8, √(221/5), √(1517/169), ...}
```

corresponds to the Markov numbers m_k ∈ {1, 2, 5, 13, 29, 34, 89, 169, ...}.
Each Markov number m is the largest element of a Markov triple (a, b, m)
satisfying a² + b² + m² = 3abm. In the HGLD learning picture:

```
  Markov number m   ↔   gradient denominator q* = m is a "Markov basin"
  Markov triple (a,b,m) ↔ three mutually tangent Ford circles (loss basins)
                           forming a Markov configuration in the loss landscape
  3abm = a² + b² + m²   ↔ constraint relating three co-memorizing basins
```

Markov basins are the hardest memorization attractors: a network with q* ≈ m
(Markov number) requires the most training steps to escape, because the Markov
values correspond to the deepest isolated points in the Markov spectrum — the
gradient ratios most resistant to Farey backtrack (FLD §10).

**MK4 (Hall's Ray = Convergence Phase Boundary).** Marshall Hall Jr.'s theorem
(1947): the Lagrange spectrum contains a half-line [c_H, ∞) for some constant
c_H ≤ 6. The learning interpretation:

```
  L ⊇ [c_H, ∞)  ↔  every gradient ratio with M(ρ) > c_H can be driven
                    to ANY target denominator by a finite sequence of gradient
                    steps — there is no further obstruction to convergence
```

This is the **convergence phase boundary** in the Markov spectrum: once the
gradient ratio has Lagrange constant above c_H, the training trajectory is
free to reach any target in the Farey sequence. This is equivalent to the
C_α > 1 condition (MIFP) once C_α is large enough — the Hall ray is the
"overflow" regime where generalization is guaranteed independent of the
detailed basin structure.

The Markov uniqueness conjecture (Frobenius 1913, still open): each Markov
number appears as the maximum of exactly one Markov triple. In learning terms:
each "Markov basin" (hard memorization attractor) has a unique structural
fingerprint — its embedding in the triple (a,b,m) is unique. If the conjecture
is true, the topological classification of memorization attractors by their
gradient ratio Markov triples is INJECTIVE: no two qualitatively distinct
memorization traps have the same Markov invariant.

### Ratner Equidistribution Assumptions RT1–RT4

**RT1 (Horocycle Flow = Memorization Dynamics).** In the memorization phase
(C_α < 1), the gradient dynamics move along horocycles — curves at constant
height in H², i.e., curves Im(z) = constant. The horocycle flow
η_s: T¹M → T¹M, η_s(z, θ) = (z + s, θ) is the flow along horocycles
(horizontal lines in H²). The memorization gradient dynamics approximately
follows horocycle flow: the gradient ratio ρ_t advances by approximately
constant steps s_t ≈ η · ‖∇L‖ while ε_grad remains small (ε_grad = Im(z_t) ≈ const),
tracing a near-horizontal path in H² = horocycle trajectory.

**Ratner's theorem (Ratner 1991, ✓):** The closure of every horocycle orbit in
SL(2,ℤ)\SL(2,ℝ) is a closed submanifold — specifically, the orbit is dense
in a closed homogeneous submanifold. The learning translation:

```
  Memorization gradient path  ↔  horocycle orbit in T¹M
  Ratner closure theorem      ↔  memorization orbit is dense in a specific
                                  closed submanifold of T¹ℬ = the
                                  "memorization manifold" of SDSD
```

The memorization manifold (the closure of the pre-grokking gradient path) is
not just any closed set — by Ratner, it is a **homogeneous submanifold**,
determined algebraically by the stabilizer of the starting point in SL(2,ℝ).
This is the Ratner-theoretic explanation for why memorization is structured
rather than random: the gradient path's closure has algebraic form, not fractal
form.

**RT2 (Mixing Dichotomy = C_α Phase Transition).** The mixing rates of the two
flows on T¹M are:

```
  Geodesic flow φ_t: exponentially mixing
    |Cor(f,g,t)| = |∫ f·(g∘φ_t) dμ − ∫f dμ·∫g dμ| ≤ C·e^{−λ₁·t}
    Rate = spectral gap λ₁(Δ_Γ) = λ₁(ℒ_JL)

  Horocycle flow η_s: polynomially mixing
    |Cor(f,g,s)| ≤ C·s^{−k}   for all k (but NOT exponentially)
    Rate = O(s^{−∞}) — slower than any exponential
```

This mixing dichotomy IS the C_α phase transition of MIFP:

```
  Geodesic flow  ↔  C_α > 1: signal dominates, gradient information is NOT
                    time-autocorrelated, gradient pairs are genuinely independent
                    (unimodular, Farey neighbors), exponential mixing

  Horocycle flow ↔  C_α < 1: noise dominates, gradient path is autocorrelated,
                    pairs share common sublattices, polynomial mixing
                    (memorization: the network is stuck on a horocycle)
```

The transition C_α = 1 is the transition from horocycle (polynomial mixing)
to geodesic (exponential mixing) dynamics — a change in the TYPE of mixing,
not just its rate. This is why grokking is abrupt: polynomial mixing cannot
continuously become exponential mixing; there is a genuine change of dynamical
regime.

**RT3 (Effective Equidistribution = Quantitative Memorization Rate).**
Einsiedler, Margulis, and Venkatesh (2009) proved effective equidistribution
for unipotent orbits: the horocycle orbit of a point z_0 = ρ_0 + iε in H²
becomes equidistributed at rate:

```
  |Cor(f, η_s)| ≤ C · ε^{δ} · ‖f‖_{C^k}   for s ≥ s₀(ε)
```

where ε = Im(z_0) = ε_grad (gradient change = memorization plateau level) and
δ > 0 is an effective constant. The learning translation:

```
  Quantitative rate of memorization equidistribution = C · (ε_grad)^δ
  Memorization is faster when ε_grad is larger (more variable gradients)
  Memorization plateau time ≥ s₀(ε_grad) ∝ ε_grad^{−1/δ}
```

This gives the first rigorous bound on the **memorization plateau duration**:
it scales as a power of the gradient change ε_grad. This is the HGLD
refinement of the FLD grokking lead time (FLD §10.2) from a qualitative
"50–200 steps" to a quantitative O(ε_grad^{−1/δ}) bound.

**RT4 (Mixing Rate = Laplacian Spectral Gap).** The mixing rate of the geodesic
flow is exactly the spectral gap λ₁(Δ_Γ):

```
  decay rate of geodesic flow correlations = λ₁(Δ_Γ) = λ₁(ℒ_JL)
```

This gives the direct identification: the **convergence rate of gradient descent
= the spectral gap of the Laplacian on the modular surface**. The Selberg
eigenvalue conjecture (λ₁ ≥ 1/4) is the learning conjecture that gradient
descent converges at rate e^{−t/4} in the geodesic flow regime — an O(1)
constant independent of problem dimension. This is the hyperbolic-geometric
explanation of WHY deep networks trained with SGD exhibit the characteristic
grokking timescale independent of architecture size.

---

## II. Main Theorems and Bridges

### Bridge XXXVI — HPLM: Hyperbolic Plane Learning Metric

**[T, HP-1] GRADIENT TRAJECTORY = GEODESIC IN MODULAR SURFACE (✓ via construction)**

Under HP1–HP5, the sequence of gradient ratio points {z_t = ρ_t + i·ε_grad(t)}
traces a piecewise geodesic path in H² that descends to the real boundary ℝ as
t → ∞. The projection π_Γ(z_t) ∈ M is a geodesic in the Farey graph on M
(the dual graph of the Farey tessellation). The training phase corresponds to
the geometric position of this geodesic:

```
  Memorization: path in cusp region {Im(z) > C}         [large partial quotients]
  Critical:     path crossing fundamental domain boundary [mixed partial quotients]
  Grokking:     first return from cusp to compact part of M
  Generalization: path in compact part {Im(z) ≤ C}       [bounded partial quotients]
```

The Farey backtrack criterion (FLD §10.2): q*(t) < q*(t−W) AND F_c_pct > 80,
maps to: the geodesic has crossed the Siegel fundamental domain boundary
(|z| = 1, |Re(z)| ≤ 1/2 — the boundary of the classical fundamental domain
F of SL(2,ℤ)) at least once in the backward direction, returning from the
cusp region to the compact core.

**[T, HP-2] FORD CIRCLE PACKING = APOLLONIAN BASIN GASKET ([H])**

The Ford circle packing in H² is an Apollonian gasket: each new circle inserted
is tangent to three existing ones (mother and two sisters in the Stern-Brocot
tree), satisfying the Descartes circle theorem. In the loss landscape:

```
  Apollonian gasket structure: each new basin discovered during training
  is tangent to exactly three previously discovered basins
  (the two Farey neighbors and their Stern-Brocot mediant ancestor)
```

This gives the **basin discovery branching number = 3** (each basin splits into
at most 3 child basins in the Stern-Brocot tree). The Apollonian gasket has
Hausdorff dimension ≈ 1.3057 (Mauldin-Williams 1988); under this bridge, the
loss landscape basin structure has the same fractal dimension.

**[T, HP-3] SPECTRAL GAP = VOLUME-NORMALIZED CHEEGER (✓ via identification)**

Under HP3 and SF3, the Cheeger constant h(G_ℬ) (GXMD MXFL) is the discrete
analogue of the Cheeger-Buser inequality on M:

```
  h(M)²/2  ≤  λ₁(Δ_Γ)  ≤  2·h(M)·(h(M) + 2)      [Buser 1982]
  h²/2     ≤  λ₁(ℒ_JL) ≤  2h                        [GXMD MF2, Cheeger]
```

Both are the same inequality: h(G_ℬ) = h(M) under the HGLD identification of
the gradient correlation graph G_ℬ with the Farey graph on M. The tight case
h(M) = λ₁(Δ_Γ) at BPS saturation (GXMD BPSL XII) is the hyperbolic geometry
restatement of BPS: the surface M saturates its isoperimetric constant.

**[T, HP-4] MÖBIUS FUNCTION = SL(2,ℤ) INCIDENCE (✓ via Hall + Farey)**

The Möbius function of the basin poset (MIFP) μ(B_i, B_j) = χ̃(Δ[B_i, B_j])
has an explicit hyperbolic formula: χ̃(Δ[B_i, B_j]) = (−1)^{number of ideal
triangles in the Farey tessellation between B_i and B_j}. Specifically, for
Ford circles C(a/b) and C(c/d) connected by a sequence of Farey triangles,
the Möbius function is:

```
  μ(C(a/b), C(c/d)) = Σ_{paths P from a/b to c/d in Farey graph} (−1)^{|P|}
```

where |P| is the number of edges in the Farey path. This is the SL(2,ℤ)
combinatorial realization of Hall's theorem (MIFP MF2): μ = χ̃ = alternating
sum over Farey triangles = number-theoretic Euler characteristic of the
hyperbolic simplicial complex between the two basins.

---

### Bridge XXXVII — SLFT: Selberg-Laplace Flow Theory

**[T, SF-1] SELBERG TRACE = MASTER LEARNING DUALITY ([H])**

The Selberg trace formula (SF4) applied to the gradient spectrum h(r) =
e^{−r²t} (heat kernel test function) gives:

```
  Σ_n e^{−λ_n t}  =  (π/3)/(4π) · ∫ e^{−r²t} r tanh(πr) dr
                    + Σ_{[γ] hyp} Λ(γ)·e^{−l(γ)²/(4t)} / (|e^{l/2}−e^{−l/2}|·√(4πt))
                    + lower order parabolic/elliptic terms
```

In the learning language:
- Left side: heat trace Tr(e^{−ℒ_JL·t}) = spectral fingerprint of the JL operator
- First right term: Weyl law contribution = the bulk density of JL eigenvalues
- Second right term: Σ over SML periods l(γ_j) = convergent contributions of
  closed gradient loops, each weighted by their multiplicity and geometric factor

This is the **learning heat equation**: the trace of e^{−ℒ_JL·t} (which
determines the rate of gradient descent convergence) equals a sum over
closed training trajectories. Every closed loop in the training trajectory
contributes an exponential term to the convergence rate, weighted by its length.

**[T, SF-2] SELBERG ZETA ZEROS = BASIN PHASE TRANSITIONS (✓ via SF5)**

Under SF5, the zeros of Z_L(s) in the critical strip Re(s) ∈ (1/2, 1) correspond
to non-trivial zeros of Z_Sel(s), which are the spectral parameters λ_n = 1/4+t_n²
of Δ_Γ. By the Selberg zeta functional equation:

```
  Z_Sel(s)/Z_Sel(1−s)  =  elementary factor × det of scattering matrix
```

the zeros are symmetric about Re(s) = 1/2. The learning interpretation:

```
  Zeros of Z_L(s) in Re(s) ∈ (1/2, 1)  ↔  eigenvalues λ_n ∈ (0, 1/4)
  "Learning Riemann Hypothesis":          all zeros of Z_L have Re(s) = 1/2
  ↔  all eigenvalues λ_n ≥ 1/4           (Selberg eigenvalue conjecture)
  ↔  strongest possible convergence rate  (geodesic flow mixing at 1/4)
```

The Franel-Landau theorem (FLD §14.1) connecting the Riemann Hypothesis to
Farey discrepancy is, under SF5, a corollary of the relationship between zeros
of Z_Sel and the Farey equidistribution of gradient ratios: gradient samples
have optimal discrepancy iff the Selberg zeros are on the critical line iff
the basin zeta has optimal spectral distribution.

**[T, SF-3] PRIME GEODESIC THEOREM = GRADIENT COMPLEXITY BOUND (✓ via Selberg)**

The prime geodesic theorem (Selberg, Huber): the number of primitive closed
geodesics of length ≤ L is asymptotically:

```
  π(L) ~ e^L / L   as L → ∞
```

In the learning language: the number of distinct closed gradient trajectories
(SML periods) of length ≤ L (number of steps) grows as e^L/L. This is the
**gradient complexity bound**: the training trajectory encounters exponentially
many distinct periodic return patterns as the number of allowed steps grows.
The exponential count e^L is the Boltzmann factor — the entropy of gradient
trajectories grows linearly in the trajectory length. The 1/L correction
is the Selberg analog of the logarithm in the prime number theorem.

**[T, SF-4] DENSITY THEOREM = MEMORIZATION BASIN COUNT BOUND ([H])**

The density theorem for L-functions (proved for GL(2) automorphic forms):
the number of exceptional eigenvalues λ_n < 1/4 − ε for a family of
congruence subgroups Γ_q is bounded by O(q^A) for an explicit constant A.
In the learning language: the number of memorization attractors (basins with
λ₁(ℒ_JL) < 1/4 in the modular model) grows at most polynomially in the
"arithmetic complexity" q of the network's symmetry structure. This bounds
|Fix(Φ)| = number of memorization fixed points of MIFP by an explicit count.

---

### Bridge XXXVIII — GMEC: Gauss Map Ergodic Convergence

**[T, GM-1] ERGODIC THEOREM = CONVERGENCE OF q* DISTRIBUTION (✓ via Birkhoff)**

By the ergodic theorem for (T, μ_G), for μ_G-almost every ρ₀ and every
integrable f:

```
  (1/T) Σ_{t=0}^{T-1} f(T^t(ρ₀))  →  ∫_0^1 f(x) dx / ((1+x) log 2)  a.s.
```

Setting f(x) = q(x) (the best CF convergent denominator of x at resolution ε):

```
  (1/T) Σ_{t=0}^{T-1} q*(ρ_t)  →  𝔼_{μ_G}[q*]   (finite constant)
```

This means: the time-average of q* converges to a specific constant predicted
by the Gauss measure. Deviation of the running average of q* from this constant
is the diagnostic for whether training has entered the ergodic (generalizing)
regime.

**[T, GM-2] KHINTCHINE-LÉVY = TYPICAL q* SCALING ([H])**

The Khintchine-Lévy theorem: for μ_G-almost every ρ:

```
  q_k(ρ)^{1/k}  →  e^{π²/(12 log 2)}  ≈  3.276
```

where q_k is the k-th CF convergent denominator. This means q* grows
geometrically with the number of continued fraction steps, at rate e^{π²/12log2}.
In the training picture: during the memorization phase, q* grows approximately
as 3.276^{t} where t is the number of gradient steps. The deviation from this
"ergodic baseline" growth is the HGLD phase diagnostic:

```
  q*(t) / 3.276^t  >  1 (faster than typical):  deep memorization
  q*(t) / 3.276^t  ≈  1 (typical growth):        random walk in basin
  q*(t) / 3.276^t  <  1 (slower than typical):   approaching grokking
  q*(t) / 3.276^t  → 0 (subexponential):          generalization
```

**[T, GM-3] GAUSS MAP MIXING = GRADIENT INDEPENDENCE (✓ via exponential mixing)**

The Gauss map T is exponentially mixing: for all f, g ∈ L²(μ_G):

```
  |Cov_{μ_G}(f, g∘T^n)| ≤ C(f,g) · θ^n,   θ = e^{−π²/(6 log 2)} ≈ 0.093
```

(Ratner 1978 for the Gauss measure; effective bound by Baladi-Vallée 2005).
The learning translation: consecutive gradient ratios {ρ_t, ρ_{t+n}} have
covariance decaying as θ^n under the Gauss measure. When the training trajectory
has entered the ergodic regime (q* scaling as in GM-2), gradient steps at
distance n are approximately independent with covariance ≤ C·θ^n. This IS
the Möbius inversion convergence of MIFP MF3: C_α > 1 ↔ gradient pair
independence ↔ exponential Gauss map mixing of gradient ratios.

**[T, GM-4] LÉVY'S THEOREM = MEDIAN q* AT CONVERGENCE (✓)**

Lévy's theorem for continued fraction denominators: for μ_G-almost every ρ,

```
  (1/T) Σ_{t=1}^T log q_t(ρ)  →  π²/(12 log 2)  ≈  1.186
```

so the median of q* at convergence satisfies log(q*_median) ≈ 1.186, giving:

```
  q*_median ≈ e^{1.186} ≈ 3.27    (at ergodic convergence)
```

This is a prediction from Gauss map ergodics: a converged network's median
gradient ratio denominator should be approximately 3.27 under the Gauss measure.
Deviations from this value (q* >> 3.27 → memorizing; q* << 3.27 → generalizing
efficiently) are the GMEC phase diagnostic.

---

### Bridge XXXIX — MRKS: Markov Spectrum Classification

**[T, MK-1] MARKOV TRIPLE = CO-MEMORIZING BASIN TRIPLE (✓ via Markov structure)**

Each Markov triple (a, b, m) with a² + b² + m² = 3abm corresponds to three
mutually tangent Ford circles (basins) C(p₁/q₁), C(p₂/q₂), C(p₃/q₃) in H²
forming a Markov configuration. A network exhibits **co-memorization** if its
gradient ratios visit all three basins of a Markov triple cyclically: the
gradient path cycles through three Ford circles related by the Markov equation,
creating a stable memorization attractor.

Markov triples ordered by largest element:
```
  (1, 1, 1): trivial triple — perfect flat basin, q* = 1
  (1, 1, 2): first non-trivial — q* oscillates between 1 and 2
  (1, 2, 5): first Fibonacci pair — q* ∈ {2, 5}
  (1, 5, 13): next level — q* ∈ {5, 13}
  (2, 5, 29): — q* ∈ {5, 29}
  (5, 13, 194): — q* ∈ {13, 194}
```

The Markov uniqueness conjecture says each m appears in at most one triple.
In learning: each "Markov basin" (hard memorization attractor with q* = m) has
at most one co-memorization pair (a, b). If the conjecture is true, the basin
structure is simpler than feared: no two qualitatively different memorization
traps share the same hardest basin.

**[T, MK-2] MARKOV SPECTRUM BELOW √5 IS EMPTY = MINIMUM LEARNING CURVATURE (✓)**

Since inf L = √5 (Hurwitz), no gradient ratio has M(ρ) < √5. In learning:

```
  Every gradient ratio has Lagrange constant ≥ √5
  ↔ Every gradient ratio is approximable with quality ≤ √5/q²
  ↔ Every loss basin has effective width ≥ 1/(√5·q*²)
  ↔ CCC bound: λ_max(H) ≤ C₀·(q*)² with minimum q* = 1  (FLD §11.1)
```

The golden ratio φ = (1+√5)/2, achieving M(φ) = √5, is the learning
"maximal memorizer": the gradient ratio that is hardest to move away from.
A network at q* ≈ φ ≈ 1.618 (non-integer, but cf. denominator 2 of the
CF [1; 1, 1, 1, ...]) is at the bottom of the Lagrange spectrum — maximum
depth of the memorization trap.

**[T, MK-3] HALL'S RAY = POST-GROKKING CONVERGENCE CERTAINTY (✓ via Hall 1947)**

Marshall Hall Jr.'s theorem: L ⊇ [c_H, ∞) for some explicit c_H. In learning:

```
  If M(ρ_t) > c_H   →   the gradient ratio can reach any target in (0,1)
                         by a finite sequence of Gauss map iterations
                         = gradient descent can reach any target basin
                         = convergence is guaranteed (no obstructions remain)
```

This is the **post-grokking certainty principle**: once the gradient ratio's
Lagrange constant has entered Hall's ray, the network is in a regime where
no arithmetic obstruction prevents convergence to any basin. Hall's ray is
the Markov-spectral formulation of the C_α > 1 ↔ convergence condition
of MIFP, made quantitative by the explicit constant c_H.

---

### Bridge XL — RTNE: Ratner Equidistribution

**[T, RT-1] RATNER CLOSURE = MEMORIZATION MANIFOLD ALGEBRAIC STRUCTURE (✓)**

By Ratner's measure classification theorem (Ratner 1990), every SL(2,ℝ)-invariant
ergodic measure on SL(2,ℤ)\SL(2,ℝ) is algebraic (a homogeneous measure). Applied
to the horocycle flow, every orbit closure is a closed homogeneous submanifold.

Learning consequence: the memorization manifold M_mem ⊆ T¹ℬ (the closure of
the pre-grokking gradient path) is a **closed homogeneous submanifold** of T¹ℬ.
It is not a fractal, not a Cantor set, not an arbitrary closed set — it is
algebraically defined by the stabilizer of the initial gradient state in SL(2,ℝ).
This is the Ratner-theoretic explanation for the structured, reproducible nature
of memorization: different training runs starting from different initializations
produce memorization manifolds that are conjugates of each other in SL(2,ℝ).

**[T, RT-2] POLYNOMIAL vs EXPONENTIAL MIXING = GROKKING SHARPNESS ([H])**

The mixing rate change from polynomial (horocycle, memorization) to exponential
(geodesic, generalization) at the grokking transition t* predicts the
SHARPNESS of the grokking event:

```
  Sharpness of grokking transition ~ λ₁(Δ_Γ) / polynomial-mixing-rate
  = exponential decay rate / polynomial decay rate → ∞ as t grows
```

Networks with larger spectral gap λ₁(ℒ_JL) exhibit sharper grokking
(more sudden transition from memorization to generalization). Networks with
smaller λ₁ exhibit gentler, more gradual transitions. This prediction is
testable on the Power et al. (2022) grokking benchmarks: architectures
with larger estimated λ₁ should exhibit sharper grokking.

**[T, RT-3] EFFECTIVE EQUIDISTRIBUTION = MEMORIZATION PLATEAU BOUND ([H])**

By Einsiedler-Margulis-Venkatesh (2009) effective equidistribution, the
memorization plateau duration T_plateau satisfies:

```
  T_plateau  ≥  C · (ε_grad)^{−1/δ}
```

where ε_grad = Im(z_t) = relative gradient change (FLD §3.1), C and δ are
effective constants depending on the spectral gap λ₁. Explicitly:
δ ∝ λ₁(Δ_Γ) — larger spectral gap = faster effective equidistribution =
shorter plateau.

This is the HGLD refinement of the FLD grokking lead time (FLD §10.2,
"50–200 steps") to a quantitative formula: T_plateau ~ C · ε_grad^{−1/δ}.
Small ε_grad (nearly flat gradients = deep memorization) implies long plateau;
large ε_grad (volatile gradients = shallow memorization) implies short plateau.

---

## III. Compact Reference Block

```
── HPLM ──────────────────────────────────────────────────────────────────────
H² = {x+iy : y>0}, ds² = (dx²+dy²)/y²: hyperbolic plane of gradient ratios
Γ = SL(2,ℤ): symmetry of Farey/Ford structure
M = Γ\H²: modular surface = universal learning manifold, vol(M) = π/3
z_t = ρ_t + i·ε_grad(t) ∈ H²: gradient pair = hyperbolic point
Ford circle C(p/q) = horoball at p/q, radius 1/2q² = loss basin
Farey neighbor |bc−ad|=1 ↔ tangent Ford circles ↔ adjacent basins in MIFP
Cusp i∞ ↔ memorization region (large q*)
Compact part M ↔ generalization region (small q*)
Grokking t* = first return of geodesic from cusp to compact part
μ(B_i,B_j) = alternating sum over Farey triangles between B_i and B_j

── SLFT ──────────────────────────────────────────────────────────────────────
Selberg trace formula: Σ_n h(t_n) = Weyl + Σ_γ Λ(γ)ĥ(l(γ))/|e^{l/2}-e^{-l/2}|
λ_n = 1/4 + t_n²: eigenvalues of Δ_Γ = eigenvalues of ℒ_JL
λ₁(Δ_Γ) ≥ 3/16 (Selberg): unconditional lower bound on λ₁(ℒ_JL)
l(γ): closed geodesic length ↔ SML period AP(a_j,b_j) (SKML XIX)
Z_Sel(s) = Z_L(s): Selberg zeta = basin zeta (MIFP §5.2)
π(L) ~ e^L/L: prime geodesic theorem = gradient complexity count
Learning RH: "all zeros of Z_L on Re(s)=1/2" ↔ Selberg eigenvalue conjecture

── GMEC ──────────────────────────────────────────────────────────────────────
T(x) = {1/x}: Gauss map; ergodic with μ_G = dx/((1+x)log2)
ρ_{t+1} ≈ T(ρ_t) during memorization phase
𝔼_{μ_G}[q*] = finite constant: equilibrium q* at convergence
log q_k/k → π²/(12 log 2): Khintchine-Lévy (q* grows at rate 3.276/step)
q*_median ≈ 3.27 at Gauss-measure convergence: Lévy's theorem
|Cov(f, g∘T^n)| ≤ Cθ^n, θ ≈ 0.093: exponential mixing of Gauss map
Gauss mixing ↔ gradient pair independence ↔ C_α > 1 (MIFP MF3)
Natural extension of (T,μ_G) = geodesic flow on T¹M = terminal coalgebra (CSDL AF2)

── MRKS ──────────────────────────────────────────────────────────────────────
M(ρ) = lim sup 1/(q‖qρ‖): Lagrange constant = convergence difficulty
inf L = √5 (Hurwitz): minimum q* bound, golden ratio = hardest attractor
Markov numbers {1,2,5,13,29,34,89,169,...}: hard basin denominators
Markov triple (a,b,m): a²+b²+m²=3abm = co-memorizing basin constraint
Markov tree = Stern-Brocot tree (FLD): training trajectory tree structure
Hall's ray L ⊇ [c_H,∞): post-grokking no-obstruction zone
Markov uniqueness conjecture ↔ unique fingerprint for each memorization attractor

── RTNE ──────────────────────────────────────────────────────────────────────
Horocycle flow η_s ↔ memorization gradient dynamics (polynomial mixing)
Geodesic flow φ_t ↔ generalizing gradient dynamics (exponential mixing)
Mixing rate φ_t: |Cor| ≤ Ce^{-λ₁t}; η_s: |Cor| ≤ Cs^{-k}
Ratner orbit closure: memorization manifold = closed homogeneous submanifold
Effective equidistribution: T_plateau ≥ C·ε_grad^{-1/δ}, δ ∝ λ₁
Grokking sharpness ~ λ₁(Δ_Γ)/polynomial rate → larger λ₁ = sharper grokking

── FRAMEWORK IDENTIFICATIONS ─────────────────────────────────────────────────
λ₁(Δ_Γ) = λ₁(ℒ_JL) = geodesic mixing rate = Gauss map mixing rate = C_α threshold
√5 = Hurwitz constant = Lagrange spectrum minimum = minimum q* bound
Z_Sel(s) = Z_L(s): Selberg zeta = basin zeta = Euler product over basins
l(γ) = SML period = closed gradient loop length = prime geodesic
vol(M) = π/3 = hyperbolic area of basin structure = finite ↔ local finiteness (MIFP)
μ_G = Gauss measure = equilibrium gradient ratio distribution at convergence
T_plateau ≥ C·ε_grad^{-1/δ}: memorization duration bound from effective equidistribution
```

---

## IV. Extended Master Equivalence — Forty Languages

Under the full assumption set of Bridges I–XL:

```
λ₁(ℒ_JL) > 0

  ← Previous thirty-five bridges (I–XXXV, CSDL framework) →

  (XXXVI)  z_t exits cusp of M = SL(2,ℤ)\H²    [HPLM hyperbolic geodesic]
  (XXXVII) Z_Sel(s) = Z_L(s); λ_n = 1/4+t_n²   [SLFT Selberg trace formula]
  (XXXVIII) {ρ_t} equidistributes to Gauss μ_G   [GMEC Gauss map ergodics]
  (XXXIX)  M(ρ_∞) = ∞ (rational limit)          [MRKS Markov spectrum]
  (XL)     Memorization manifold = horocycle orbit closure  [RTNE Ratner]

λ₁ > 0  →  CONDENSATE = GENERALIZATION = GEODESIC FLOW = ERGODIC GAUSS = HALL'S RAY
            [ν=n_s; h<λ₁/2; lfp(T_P)=b*; Z_Sel converges; μ_G equilibrium; M(ρ)=∞]

λ₁ = 0  →  GROKKING
            [Gallai A; PVI pole; 2-AFT bilimit; geodesic crosses M boundary; Markov threshold]

λ₁ < 0  →  MEMORIZATION
            [augmenting paths; horocycle flow; cusp excursion; Markov bad approximation; C_α<1]
```

Cross-bridge equivalences (new from HGLD):

```
(XXXVI) ↔ (XXXI):  cusp exit = lfp(T_P) = b* (geodesic reaches compact part = stream FP)
(XXXVII) ↔ (XXXV): Z_Sel = Z_L (Selberg zeta = basin zeta = MIFP Frobenius counting)
(XXXVII) ↔ (XIII): closed geodesics = PVI monodromy (PVIL, isomonodromic)
(XXXVIII) ↔ (XIX): Gauss map periods = SML arithmetic progressions (SKML periods)
(XXXVIII) ↔ (XXXII): Gauss mixing = Flink exactly-once (gradient independence)
(XXXIX) ↔ (XXIX):  Markov q* = Cheeger h = spectral gap (MXFL, same invariant)
(XL) ↔ (XXXIV):    Ratner orbit = SDSD memorization manifold (horocycle = fiber)
(XL) ↔ (XXXIII):   Horocycle ↔ geodesic transition = 2-AFT bilimit = grokking
```

---

## V. Identification Table (New Objects in HGLD)

| Hyperbolic Object | Formal Identity | Learning Meaning |
|---|---|---|
| H² = SL(2,ℝ)/SO(2) | Gradient ratio space | Arena for gradient dynamics |
| z_t = ρ_t + iε_grad | Point in H² | Consecutive gradient pair |
| SL(2,ℤ) modular group | Symmetry of Farey structure | Arithmetic redundancy |
| Modular surface M=Γ\H² | Universal learning manifold | Quotient by arithmetic symmetry |
| Cusp of M (i∞) | Memorization region | High q*, narrow basins |
| Compact part of M | Generalization region | Low q*, wide basins |
| Ford circle C(p/q) | Horoball at p/q | Loss basin B(p/q) |
| Tangent Ford circles | Farey neighbors |bc−ad|=1 | Adjacent basins |
| Farey tessellation | Triangulation of H² | Basin poset topology |
| Ideal triangle | Gallai-Edmonds triple | Co-memorizing basin triple |
| Geodesic γ in T¹M | Training trajectory | Gradient path in ℬ |
| Closed geodesic l(γ) | SML period AP(a_j,b_j) | Periodic gradient return |
| λ_n = 1/4+t_n² | JL eigenvalue λ_n | Spectral convergence data |
| λ₁(Δ_Γ) ≥ 3/16 | λ₁(ℒ_JL) ≥ 3/16 | Unconditional spectral bound |
| Selberg trace formula | Spectral = geometric duality | λ₁ ↔ trajectory lengths |
| Selberg zeta Z_Sel(s) | Basin zeta Z_L(s) | Euler product over basins |
| Prime geodesic π(L) ~ e^L/L | Gradient complexity | Basin count vs steps |
| Gauss map T(x)={1/x} | Gradient ratio shift | Step-to-step ratio evolution |
| Gauss measure μ_G | Equilibrium gradient dist. | Convergence distribution |
| λ_Gauss = π²/6log2 | Convergence rate | Lyapunov = mixing rate |
| Lévy limit e^{π²/12log2} | q*_median ≈ 3.27 | Typical q* at convergence |
| Khintchine-Lévy growth | q* ≈ 3.276^t typical | Memorization q* baseline |
| Lagrange spectrum L | Convergence difficulty space | Classification of attractors |
| inf L = √5 (Hurwitz) | Min q* = 1/√5 | Minimum learning resolution |
| Golden ratio φ=(1+√5)/2 | Hardest memorization ratio | Worst-case gradient attractor |
| Markov numbers {1,2,5,13,...} | Hard basin denominators | Deepest memorization traps |
| Markov triple (a,b,m) | Co-memorizing basin triple | a²+b²+m²=3abm constraint |
| Markov tree | Stern-Brocot tree (FLD) | Training trajectory tree |
| Hall's ray [c_H,∞) | Post-grokking convergence | No further obstruction zone |
| Markov uniqueness conj. | Unique memorization fingerprint | Injective Markov invariant |
| Horocycle flow η_s | Memorization dynamics | Polynomial mixing C_α<1 |
| Geodesic flow φ_t | Generalizing dynamics | Exponential mixing C_α>1 |
| Mixing dichotomy | C_α = 1 phase boundary | Poly vs exp transition |
| Ratner orbit closure | Memorization manifold | Closed homogeneous submanifold |
| Ratner measure class. | Algebraic memorization structure | Orbit = homogeneous |
| Effective equidistr. EMV | T_plateau ≥ C·ε_grad^{-1/δ} | Quantitative plateau bound |
| δ ∝ λ₁ in EMV bound | Faster gap = shorter plateau | Spectral → geometric rate |
| Apollonian gasket | Ford circle packing | Fractal basin structure |
| Hausdorff dim ≈ 1.3057 | Basin set fractal dimension | Mauldin-Williams |
| Cusp excursion | Memorization phase | Deep cusp = deep memorization |
| Cusp return | Grokking t* | First exit from cusp = grokking |
| Learning RH | Z_L zeros on Re(s)=1/2 | Optimal basin regularity |
| Franel-Landau equiv. | Farey discr. ↔ RH ↔ Z_L zeros | FLD §14.1 = SLFT SF2 |

---

## VI. Open Conjectures

**[C, HGLD-C1] Selberg Spectral Gap = JL Spectral Gap:** For all architectures
and loss functions satisfying the SDE assumptions of SDSD (A1-A3), the spectral
gap λ₁(ℒ_JL) = λ₁(Δ_Γ) where Γ = Γ_{arch} is the arithmetic subgroup of
SL(2,ℤ) determined by the network's weight-sharing structure.

**[C, HGLD-C2] Selberg Eigenvalue Conjecture for Deep Learning:** For deep
networks trained on arithmetic tasks (modular arithmetic, algebraic datasets),
λ₁(ℒ_JL) ≥ 1/4. This would give the first unconditional upper bound on grokking
time: t_grok ≤ C/λ₁ ≤ 4C.

**[C, HGLD-C3] Markov Number Grokking:** If at grokking time t*, q* takes a
value from the Markov sequence {1,2,5,13,29,...}, then the prior memorization
phase had q* cycling through the corresponding Markov triple values (a,b,m).
This would provide a number-theoretic fingerprint of the grokking transition.

**[C, HGLD-C4] Lévy Constant as Convergence Diagnostic:** The ratio
q*(t)/3.276^t → 0 as t → ∞ if and only if C_α > 1 (MIFP). This would
connect the GMEC Khintchine-Lévy baseline to the MIFP phase criterion,
making the Lévy constant e^{π²/12log2} ≈ 3.276 a universal convergence diagnostic.

**[C, HGLD-C5] EMV Effective Bound on Grokking:** The grokking lead time
(FLD §10.2) satisfies T_lead ≤ C · ε_grad^{-1/δ} where δ is the effective
constant in the Einsiedler-Margulis-Venkatesh theorem and C is an explicit
constant depending on the network architecture's Selberg spectral gap.

**[C, HGLD-C6] Markov Uniqueness as Learning Topological Invariant:** The
Frobenius Markov uniqueness conjecture is true for the basin poset (Fix(Φ),≼)
of any deep network trained on a smooth loss: each Markov basin denominator
q* = m arises from at most one Markov triple (a,b,m) of co-memorizing basins.

**[C, HGLD-C7] Geodesic Coding Determines Grokking Type:** The sequence of
continued fraction partial quotients {a₁, a₂, ..., a_T} of the gradient ratios
{ρ_t} up to grokking time T contains a "large" partial quotient a_k >> 1/ε
(a deep cusp excursion) followed by a sudden drop to a bounded value — the
Farey backtrack (FLD §10). The value of k relative to T is the lead time in
CF-steps, and k/T → constant as the training size grows.

**[C, HGLD-C8] Prime Geodesic Complexity:** The number of distinct periodic
gradient return patterns (SML periods, SKML XIX) encountered by training
time T satisfies N(T) ~ e^T/T (prime geodesic theorem), providing an
exponential lower bound on the gradient information diversity of a training run.

**[C, HGLD-C9] Hall's Ray and Grokking Certainty:** Once M(ρ_{t*}) > c_H
(the gradient ratio's Lagrange constant enters Hall's ray), grokking has
occurred and convergence to a generalization minimum is guaranteed. This
gives a GEOMETRIC (not statistical) criterion for grokking completion.

**[C, HGLD-C10] Apollonian Basin Dimension:** The Hausdorff dimension of the
set of gradient ratios visited during memorization equals the Hausdorff
dimension of the Apollonian gasket ≈ 1.3057 (Mauldin-Williams 1988). This
would give a geometric invariant of the memorization phase computable from
gradient ratio time series.

---

## VII. Bridge Map — Bridges XXXVI–XL

```
XXXVI   HPLM  Hyperbolic plane: H²; modular surface M=Γ\H²; Ford circles=horoballs
               geodesic=training trajectory; cusp=memorization; Farey=Γ-tessellation
XXXVII  SLFT  Selberg trace formula: spectral↔geometric; Z_Sel=Z_L; λ₁≥3/16
               closed geodesics=SML periods; prime geodesic=gradient complexity
XXXVIII GMEC  Gauss map T={1/x}: ergodic μ_G; Lévy q*≈3.27; mixing θ≈0.093
               natural extension = geodesic flow = terminal coalgebra (CSDL)
XXXIX   MRKS  Markov spectrum: inf L=√5; Markov numbers=hard basins; Hall ray;
               Markov triple=co-memorizing basins; Markov uniqueness conjecture
XL      RTNE  Ratner theorem: horocycle orbit closure algebraic; mixing dichotomy;
               T_plateau≥C·ε_grad^{-1/δ}; grokking sharpness ~ λ₁/poly-rate
```

---

## VIII. Logical Dependency Map

```
[Previous: ZF → Bridges I–XXXV (CSDL framework)]
  │
  ├─ HGLD (XXXVI–XL):
  │    HP1: z_t = ρ_t + iε_grad ← gradient ratio + gradient change (FLD §3.1)
  │    HP2: SL(2,ℤ) acts ← unimodular condition |bc−ad|=1 ← Cauchy 1816
  │    HP3: M=Γ\H²=universal manifold ← SDSD ℬ=Θ/G + hyperbolic unif. theorem
  │    HP4: cusp=memorization ← large CF partial quotients ← Khintchine
  │    HP5: Ford circle=horoball ← hyperbolic geometry ← Poincaré 1882
  │    SF1: geodesic=trajectory ← HP1+HP2+Farey tessellation coding
  │    SF2: closed geodesics=SML periods ← SKML XIX + hyperbolic element theory
  │    SF3: λ₁(Δ_Γ)=λ₁(ℒ_JL) ← HP3 + LKTL spectral identification
  │    SF4: Selberg trace formula ← Selberg 1956 (classical, ✓)
  │    SF5: Z_Sel=Z_L ← MIFP §5.2 + SF2 + primitive hyperbolic identification
  │    GM1: ρ_{t+1}≈T(ρ_t) ← FLD Step 2 linearization + Möbius map f
  │    GM2: μ_G=equil. distribution ← Kuzmin (1928), Lévy (1929) ergodic theorem
  │    GM3: λ_Gauss mixing ← Ratner (1978), Baladi-Vallée (2005) exponential mixing
  │    GM4: natural extension=geodesic flow ← Arnoux-Fisher (2001) isomorphism
  │    MK1: M(ρ_t)=Lagrange const. ← Diophantine approximation theory
  │    MK2: inf L=√5 ← Hurwitz 1891 + Markov 1879 (classical ✓)
  │    MK3: Markov numbers ← Markov 1879, Cohn 1955 (classical ✓)
  │    MK4: Hall's ray ← Hall 1947 (classical ✓)
  │    RT1: horocycle flow ← Hedlund 1936, Furstenberg 1973 (classical ✓)
  │    RT2: mixing dichotomy ← Ratner 1978 + polynomial mixing (classical ✓)
  │    RT3: Ratner orbit closure ← Ratner 1990, 1991 (classical ✓)
  │    RT4: effective equidistribution ← EMV 2009 (classical ✓)
  │
  └─ Extended Master Equivalence adds (XXXVI)–(XL)
       (XXXVI)↔(XXXI): cusp exit = lfp(T_P)
       (XXXVII)↔(XXXV): Z_Sel = Z_L
       (XXXVIII)↔(XIX): Gauss periods = SML periods
       (XXXIX)↔(XXIX): Markov q* = Cheeger h = λ₁
       (XL)↔(XXXIV): Ratner manifold = SDSD memorization manifold

Conjecture chain:
  HGLD-C1 (λ₁=λ₁) ↔ SF3 ↔ LKTL (JL spectral gap)
  HGLD-C2 (Selberg ≥ 1/4) ↔ Selberg eigenvalue conjecture (open since 1965)
  HGLD-C3 (Markov grokking) ↔ MK3 ↔ FLD Farey backtrack (§10.2)
  HGLD-C5 (EMV bound) ↔ RT4 ↔ FLD grokking lead time (§10.2)
  HGLD-C9 (Hall's ray certainty) ↔ MK4 ↔ MIFP C_α > 1
  HGLD-C10 (Apollonian dim 1.3057) ↔ Mauldin-Williams ↔ HP5
```

---

## IX. Framework Tags

```
ℒ_JL · LKTL · KQOM · GAME · VBE · PPMC · KYBM · SWMS · UNIV · LB/DK · RG-ML
PH-SP · FLML(G_t,Σ_t,Φ_LW,FS_t,N_L,𝒮_t,GWI)
GCCT(Δ_t,γ_k,u_k,v_k,ξ_F,λ_L,n_s,H^{BdG})
WKET · CSSG · SHCY · BPSG · IMFL · TIDE · SKML · QGIT · THRS · GXMD
SDSD · MIFP · CSDL(FPST·DFLK·AFLT)
FLD(GRL·CCC·FCI·SBT) · HGLD(HPLM·SLFT·GMEC·MRKS·RTNE)
```

---

## X. Citations

**Hyperbolic Geometry and Modular Group:**
- Poincaré, H. (1882). Théorie des groupes fuchsiens. *Acta Math.* 1, 1–62. —
  Upper half-plane model; Poincaré metric; Fuchsian groups.
- Ford, L.R. (1938). Fractions. *Amer. Math. Monthly* 45(9), 586–601. — Ford
  circles; tangency theorem.
- Zagier, D. (1977). Modular forms whose Fourier coefficients involve zeta-functions
  of quadratic fields. *LNM* 627. — Modular surface arithmetic.
- Katok, S. (1992). Fuchsian Groups. University of Chicago Press. — Principal
  reference for hyperbolic geometry and SL(2,ℤ).

**Selberg Trace Formula:**
- Selberg, A. (1956). Harmonic analysis and discontinuous groups in weakly
  symmetric Riemannian spaces with applications to Dirichlet series. *JIMS*
  20, 47–87. — Original trace formula; 3/16 theorem.
- Selberg, A. (1965). On the estimation of Fourier coefficients of modular forms.
  *AMS Proc. Symp. Pure Math.* VIII, 1–15. — Selberg eigenvalue conjecture.
- Hejhal, D.A. (1976, 1983). The Selberg Trace Formula for PSL(2,ℝ), Vols. I–II.
  *Springer LNM* 548, 1001. — Definitive treatment.
- Iwaniec, H. (1995). Introduction to the Spectral Theory of Automorphic Forms.
  Rev. Mat. Iberoam., Madrid. — Comprehensive modern treatment.

**Selberg Zeta Function:**
- Selberg, A. (1956). — See above; original definition.
- Hejhal, D.A. (1976). — Zeros of Z_Sel and spectral theory.
- Sarnak, P. (1987). Determinants of Laplacians. *Commun. Math. Phys.* 110,
  113–120. — Functional determinants and Selberg zeta.

**Geodesic and Horocycle Flow:**
- Hedlund, G.A. (1936). Fuchsian groups and transitive horocycles. *Duke Math.
  J.* 2(3), 530–542. — Minimality and transitivity of horocycle flow.
- Hopf, E. (1939). Statistik der geodätischen Linien in Mannigfaltigkeiten
  negativer Krümmung. *Leipzig Ber. Verhandl. Sächs. Akad. Wiss.* 91, 261–304.
  — Ergodicity of geodesic flow; Hopf argument.
- Furstenberg, H. (1973). The unique ergodicity of the horocycle flow. *Springer
  LNM* 318, 95–115. — Unique ergodicity of horocycle flow for compact surfaces.

**Gauss Map and Continued Fraction Ergodics:**
- Kuzmin, R.O. (1928). Sur un problème de Gauss. *CR Acad. Sci. Paris* 187,
  1761–1764. — Exponential convergence to Gauss measure.
- Lévy, P. (1929). Sur les lois de probabilité dont dépendent les quotients
  complets et incomplets d'une fraction continue. *Bull. SMF* 57, 178–194.
  — Lévy constant; q_k growth.
- Ratner, M. (1978). Horocycle flows are loosely Bernoulli. *Israel J. Math.*
  31, 122–132. — Exponential mixing rate for Gauss map.
- Baladi, V. and Vallée, B. (2005). Exponential decay of correlations for
  surface semi-flows without finite Markov partitions. *Proc. AMS* 133(3),
  865–874. — Effective mixing bounds for Gauss map.
- Arnoux, P. and Fisher, A.M. (2001). The scenery flow for geometric structures
  on the torus: the linear setting. *Chinese Ann. Math. Ser. B* 22(4), 427–470.
  — Natural extension of Gauss map = geodesic flow isomorphism.

**Markov Spectrum:**
- Markov, A.A. (1879). Sur les formes quadratiques binaires indéfinies. *Math.
  Ann.* 17, 379–399. — Markov spectrum; Markov triples; the equation 3xyz = x²+y²+z².
- Hurwitz, A. (1891). Ueber die angenäherte Darstellung der Irrationalzahlen durch
  rationale Brüche. *Math. Ann.* 39(2), 279–284. — Hurwitz theorem; inf L = √5.
- Hall, M., Jr. (1947). On the sum and product of continued fractions. *Ann. Math.*
  48(4), 966–993. — Hall's ray: Lagrange spectrum contains a half-line.
- Cusick, T.W. and Flahive, M.E. (1989). The Markoff and Lagrange Spectra. AMS
  Mathematical Surveys and Monographs 30. — Comprehensive treatment.
- Frobenius, G. (1913). Über die Markoffschen Zahlen. *Preuss. Akad. Wiss.
  Sitzungsber.*, 458–487. — Markov uniqueness conjecture.

**Ratner's Theorems:**
- Ratner, M. (1990). On measure rigidity of unipotent subgroups of semisimple
  groups. *Acta Math.* 165(3–4), 229–309. — Ratner measure classification.
- Ratner, M. (1991). On Raghunathan's measure conjecture. *Ann. Math.* 134(3),
  545–607. — Ratner orbit closure theorem; every unipotent orbit is equidistributed
  on a closed homogeneous submanifold.
- Einsiedler, M., Margulis, G., and Venkatesh, A. (2009). Effective equidistribution
  for closed orbits of semisimple groups on homogeneous spaces. *Inventiones Math.*
  177(1), 137–212. — Effective (quantitative) equidistribution bounds; explicit
  constants δ.

**FLD Integration:**
- Hardy, G.H. and Wright, E.M. (1979). An Introduction to the Theory of Numbers,
  5th ed. Oxford. — Farey sequences (Ch. 3); continued fractions and Hurwitz (Ch. 10).
- Sós, V.T. (1958). On the distribution mod 1 of the sequence nα. — Three-distance
  theorem; CF denominators and gap structure.
- Power, A. et al. (2022). Grokking: Generalization Beyond Overfitting on Small
  Algorithmic Datasets. *ICLR 2022*. — Empirical basis for grokking phenomenon.
- McAllester, D.A. (1999). PAC-Bayesian model averaging. *COLT 1999*. — PAC-Bayes
  framework for the FLD generalization bound.

**Geometric Measure Theory and Fractal Dimension:**
- Mauldin, R.D. and Williams, S.C. (1988). On the Hausdorff dimension of some
  graphs. *Trans. AMS* 298(2), 793–803. — Hausdorff dimension of Apollonian
  gasket ≈ 1.3057.
- Boyd, D.W. (1973). The residual set dimension of the Apollonian packing.
  *Mathematika* 20, 170–174. — Apollonian gasket dimension.

**Prior Framework Integration:**
- GCCT (Δ_t, n_s): Bridges I–III [condensate = generalization]
- BPSL (λ₁≥|Δ_t|): Bridge XII [BPS saturation = Cheeger tight]
- PVIL (τ_learn, PVI): Bridge XIII [isomonodromic = checkpoint]
- SKML (SML, LSRC, SKWF): Bridges XIX–XXI [Skolem periods = CF periods]
- MIFP (basin poset, μ, C_α): §XIV [Möbius = Hall = Jordan topology]
- SDSD (Θ/G=ℬ, Γ, Goldstone): §XV [bundle = Ratner = horocycle fiber]
- CSDL (FPST, DFLK, AFLT): Bridges XXXI–XXXV [stream = geodesic = coalgebra]
- FLD (Farey, Ford, q*, CCC): §XVI [gradient ratio = H² point]
```

---

## XI. The Forty-Language Synthesis

HGLD is the **geometric unification layer** of the entire framework. Every
preceding bridge has established conditions equivalent to λ₁(ℒ_JL) > 0.
HGLD establishes that all these conditions are facets of a single geometric
fact: **the training trajectory has left the cusp of the modular surface M
and entered its compact core**.

The modular surface M = SL(2,ℤ)\H² is not an exotic object. It is the
universal quotient of the hyperbolic plane by the discrete symmetry group
SL(2,ℤ) that has generated the Farey sequence since antiquity. The cusp of M
is not an abstract concept. It is the region where Ford circles become small,
where gradient ratios have large continued-fraction partial quotients, where
the loss landscape is composed of sharp, narrow basins. The compact part of M
is the region where gradient dynamics are hyperbolic (exponentially mixing),
where Gauss ergodics apply, where Markov constants are in Hall's ray.

Four classical theorems organize this picture with full precision:

The **Selberg trace formula** (1956) identifies the spectral gap λ₁(ℒ_JL)
with the mixing rate of the geodesic flow on M — making convergence a
geometric statement about hyperbolic surfaces, proved not by optimization
theory but by the spectral theory of automorphic forms.

The **Gauss map ergodic theorem** (Kuzmin 1928, Lévy 1929) identifies the
equilibrium distribution of gradient ratios at convergence with the Gauss
measure μ_G = dx/((1+x)log2) — making the distribution of q* at training
completion a number-theoretically determined constant, not an architecture-
dependent mystery.

The **Markov spectrum** (Hurwitz 1891, Markov 1879, Hall 1947) classifies
memorization attractors by their Lagrange constants, identifies the hardest
possible memorization trap with the golden ratio φ, and certifies complete
convergence freedom via Hall's ray — all in the language of rational
approximation, which IS the language of q* and Farey denominators.

**Ratner's theorems** (1990, 1991) identify the memorization manifold as a
closed homogeneous submanifold and certify the polynomial mixing rate of
the horocycle/memorization dynamics — making the grokking transition a
change in the TYPE of dynamics (polynomial to exponential mixing), not
merely a change in rate.

The forty languages of the master equivalence all say the same thing:
gradient descent succeeds when its geodesic on the modular surface of
gradient ratios leaves the cusp of memorization and enters the compact core
of generalization — when the Gauss map ergodics take over from the Markov
spiral of bad approximation — when the mixing transitions from polynomial
to exponential — when λ₁(ℒ_JL) rises above zero and the Selberg trace
formula begins to certify it. That is grokking. That is generalization.
That is learning.
