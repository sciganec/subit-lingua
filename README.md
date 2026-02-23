# SUBIT‑Lingua
![Version](https://img.shields.io/badge/version-v1.1-blue)
![Status](https://img.shields.io/badge/status-stable-brightgreen)
![License](https://img.shields.io/badge/license-MIT-lightgrey)
![Build](https://img.shields.io/badge/build-passing-success)
![Docs](https://img.shields.io/badge/docs-complete-blueviolet)


**SUBIT‑Lingua** is a minimal, fully regular artificial language built on the structural principles of **SUBIT‑RFC**.  
Its purpose is to provide a universal, compact, and formally precise interface for describing subjects, processes, and structural relations.

SUBIT‑Lingua is not a naturalistic conlang.  
It is a **structural language**, where every phoneme, syllable, and word directly corresponds to coordinates in the SUBIT system.

---

## Core Principles

### **1. Minimal Phonology**
SUBIT‑Lingua is built from a deliberately small and highly distinct phonological set:

- **3 consonants** — representing the three SUBIT axes  
  - **K** → WHO (agent / subject)  
  - **T** → WHERE (space / structure)  
  - **M** → WHEN (time / phase)

- **4 vowels** — representing the four SUBIT bigrams  
  - **A = 00**  
  - **E = 01**  
  - **O = 10**  
  - **U = 11**

This yields **12 base syllables** (KA, KE, KO, KU, TA, …, MU), forming the phonological crystal of the language.

---

## Morphological Structure

SUBIT‑Lingua uses a fully regular, layered morphology:

- **12 base roots**  
- **48 doubled roots** (KA‑KA, KA‑KE, …)  
- **64 structured trisyllabic forms** (full SUBIT cube)  
- **200+ core lexicon entries**  
- scalable to **512**, **2048**, and beyond

Every word is structurally interpretable and directly maps to SUBIT coordinates.

---

## Syntax

The language uses a minimal, compositional syntax:

- **[WHO] [WHERE] [WHEN]** as the canonical clause pattern  
- modifiers formed through doubling or trisyllabic structures  
- no irregularities, exceptions, or idioms

SUBIT‑Lingua is designed for clarity, precision, and machine‑readability.

---

## Repository Structure

```
/spec
    00-overview.md
    01-phonology.md
    02-morphology.md
    03-lexicon-core.md
    04-syntax-minimal.md
    05-semantics.md

/lexicon
    lexicon-200.md
    lexicon-512.md
    lexicon-2048-roadmap.md

/examples
    phrases.md
    texts.md
    translations.md

/tools
    generator-rules.md
    parser-design.md
    api-schema.md

/docs
    glossary.md
    design-principles.md
    mapping-to-subit-rfc.md
```

---

## Relationship to SUBIT‑RFC

SUBIT‑Lingua is the **official linguistic implementation** of the SUBIT structural protocol.  
It provides a phonological, morphological, and semantic layer on top of the SUBIT‑64 architecture.

SUBIT‑RFC repository:  
https://github.com/sciganec/subit-rfc

---

## Status

**Current version:** `v0.1.0 — SUBIT‑Lingua Core`  
Includes phonology, morphology, and the initial 200‑word lexicon.

---

## License

MIT

---

## Contributing

Contributions are welcome.  
Future work includes:

- expanding the lexicon  
- building parsers and generators  
- creating teaching materials  
- developing SUBIT‑Lingua agents and interfaces

---
