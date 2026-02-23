# SUBIT‑Lingua — API Schema

This document defines the **official API schema** for interacting with SUBIT‑Lingua programmatically.  
It provides:

- JSON schemas for all linguistic units  
- canonical representations of roots, doubles, structured forms, and compounds  
- validation rules  
- semantic mapping structures  
- recommended API endpoints for tools and agents  

The API is designed to be:

- deterministic  
- reversible  
- axis‑aware  
- fully isomorphic to SUBIT‑RFC  
- stable across versions  

---

# 1. Overview

SUBIT‑Lingua expresses structure through:

- **phonology** (CV syllables)  
- **morphology** (CV, CV‑CV, CV‑CV‑CV)  
- **syntax** (ordered units)  
- **semantics** (axis × bigram × position)  

The API exposes these layers through a unified JSON interface.

---

# 2. JSON Schema: Base Root (CV)

```json
{
  "title": "SubitLinguaRoot",
  "type": "object",
  "required": ["form", "type", "axis", "bigram"],
  "properties": {
    "form": { "type": "string", "pattern": "^[KTM][AEOU]$" },
    "type": { "type": "string", "enum": ["root"] },
    "axis": { "type": "string", "enum": ["WHO", "WHERE", "WHEN"] },
    "bigram": { "type": "string", "enum": ["00", "01", "10", "11"] }
  }
}
```

---

# 3. JSON Schema: Doubled Root (CV‑CV)

```json
{
  "title": "SubitLinguaDouble",
  "type": "object",
  "required": ["form", "type", "axis", "bigrams"],
  "properties": {
    "form": { "type": "string", "pattern": "^[KTM][AEOU]-[KTM][AEOU]$" },
    "type": { "type": "string", "enum": ["double"] },
    "axis": { "type": "string", "enum": ["WHO", "WHERE", "WHEN"] },
    "bigrams": {
      "type": "array",
      "items": { "type": "string", "enum": ["00", "01", "10", "11"] },
      "minItems": 2,
      "maxItems": 2
    }
  }
}
```

**Validation rule:**  
Both consonants must match (axis‑preserving).

---

# 4. JSON Schema: Structured Form (CV‑CV‑CV)

```json
{
  "title": "SubitLinguaStructured",
  "type": "object",
  "required": ["form", "type", "axes", "bigrams"],
  "properties": {
    "form": {
      "type": "string",
      "pattern": "^K[AEOU]-T[AEOU]-M[AEOU]$"
    },
    "type": { "type": "string", "enum": ["structured"] },
    "axes": {
      "type": "array",
      "items": { "type": "string", "enum": ["WHO", "WHERE", "WHEN"] },
      "minItems": 3,
      "maxItems": 3
    },
    "bigrams": {
      "type": "array",
      "items": { "type": "string", "enum": ["00", "01", "10", "11"] },
      "minItems": 3,
      "maxItems": 3
    }
  }
}
```

**Validation rule:**  
Axis pattern must be **K–T–M**.

---

# 5. JSON Schema: Compound

```json
{
  "title": "SubitLinguaCompound",
  "type": "object",
  "required": ["form", "type", "units"],
  "properties": {
    "form": { "type": "string" },
    "type": { "type": "string", "enum": ["compound"] },
    "units": {
      "type": "array",
      "items": {
        "oneOf": [
          { "$ref": "#/definitions/root" },
          { "$ref": "#/definitions/double" },
          { "$ref": "#/definitions/structured" }
        ]
      }
    }
  },
  "definitions": {
    "root": {
      "type": "object",
      "properties": { "type": { "const": "root" } }
    },
    "double": {
      "type": "object",
      "properties": { "type": { "const": "double" } }
    },
    "structured": {
      "type": "object",
      "properties": { "type": { "const": "structured" } }
    }
  }
}
```

---

# 6. Semantic Mapping Schema

```json
{
  "title": "SubitLinguaSemantic",
  "type": "object",
  "required": ["axis_pattern", "bigrams", "coordinates"],
  "properties": {
    "axis_pattern": {
      "type": "array",
      "items": { "type": "string", "enum": ["WHO", "WHERE", "WHEN"] }
    },
    "bigrams": {
      "type": "array",
      "items": { "type": "string", "enum": ["00", "01", "10", "11"] }
    },
    "coordinates": {
      "type": "object",
      "properties": {
        "who": { "type": "string" },
        "where": { "type": "string" },
        "when": { "type": "string" }
      }
    }
  }
}
```

Coordinates map directly to SUBIT‑RFC.

---

# 7. Recommended API Endpoints

These endpoints describe **how tools should expose SUBIT‑Lingua functionality**.

---

## 7.1 `/parse`

**Input:**

```json
{ "text": "KA-TE-MU TA-ME" }
```

**Output:**

- token list  
- morphological classification  
- semantic mapping  
- syntax pattern  

---

## 7.2 `/generate/root`

Generates all 12 base roots.

**Output:**

```json
["KA", "KE", "KO", "KU", "TA", "TE", "TO", "TU", "MA", "ME", "MO", "MU"]
```

---

## 7.3 `/generate/double`

Generates all 48 doubled roots.

---

## 7.4 `/generate/structured`

Generates all 64 structured forms.

---

## 7.5 `/generate/compound`

**Input:**

```json
{
  "units": ["KA-TE-MU", "TA-ME"]
}
```

**Output:**

```json
{
  "form": "KA-TE-MU TA-ME",
  "type": "compound",
  "units": [...]
}
```

---

## 7.6 `/semantic`

Maps any valid form to SUBIT‑RFC coordinates.

---

# 8. Validation Rules

The API must enforce:

- CV syllables only  
- axis‑preserving doubles  
- K–T–M structured forms  
- no invalid characters  
- no malformed hyphens  
- no ambiguous tokens  

Invalid input must return:

```json
{
  "error": "InvalidForm",
  "message": "Expected CV-CV-CV with K-T-M axis pattern."
}
```

---

# 9. Versioning

The API follows SUBIT‑Lingua versioning:

- **v0.1.0** — Core (roots, doubles, structured)  
- **v0.2.0** — Extended Lexicon (512)  
- **v0.3.0** — Full Lexicon (2048)  

All schemas remain backward‑compatible.

---

# Status

This file is part of:

**SUBIT‑Lingua v0.1.0 — API Specification**

---
