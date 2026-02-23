# 05 — Semantics

SUBIT‑Lingua semantics are **structural**, not naturalistic.  
Meaning is not assigned through cultural convention, metaphor, or usage patterns.  
Instead, every word in the language corresponds directly to a **coordinate in the SUBIT‑64 semantic space** defined by SUBIT‑RFC.

Semantics in SUBIT‑Lingua is therefore:

- **compositional**  
- **axis‑based**  
- **binary‑encoded**  
- **transparent**  
- **machine‑interpretable**  

This chapter defines how meaning is constructed from axes, bigrams, syllables, and morphological structures.

---

## 1. Semantic Foundations

SUBIT‑Lingua inherits its semantic architecture from SUBIT‑RFC:

- **3 axes**  
  - WHO (subject)  
  - WHERE (space/structure)  
  - WHEN (time/phase)

- **4 bigrams**  
  - 00, 01, 10, 11

- **64 states**  
  - full SUBIT cube

Each linguistic unit maps directly to these structural elements.

---

## 2. Semantics of Consonants (Axes)

Each consonant encodes a **semantic axis**:

| Consonant | Axis | Meaning |
|-----------|------|---------|
| **K** | WHO | subject, agent, identity, will |
| **T** | WHERE | space, structure, boundary, relation |
| **M** | WHEN | time, phase, continuity, change |

These axes are **semantic primitives**.  
They do not describe objects but **structural roles**.

---

## 3. Semantics of Vowels (Bigrams)

Each vowel encodes a **binary semantic state**:

| Vowel | Bigram | Meaning |
|-------|--------|---------|
| **A** | 00 | emptiness, potential, origin |
| **E** | 01 | form, boundary, differentiation |
| **O** | 10 | depth, source, root |
| **U** | 11 | energy, intensity, realization |

These four states appear across all axes.

---

## 4. Semantics of Base Roots (CV)

A base root encodes:

```
[Axis] + [Bigram]
```

Example:

- **KA** = WHO + 00 → subject‑potential  
- **TE** = WHERE + 01 → spatial‑form  
- **MO** = WHEN + 10 → temporal‑source  

Base roots are **semantic atoms**.

---

## 5. Semantics of Doubled Roots (CV‑CV)

Doubled roots express **internal modulation** of a base concept:

- refinement  
- emphasis  
- structural elaboration  
- stable derived meaning  

Examples:

- **KA‑KE** → identity (subject + form)  
- **TE‑TU** → tension (structure + intensity)  
- **MO‑MU** → resonance (time‑source + time‑energy)

Doubled forms remain **axis‑aligned**.

---

## 6. Semantics of Structured Forms (CV‑CV‑CV)

Structured forms map directly to the **64 SUBIT cube states**.

### 6.1 Structure

```
[Axis] – [Modifier] – [Phase]
```

Each position contributes:

- **Axis** → semantic domain  
- **Modifier** → structural shaping  
- **Phase** → temporal or energetic state  

### 6.2 Example

```
KA‑TE‑MU
```

Breakdown:

- **KA** → WHO + 00 (subject‑potential)  
- **TE** → WHERE + 01 (spatial‑form)  
- **MU** → WHEN + 11 (temporal‑energy)

Meaning:

- “active manifestation of a subject”
- structurally: WHO(00) × WHERE(01) × WHEN(11)

Structured forms are **the semantic core** of the language.

---

## 7. Semantic Composition

SUBIT‑Lingua uses **positional semantics**:

### 7.1 Rule

```
[Head] [Modifier]
```

The modifier narrows, shapes, or contextualizes the head.

Example:

```
KA KE
```

Meaning:

- “a subject with form”
- “formed subject”

### 7.2 Compound Semantics

Compounds are interpreted **left‑to‑right**:

```
TA‑KO‑ME MA‑TU‑KE
```

Meaning:

- “a deep spatial root undergoing shaping”
- WHERE(10) × WHEN(01)

Compounds remain fully transparent.

---

## 8. Semantic Transparency

Every word in SUBIT‑Lingua is:

- decomposable  
- interpretable  
- structurally grounded  
- predictable  

There are **no idioms**, **no irregular meanings**, and **no semantic drift**.

---

## 9. Semantic Types

SUBIT‑Lingua supports three semantic types:

1. **Atomic semantics**  
   - base roots (CV)

2. **Derived semantics**  
   - doubled roots (CV‑CV)

3. **Structured semantics**  
   - trisyllabic forms (CV‑CV‑CV)

All higher‑order meanings are built from these.

---

## 10. Mapping to SUBIT‑RFC

| Linguistic Unit | Semantic Mapping |
|------------------|------------------|
| Consonant | Axis (WHO/WHERE/WHEN) |
| Vowel | Bigram (00/01/10/11) |
| Base root | Axis × Bigram |
| Doubled root | Axis × Bigram × Bigram |
| Structured form | Full SUBIT cube state |
| Compound | Higher‑order structural relation |

SUBIT‑Lingua is therefore **semantically isomorphic** to SUBIT‑RFC.

---

## 11. Status

This semantic system is part of:

**SUBIT‑Lingua v0.1.0 — Core Specification**

It is stable and intended to remain unchanged across future versions.

---
