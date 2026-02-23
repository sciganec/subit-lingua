# SUBIT‑Lingua — Parser Design

This document defines the **formal design** of the SUBIT‑Lingua parser.  
The parser must be:

- deterministic  
- reversible  
- axis‑aware  
- morphology‑aware  
- fully isomorphic to SUBIT‑RFC  

The parser does **not** guess, infer, or interpret natural‑language meaning.  
It performs **structural parsing** only.

---

# 1. Parser Goals

The parser must:

1. Accept any valid SUBIT‑Lingua input (CV, CV‑CV, CV‑CV‑CV, compounds).  
2. Validate phonology, morphology, and syntax.  
3. Decompose expressions into structural units.  
4. Map each unit to SUBIT‑RFC coordinates.  
5. Produce a machine‑readable semantic structure.  
6. Reject invalid or ambiguous forms.

The parser must be **strict** and **exception‑free**.

---

# 2. Input Specification

The parser accepts:

- plain SUBIT‑Lingua text  
- whitespace‑separated units  
- hyphenated morphological forms  

### 2.1 Valid tokens

```
CV
CV-CV
CV-CV-CV
```

### 2.2 Valid characters

```
Consonants: K, T, M
Vowels: A, E, O, U
Hyphen: -
Whitespace: space, newline
```

Any other character → **invalid token**.

---

# 3. Tokenizer

The tokenizer splits input into **units**:

### 3.1 Rules

1. Split on whitespace.  
2. Preserve hyphens inside tokens.  
3. Reject tokens containing characters outside {K,T,M,A,E,O,U,-}.  
4. Reject tokens with consecutive hyphens.  
5. Reject tokens starting or ending with a hyphen.

### 3.2 Examples

Input:
```
KA-TE-MU TA-ME
```

Tokens:
```
["KA-TE-MU", "TA-ME"]
```

---

# 4. Morphological Classifier

Each token is classified as:

- **ROOT** (CV)  
- **DOUBLE** (CV‑CV)  
- **STRUCTURED** (CV‑CV‑CV)  
- **COMPOUND** (sequence of valid units)  

### 4.1 ROOT Rule

```
Length = 2
Pattern = C V
```

### 4.2 DOUBLE Rule

```
Length = 5
Pattern = C V - C V
C1 = C2 (axis‑preserving)
```

### 4.3 STRUCTURED Rule

```
Length = 8
Pattern = C V - C V - C V
C1 = K
C2 = T
C3 = M
```

### 4.4 COMPOUND Rule

A sequence of valid units:

```
Unit1 Unit2 Unit3 ...
```

---

# 5. Phonological Validator

The validator ensures:

### 5.1 Consonants

```
C ∈ {K, T, M}
```

### 5.2 Vowels

```
V ∈ {A, E, O, U}
```

### 5.3 Syllable Structure

```
CV only
```

### 5.4 Hyphen Rules

- Hyphens only between CV units  
- No trailing or leading hyphens  
- No double hyphens  

Invalid forms → **reject**.

---

# 6. Morphological Validator

### 6.1 ROOT Validation

- Must be exactly CV  
- Must pass phonology  

### 6.2 DOUBLE Validation

- Must be CV‑CV  
- Both CV must share the same consonant (axis‑preserving)  

### 6.3 STRUCTURED Validation

- Must be CV‑CV‑CV  
- Consonant pattern must be **K–T–M**  
- Vowels may vary freely  

### 6.4 COMPOUND Validation

- All units must be valid ROOT, DOUBLE, or STRUCTURED  
- No limit on length (recommended ≤ 5 units)

---

# 7. Semantic Mapper

The parser must map each morphological unit to a **SUBIT‑RFC semantic coordinate**.

## 7.1 Base Root Semantics

```
CV → Axis(C) × Bigram(V)
```

Example:
```
KA → WHO × 00
```

## 7.2 Doubled Root Semantics

```
CV-CV → Axis(C) × Bigram(V1) × Bigram(V2)
```

## 7.3 Structured Form Semantics

```
(C1Vx)-(C2Vy)-(C3Vz)
→ WHO(Vx) × WHERE(Vy) × WHEN(Vz)
```

## 7.4 Compound Semantics

Left‑to‑right composition:

```
Meaning = Meaning(Unit1) modified by Meaning(Unit2) ...
```

---

# 8. Syntax Parser

The syntax parser identifies:

- clause patterns  
- modification structures  
- compound structures  

### 8.1 Clause Pattern

```
[WHO] [WHERE] [WHEN]
```

### 8.2 Modification Pattern

```
Head Modifier
```

### 8.3 Compound Pattern

```
Unit1 Unit2 Unit3 ...
```

The parser must not infer natural‑language grammar.

---

# 9. Output Schema

The parser outputs a **JSON structure**:

```json
{
  "input": "KA-TE-MU TA-ME",
  "tokens": [
    {
      "form": "KA-TE-MU",
      "type": "structured",
      "axis_pattern": ["WHO", "WHERE", "WHEN"],
      "bigrams": ["00", "01", "11"],
      "meaning": "active manifestation of a subject"
    },
    {
      "form": "TA-ME",
      "type": "double",
      "axis": "WHERE",
      "bigrams": ["00", "01"],
      "meaning": "spatial form"
    }
  ],
  "syntax": {
    "pattern": "compound",
    "structure": ["structured", "double"]
  }
}
```

---

# 10. Error Handling

The parser must reject:

- invalid characters  
- invalid syllables  
- invalid hyphenation  
- invalid axis patterns  
- malformed structured forms  
- ambiguous tokens  

Errors must be:

- explicit  
- structural  
- non‑heuristic  

Example:

```
Error: Invalid token "KAA". Expected CV.
```

---

# 11. Future Extensions

Future versions may include:

- probabilistic semantic weighting  
- domain‑specific semantic layers  
- SUBIT‑Lingua → English translation  
- English → SUBIT‑Lingua generation  
- AST (Abstract Syntax Tree) for complex compounds  
- integration with SUBIT‑RFC engines  

---

# Status

This file is part of:

**SUBIT‑Lingua v0.1.0 — Parser Specification**

---
