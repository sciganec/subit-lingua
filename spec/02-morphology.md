# 02 — Morphology

SUBIT‑Lingua uses a fully regular, layered morphological system derived directly from the SUBIT‑RFC architecture.  
Every morphological unit is structurally interpretable and maps to a specific coordinate in the SUBIT‑64 space.

Morphology in SUBIT‑Lingua is not semantic in the natural‑language sense.  
It is **structural**: each form expresses a combination of axis, bigram, and phase.

This chapter defines the morphological layers, formation rules, and structural logic.

---

## 1. Morphological Layers

SUBIT‑Lingua morphology is built from three primary layers:

1. **Base Roots (12 forms)**  
   - one for each combination of consonant (axis) and vowel (bigram)

2. **Doubled Roots (48 forms)**  
   - structural modifications of the base roots

3. **Structured Trisyllabic Forms (64 forms)**  
   - full mapping of the SUBIT cube

These layers scale to larger lexicons (200, 512, 2048+ entries) without breaking regularity.

---

## 2. Base Roots (12 forms)

Base roots are the atomic morphological units of SUBIT‑Lingua.  
Each root is a single syllable of the form **CV**, where:

- **C** ∈ {K, T, M}  
- **V** ∈ {A, E, O, U}

| Axis | A (00) | E (01) | O (10) | U (11) |
|------|--------|--------|--------|--------|
| WHO (K) | **KA** | **KE** | **KO** | **KU** |
| WHERE (T) | **TA** | **TE** | **TO** | **TU** |
| WHEN (M) | **MA** | **ME** | **MO** | **MU** |

### 2.1 Structural Interpretation

Each base root encodes:

```
[Axis] + [Bigram]
```

Examples:

- **KA** = WHO + 00 → subject‑potential  
- **TE** = WHERE + 01 → spatial‑form  
- **MO** = WHEN + 10 → temporal‑source  

Base roots function as:

- standalone words  
- components of doubled forms  
- components of structured forms  
- modifiers in compounds

---

## 3. Doubled Roots (48 forms)

Doubled roots are formed by repeating or pairing base roots:

```
CV‑CV
```

There are **4 doubled forms for each base root**, yielding **48 total**.

### 3.1 Structural Role

Doubled roots express:

- refinement  
- modulation  
- internal structure  
- emphasis  
- stable derived concepts

They do **not** introduce irregularity; they are purely combinatorial.

### 3.2 Examples

#### WHO‑axis (K‑series)

- **KA‑KA** — selfhood  
- **KA‑KE** — identity  
- **KA‑KO** — intention  
- **KA‑KU** — impulse  

#### WHERE‑axis (T‑series)

- **TE‑TA** — spatial form  
- **TE‑TE** — structure  
- **TE‑TO** — framework  
- **TE‑TU** — tension  

#### WHEN‑axis (M‑series)

- **MO‑MA** — temporal origin  
- **MO‑ME** — duration  
- **MO‑MO** — depth of time  
- **MO‑MU** — resonance  

A complete table of all 48 forms appears in the lexicon.

---

## 4. Structured Trisyllabic Forms (64 forms)

The core of SUBIT‑Lingua morphology is the **structured trisyllabic form**, which maps directly to the 64 states of the SUBIT cube.

### 4.1 Structure

A structured form has the pattern:

```
[Axis] – [Modifier] – [Phase]
```

Each component is a base root (CV).

Example:

```
KA‑TE‑MU
```

Breakdown:

- **KA** → WHO + 00  
- **TE** → WHERE + 01  
- **MU** → WHEN + 11  

Meaning:

- “active manifestation of a subject”
- structurally: WHO(00) × WHERE(01) × WHEN(11)

### 4.2 Why 64 forms?

Because:

- 3 positions  
- each position has 4 vowel states (00, 01, 10, 11)  
- consonant determines axis role  

Thus:

```
4 × 4 × 4 = 64
```

These 64 forms constitute the **complete morphological cube** of SUBIT‑Lingua.

---

## 5. Compounding

SUBIT‑Lingua allows compounds formed by concatenating valid morphological units:

```
[Root] [Modifier]
[Structured] [Root]
[Root] [Root] [Structured]
```

Compounds remain:

- regular  
- transparent  
- structurally interpretable  

Example:

```
KA‑TE‑MU TA‑ME
```

Meaning:

- “an active subject within a formed space”

---

## 6. Morphological Rules Summary

### 6.1 Allowed

- CV  
- CV‑CV  
- CV‑CV‑CV  
- concatenations of valid forms  

### 6.2 Forbidden

To preserve structural clarity:

- no consonant clusters  
- no codas  
- no diphthongs  
- no irregular affixes  
- no suppletion  
- no unpredictable derivation  

SUBIT‑Lingua morphology is **strictly combinatorial**.

---

## 7. Mapping to SUBIT‑RFC

| Morphological Layer | Count | SUBIT Mapping |
|---------------------|-------|----------------|
| Base roots | 12 | Axis × Bigram |
| Doubled roots | 48 | Extended states |
| Structured forms | 64 | Full SUBIT cube |
| Compounds | ∞ | Higher‑order structures |

Morphology is therefore **isomorphic** to the SUBIT‑64 architecture.

---

## 8. Status

This morphology is part of:

**SUBIT‑Lingua v0.1.0 — Core Specification**

It is stable and intended to remain unchanged across future versions.

---
