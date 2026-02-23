# 04 — Minimal Syntax

SUBIT‑Lingua uses a deliberately minimal and fully regular syntactic system.  
Its purpose is not to imitate natural languages, but to provide a **transparent, compositional, and structurally interpretable interface** for expressing SUBIT‑based relations.

Syntax in SUBIT‑Lingua is:

- **order‑based**  
- **exception‑free**  
- **fully compositional**  
- **isomorphic to SUBIT‑RFC**  

This chapter defines the minimal syntax rules, clause patterns, modification structures, and composition principles.

---

## 1. Design Principles

SUBIT‑Lingua syntax follows four core principles:

1. **Minimalism**  
   Only the structures necessary for SUBIT‑level expression are included.

2. **Regularity**  
   No irregular forms, exceptions, or idiomatic constructions.

3. **Compositionality**  
   Meaning is derived from the structure of the expression.

4. **Transparency**  
   Every syntactic unit maps directly to a SUBIT coordinate or relation.

---

## 2. Basic Clause Structure

The canonical clause pattern is:

```
[WHO] [WHERE] [WHEN]
```

Where:

- **WHO** — subject axis (K‑series)  
- **WHERE** — spatial or structural axis (T‑series)  
- **WHEN** — temporal or phase axis (M‑series)

### 2.1 Example

```
KA TE MA
```

Meaning:

- “a subject in structured space at the beginning of time”
- structurally: WHO(00) × WHERE(01) × WHEN(00)

This is the minimal complete expression in SUBIT‑Lingua.

---

## 3. Word Classes

SUBIT‑Lingua does not use traditional parts of speech.  
Instead, words fall into three structural classes:

1. **Roots (CV)**  
   - can function as nouns, verbs, adjectives depending on position  
   - always retain their structural meaning

2. **Doubled Forms (CV‑CV)**  
   - function as modifiers or refined concepts  
   - attach to roots or structured forms

3. **Structured Forms (CV‑CV‑CV)**  
   - function as complex nouns, verbs, or predicates  
   - represent full SUBIT cube states

There are **no separate categories** for nouns, verbs, adjectives, or adverbs.

---

## 4. Modification

Modification is strictly **post‑positional**.

### 4.1 Rule

```
[Head] [Modifier]
```

Where:

- **Head** = root or structured form  
- **Modifier** = doubled form or root

### 4.2 Examples

```
KA KE
```

Meaning:  
“a subject with form” → “formed subject”

```
KA‑TE‑MU TA‑ME
```

Meaning:  
“an active subject in formed space”

---

## 5. Compounding

Compounds are formed by concatenating valid morphological units.

### 5.1 Rule

```
[Unit] [Unit] [Unit] ...
```

Units may be:

- roots  
- doubled forms  
- structured forms  

### 5.2 Example

```
TA‑KO‑ME MA‑TU‑KE
```

Meaning:

- “a deep spatial root undergoing shaping”
- structurally: WHERE(10) × WHEN(01)

Compounds remain fully interpretable.

---

## 6. Predicate Structure

SUBIT‑Lingua does not distinguish between nouns and verbs.  
Predication is achieved through **ordering**.

### 6.1 Rule

```
[Agent] [Process] [Phase]
```

Where:

- **Agent** = WHO‑series  
- **Process** = WHERE‑ or WHO‑series  
- **Phase** = WHEN‑series

### 6.2 Example

```
KA KU MU
```

Meaning:

- “the subject energizes at peak time”
- literally: subject → energy → temporal burst

---

## 7. Negation

SUBIT‑Lingua Core does **not** include negation.  
Negation appears in extended syntax (future version).

---

## 8. Questions

SUBIT‑Lingua Core does **not** include interrogative syntax.  
Questions are expressed through context or metadata (future version).

---

## 9. Syntax Summary

| Structure | Pattern | Function |
|----------|---------|----------|
| Basic clause | WHO WHERE WHEN | minimal expression |
| Modification | Head Modifier | refinement |
| Compound | Unit Unit... | complex concepts |
| Predicate | Agent Process Phase | action/state |

---

## 10. Status

This syntax is part of:

**SUBIT‑Lingua v0.1.0 — Core Specification**

It is stable and intended to remain unchanged in future versions.

---
