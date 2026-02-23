# SUBIT‑Lingua — Generator Rules

This document defines the **formal rules** for automatically generating valid SUBIT‑Lingua words.  
These rules ensure that all generated forms remain:

- structurally valid  
- morphologically regular  
- semantically transparent  
- isomorphic to SUBIT‑RFC  

The generator must never introduce irregularities, exceptions, or non‑CV structures.

---

# 1. Phonological Rules

## 1.1 Consonant Set (Axes)

```
C ∈ { K, T, M }
```

- K → WHO  
- T → WHERE  
- M → WHEN  

## 1.2 Vowel Set (Bigrams)

```
V ∈ { A, E, O, U }
```

- A → 00  
- E → 01  
- O → 10  
- U → 11  

## 1.3 Syllable Template

```
S = C V
```

There are exactly **12 valid syllables**.

The generator must reject:

- consonant clusters  
- codas  
- diphthongs  
- multi‑vowel sequences  

---

# 2. Morphological Rules

SUBIT‑Lingua has three canonical morphological layers:

1. **Base Roots** (CV)  
2. **Doubled Roots** (CV‑CV)  
3. **Structured Forms** (CV‑CV‑CV)

The generator must support all three.

---

# 3. Base Root Generation (12 Forms)

## 3.1 Rule

```
Root = C V
```

## 3.2 Total

```
3 consonants × 4 vowels = 12 roots
```

## 3.3 Example Output

```
KA, KE, KO, KU
TA, TE, TO, TU
MA, ME, MO, MU
```

---

# 4. Doubled Root Generation (48 Forms)

## 4.1 Rule

```
Double = (C1 V1) – (C2 V2)
```

Where:

- C1 = C2 (axis‑preserving)
- V1, V2 ∈ {A, E, O, U}

## 4.2 Total

```
3 axes × 4 vowels × 4 vowels = 48 forms
```

## 4.3 Example Output

```
KA‑KA, KA‑KE, KA‑KO, KA‑KU
TE‑TA, TE‑TE, TE‑TO, TE‑TU
MO‑MA, MO‑ME, MO‑MO, MO‑MU
```

---

# 5. Structured Form Generation (64 Forms)

Structured forms map directly to the **SUBIT‑64 cube**.

## 5.1 Rule

```
Structured = (C1 Vx) – (C2 Vy) – (C3 Vz)
```

Where:

- C1 = WHO (K)
- C2 = WHERE (T)
- C3 = WHEN (M)
- Vx, Vy, Vz ∈ {A, E, O, U}

## 5.2 Total

```
4 × 4 × 4 = 64 forms
```

## 5.3 Example Output

```
KA‑TE‑MA
KA‑TE‑ME
KA‑TE‑MO
KA‑TE‑MU
...
```

---

# 6. Compound Generation

Compounds are concatenations of valid morphological units.

## 6.1 Rule

```
Compound = Unit1 Unit2 Unit3 ...
```

Where each Unit ∈ {Root, Double, Structured}.

## 6.2 Constraints

- No more than 5 units per compound (recommended).  
- No phonological merging.  
- No elision.  
- No irregular affixes.

## 6.3 Example Output

```
KA‑TE‑MU TA‑ME
TA‑KO‑ME MA‑TU‑KE
KA KE TA‑ME‑KO
```

---

# 7. Semantic Generation Rules

SUBIT‑Lingua semantics are **structural**, not lexical.

The generator must assign meaning based on:

1. **Axis (consonant)**  
2. **Bigram (vowel)**  
3. **Position in the form**  
4. **Compositional order**

## 7.1 Base Root Semantics

```
Meaning(CV) = Axis(C) × Bigram(V)
```

## 7.2 Doubled Root Semantics

```
Meaning(CV‑CV) = refinement/modulation of Axis(C)
```

## 7.3 Structured Form Semantics

```
Meaning(C1Vx – C2Vy – C3Vz)
= WHO(Vx) × WHERE(Vy) × WHEN(Vz)
```

## 7.4 Compound Semantics

```
Meaning = Meaning(Unit1) modified by Meaning(Unit2) ...
```

---

# 8. Validity Checks

A generator must validate:

### 8.1 Phonological Validity
- Only CV syllables allowed  
- Only K/T/M consonants  
- Only A/E/O/U vowels  

### 8.2 Morphological Validity
- Doubled roots must preserve axis  
- Structured forms must follow K–T–M order  
- Compounds must contain only valid units  

### 8.3 Semantic Validity
- No contradictions (e.g., mixing axes inside a single root)  
- No undefined forms  
- No irregular patterns  

---

# 9. Output Formats

The generator should support:

- **flat lists**  
- **JSON dictionaries**  
- **CSV tables**  
- **structured lexicon blocks**  

Example JSON schema:

```json
{
  "form": "KA-TE-MU",
  "type": "structured",
  "axis_pattern": ["WHO", "WHERE", "WHEN"],
  "bigrams": ["00", "01", "11"],
  "meaning": "active manifestation of a subject"
}
```

---

# 10. Generation Modes

## 10.1 Mode A — Full Lexicon
Generates all valid forms (12 + 48 + 64 + compounds).

## 10.2 Mode B — Axis‑Restricted
Generates only WHO, WHERE, or WHEN forms.

## 10.3 Mode C — Semantic Targeting
Generates forms matching a semantic pattern:

```
WHO + depth
WHERE + intensity
WHEN + origin
```

## 10.4 Mode D — Random Valid Word
Generates a random valid form with structural guarantees.

---

# 11. Roadmap for Automated Tools

Future tools may include:

- SUBIT‑Lingua word generator  
- SUBIT‑Lingua parser  
- SUBIT‑Lingua semantic interpreter  
- SUBIT‑Lingua teaching assistant  
- SUBIT‑Lingua → English translator  
- English → SUBIT‑Lingua generator  

All tools must follow the rules in this document.

---

# Status

This file is part of:

**SUBIT‑Lingua v0.1.0 — Generator Specification**

---

