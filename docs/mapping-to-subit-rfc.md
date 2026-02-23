# SUBIT‑Lingua — Mapping to SUBIT‑RFC

SUBIT‑Lingua is not an independent conlang.  
It is the **phonological and morphological interface** of SUBIT‑RFC.

This document defines the exact mapping between:

- SUBIT‑RFC structural primitives  
- SUBIT‑Lingua phonology  
- SUBIT‑Lingua morphology  
- SUBIT‑Lingua syntax  
- SUBIT‑Lingua semantics  

Every element of the language corresponds directly to a SUBIT coordinate.

---

# 1. Overview of the Mapping

SUBIT‑RFC defines:

- **3 axes** (WHO, WHERE, WHEN)  
- **4 bigram states** (00, 01, 10, 11)  
- **64 structural states** (the SUBIT cube)  

SUBIT‑Lingua maps these to:

| SUBIT‑RFC | SUBIT‑Lingua |
|-----------|---------------|
| Axis | Consonant (K/T/M) |
| Bigram | Vowel (A/E/O/U) |
| Atomic state | CV syllable |
| 64 states | CV‑CV‑CV structured forms |
| Structural relations | Syntax (WHO WHERE WHEN) |
| Higher‑order structures | Compounds |

This mapping is **total**, **deterministic**, and **reversible**.

---

# 2. Axis Mapping (Consonants)

SUBIT‑RFC defines three axes:

| Axis | Meaning | SUBIT‑Lingua Consonant |
|------|----------|-------------------------|
| WHO | subject, agent | **K** |
| WHERE | space, structure | **T** |
| WHEN | time, phase | **M** |

This mapping is **fixed** and **non‑negotiable**.  
All SUBIT‑Lingua semantics derive from this consonant–axis identity.

---

# 3. Bigram Mapping (Vowels)

SUBIT‑RFC defines four bigram states:

| Bigram | Meaning | SUBIT‑Lingua Vowel |
|--------|----------|---------------------|
| 00 | emptiness, potential | **A** |
| 01 | form, boundary | **E** |
| 10 | depth, source | **O** |
| 11 | energy, realization | **U** |

Every vowel in SUBIT‑Lingua is a **direct encoding** of a SUBIT bigram.

---

# 4. Atomic State Mapping (CV Syllables)

A SUBIT atomic state is:

```
Axis × Bigram
```

SUBIT‑Lingua expresses this as:

```
C V
```

Example:

- **KA** = WHO × 00  
- **TE** = WHERE × 01  
- **MO** = WHEN × 10  

There are exactly **12** such states, matching the 3×4 SUBIT grid.

---

# 5. Doubled Form Mapping (CV‑CV)

Doubled forms represent **axis‑preserving modulation**:

```
Axis × Bigram1 × Bigram2
```

Example:

- **KA‑KE** = WHO × (00 → 01)  
- **TE‑TU** = WHERE × (01 → 11)  
- **MO‑MU** = WHEN × (10 → 11)  

These correspond to **extended SUBIT states** within a single axis.

There are **48** such forms (3 axes × 4 vowels × 4 vowels).

---

# 6. Structured Form Mapping (CV‑CV‑CV)

Structured forms map directly to the **64 SUBIT cube states**.

SUBIT‑RFC defines a state as:

```
WHO(Vx) × WHERE(Vy) × WHEN(Vz)
```

SUBIT‑Lingua expresses this as:

```
K Vx – T Vy – M Vz
```

Example:

- **KA‑TE‑MU**  
  - WHO(00)  
  - WHERE(01)  
  - WHEN(11)  
  → “active manifestation of a subject”

There are **4×4×4 = 64** such forms.

This is the **core isomorphism** of the language.

---

# 7. Syntax Mapping (WHO WHERE WHEN)

SUBIT‑RFC defines structural relations as:

```
subject → spatial context → temporal phase
```

SUBIT‑Lingua expresses this through canonical syntax:

```
[WHO] [WHERE] [WHEN]
```

Examples:

- **KA TE MA**  
  → subject in structured space at the beginning

- **KE TA ME**  
  → role in open space during a phase

Syntax is therefore a **direct reflection** of SUBIT‑RFC ordering.

---

# 8. Compound Mapping

SUBIT‑RFC allows higher‑order structures by combining states.

SUBIT‑Lingua expresses this through **compounds**:

```
Unit1 Unit2 Unit3 ...
```

Each unit is a valid SUBIT state:

- CV  
- CV‑CV  
- CV‑CV‑CV  

Compounds represent **multi‑state structural relations**.

Example:

```
KA‑TE‑MU TA‑ME MA‑KU‑ME
```

Meaning:

- active subject  
- in formed space  
- at cycle‑peak  

This corresponds to a **3‑state SUBIT structural chain**.

---

# 9. Semantic Mapping

SUBIT‑Lingua semantics are **structural**, not lexical.

Meaning is derived from:

- consonant (axis)  
- vowel (bigram)  
- position (role)  
- order (composition)  

### 9.1 Base Root Semantics

```
CV → Axis(C) × Bigram(V)
```

### 9.2 Doubled Root Semantics

```
CV‑CV → Axis(C) × Bigram(V1) × Bigram(V2)
```

### 9.3 Structured Form Semantics

```
(C1Vx)-(C2Vy)-(C3Vz)
→ WHO(Vx) × WHERE(Vy) × WHEN(Vz)
```

### 9.4 Compound Semantics

```
Meaning = Meaning(Unit1) modified by Meaning(Unit2) ...
```

This is identical to SUBIT‑RFC’s structural composition rules.

---

# 10. Coordinate Mapping Table

| SUBIT‑RFC Layer | SUBIT‑Lingua Representation |
|------------------|-----------------------------|
| Axis | Consonant (K/T/M) |
| Bigram | Vowel (A/E/O/U) |
| Atomic State | CV |
| Extended State | CV‑CV |
| Cube State | CV‑CV‑CV |
| Structural Relation | WHO WHERE WHEN |
| Higher‑Order Structure | Compound |

This table defines the **complete isomorphism**.

---

# 11. Reversibility

Every SUBIT‑Lingua form can be mapped back to SUBIT‑RFC:

- CV → axis + bigram  
- CV‑CV → axis + bigram pair  
- CV‑CV‑CV → cube coordinate  
- compounds → structural chains  

The mapping is **lossless**.

---

# 12. Version Alignment

SUBIT‑Lingua versions correspond to SUBIT‑RFC layers:

| SUBIT‑Lingua | SUBIT‑RFC |
|--------------|------------|
| v0.1.0 | Core (axes, bigrams, cube) |
| v0.2.0 | Extended (derivatives, composites) |
| v0.3.0 | Full (2048 lexicon) |

---

# Status

This document is part of:

**SUBIT‑Lingua v0.1.0 — RFC Mapping Specification**

---
